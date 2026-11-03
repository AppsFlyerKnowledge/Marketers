---
title: >-
  [Beta fechada] Implementação da regra de série de eventos para prevenção
  avançada de fraude
metadata:
  keywords:
    - Marketers
    - Closed beta
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-07-10T09:41:19Z'
  edited_at: '2026-09-29T00:03:28Z'
  id: 26596474431761
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/26596474431761
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** A série de eventos nas regras de validação permite que os anunciantes definam uma sequência de eventos pela qual um usuário real deve passar. Qualquer desvio da ordem definida por você ou do intervalo de tempo entre eventos é detectado e bloqueado.

## Introdução

Os anunciantes podem definir uma sequência de eventos pela qual um usuário real deve passar no seu aplicativo. A AppsFlyer avalia essa sequência usando uma janela de avaliação que começa no dia em que a regra é salva: ela cresce diariamente até 30 dias e depois se torna uma janela contínua de 30 dias, que avança todos os dias. Eventos disparados antes da criação da regra nunca são avaliados.

Se a sequência for interrompida, seja na ordem ou no tempo, o usuário é considerado falso e:

* Quaisquer eventos in-app, bem como sessões, após a interrupção são bloqueados imediatamente.
* A instalação é bloqueada na pós-atribuição, se ocorrer dentro da janela de pós-atribuição (7 dias)
* Os eventos in-app associados dentro da janela de avaliação são bloqueados como parte do processo de pós-atribuição
* Outros eventos in-app que atendem às condições da regra em outras partes do aplicativo não são afetados

Observação: editar a regra de qualquer forma, incluindo seleção de aplicativo, condições, fonte de tráfego, sequência de eventos ou ativação/desativação, redefine a janela de avaliação para o dia 0.

## Para quem é isso?

Esse recurso é adequado apenas para:

* **Eventos de SDK** - Apps que criarão regras apenas com eventos de SDK.
* **Eventos não repetidos** - Aplicativos que têm uma sequência de eventos em que os eventos não ocorrerão mais de uma vez na sequência. Se o mesmo evento ocorrer mais de uma vez na sequência (por exemplo, o Evento C for enviado duas vezes), isso será tratado como uma violação e os eventos associados serão bloqueados.
* **Tráfego NOI** - Esse recurso está disponível apenas para tráfego NOI

## Como configurar uma regra de série de eventos

Siga estas instruções para configurar uma regra de série de eventos:

1. Acesse **Configurações > Regras de validação**
2. Clique em **+ Nova regra**
3. Nomeie a regra
4. Selecione a aba **Pós-atribuição**
5. Selecione o aplicativo para o qual você deseja definir a regra  
   Observação: você só pode selecionar um aplicativo para cada regra
6. Defina a fonte de tráfego na qual a regra será executada
7. Escolha as condições. No momento, as opções são:
   1. Geografia
   2. Modelo do dispositivo
8. Seu identificador único é definido automaticamente com base no aplicativo selecionado: **IDFA** para iOS ou **ID do anunciante** para Android. Você pode alterar para **ID de usuário do cliente** em qualquer uma das plataformas.
9. Defina a sequência de eventos: adicione pelo menos 2 eventos, na ordem em que um usuário real deve concluí-los
10. Opcionalmente, defina um intervalo mínimo entre cada par de eventos. Se você não definir um, um mínimo de 1 segundo será aplicado por padrão
11. Revise a seção **Resultado da regra** para confirmar o estado da janela de avaliação e o tempo total mínimo da sequência
12. Clique em **Salvar**.

> 🚧 **Importante!**
>
> Não selecione todos os eventos do seu aplicativo. Selecione apenas os eventos em que normalmente pode haver fraude

## Acesso aos dados

Quando uma regra de série de eventos bloqueia uma instalação ou um evento in-app, os detalhes são registrados nos seus Relatórios de dados brutos. Acesse **Dados brutos > Protect360 & Regras de validação** para encontrar eventos bloqueados e use os campos abaixo para identificar quais foram bloqueados por essa regra.

| Relatório | Campos principais |
| --- | --- |
| Instalações pós-atribuição | <ul><li>Motivo da fraude = bots de validação</li><li>Submotivo da fraude = regras de validação pa</li><li>Valor do motivo do bloqueio = nome da regra</li></ul> |
| Eventos in-app pós-atribuição | <ul><li>fraud\_reason = bots de validação</li><li>fraud\_sub\_reason = regras de validação pa</li></ul> |
| Eventos na aplicação bloqueados | <ul><li>Motivo do bloqueio = bots de validação</li><li>Submotivo do bloqueio = regras de validação pa</li><li>Valor do motivo do bloqueio = nome da regra</li></ul> |

## Exemplos

Abaixo estão exemplos de diferentes séries de eventos e se elas seriam consideradas fraudulentas ou não.

<Accordion title="Exemplo 1">

**Regra definida**

O usuário deve executar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**Executado na prática**

O usuário executa os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 1: evento A enviado
* Dia 2: evento B enviado
* Dia 3: evento C enviado

**Resultado:**

Não é fraude. O usuário realizou a série de eventos na sequência definida.

</Accordion>

<Accordion title="Exemplo 2">

**Regra definida**

O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**O que foi realmente realizado**

O usuário realiza os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 1: evento A enviado
* Dia 2: evento C enviado
* Dia 3: evento B enviado

**Resultado:**

Fraude. O usuário realizou o Evento C antes do Evento B, o que está fora da sequência definida. Como resultado,

* O evento A será bloqueado na pós-atribuição
* O evento B será bloqueado em tempo real
* O evento C será bloqueado em tempo real ou na pós-atribuição, pois esse evento quebrou a sequência
* Todos os eventos seguintes serão bloqueados em tempo real

</Accordion>

<Accordion title="Exemplo 3">

**Regra definida**  
 O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B (tempo mínimo até o evento anterior: 1 hora)
* Evento C (tempo mínimo até o evento anterior: 2 horas)

**Realizado**  
 O usuário realiza os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 0: evento A enviado
* Dia 0: evento B enviado 10 minutos após o evento A
* Dia 0: evento C enviado 2 horas após o evento B

**Resultado:**  
 Fraude. O usuário realizou todos os eventos na ordem correta, mas o intervalo entre o evento A e o evento B foi de apenas 10 minutos, o que é menor do que o mínimo configurado de 1 hora. A restrição de tempo foi violada, independentemente da ordem correta da sequência. Como resultado,

* O evento A será bloqueado na pós-atribuição
* O evento B será bloqueado em tempo real, pois violou a restrição de tempo mínimo
* O evento C será bloqueado em tempo real, pois ocorreu após uma sequência violada
* Todos os eventos seguintes serão bloqueados em tempo real

</Accordion>

<Accordion title="Exemplo 4">

**Regra definida**  
 O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**O que ocorreu na prática**  
 O usuário realiza os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 1: Evento A enviado
* Dia 2: Evento B enviado
* Evento C não enviado

**Resultado:**  
 Não é fraude. O usuário concluiu os eventos A e B na ordem correta, mas nunca disparou o evento C. Sequências incompletas não são sinalizadas como violações. Nenhum evento é bloqueado. A regra continua a avaliar eventos futuros dentro da janela de avaliação de 30 dias.

</Accordion>

<Accordion title="Exemplo 5">

**Regra definida**

O usuário foi identificado pelo <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor>.

O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**O que ocorreu na prática**

O usuário realiza os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 1: Evento A enviado
* Dia 1: a desinstalação ocorreu
* Dia 1: a instalação ocorreu
* Dia 2: Evento B enviado
* Dia 3: Evento C enviado

**Resultado:**

Não é fraude. Como o usuário foi identificado pelo <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> e os eventos foram realizados na ordem.

</Accordion>

<Accordion title="Exemplo 6">

**Regra definida**

O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**O que aconteceu na prática**

O usuário foi identificado pelo ID do Anunciante

O usuário realiza os eventos nesta ordem:

* Dia 0: a instalação ocorreu
* Dia 1: evento A enviado
* Dia 1: a desinstalação ocorreu
* Dia 1: a instalação ocorreu
* Dia 2: evento B enviado
* Dia 3: evento C enviado

**Resultado:**

Não é fraude. Como o usuário foi identificado pelo ID do Anunciante e os eventos foram realizados na ordem.

</Accordion>

<Accordion title="Exemplo 7">

**Regra definida**  
 O usuário deve realizar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

Regra criada em 1º de janeiro.

**O que aconteceu na prática:**

* 1º de janeiro (Dia 0): Regra criada. A janela de avaliação começa. Os eventos acionados antes desta data são ignorados.
* 15 de janeiro (Dia 14): evento A enviado. A janela está aumentando e agora avalia os últimos 14 dias.
* 30 de janeiro (Dia 29): evento B enviado. A janela está aumentando e agora avalia os últimos 29 dias.
* 31 de janeiro (Dia 30): A janela chega a 30 dias e se torna uma janela contínua de 30 dias, avançando todos os dias.
* 20 de fevereiro: evento C enviado. A janela contínua agora retrocede 30 dias, até 21 de janeiro. O evento A (acionado em 15 de janeiro) fica fora da janela e deixa de ser avaliado.

**Resultado:**  
 Não é fraude. Em 20 de fevereiro, a janela contínua retrocede até 21 de janeiro, deixando o evento A (15 de janeiro) fora da janela de avaliação. Somente os eventos B e C são avaliados — ambos na ordem correta, sem nenhuma violação sinalizada.

</Accordion>

<Accordion title="Exemplo 8">

**Regra definida**

O usuário deve executar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**Executado na prática**

O usuário executa os eventos nesta ordem:

* Dia 0: A instalação ocorreu
* Dia 1: Evento A enviado
* Dia 2: Evento B enviado
* Dia 3: evento B enviado
* Day4: evento C enviado

**Resultado:**

Fraude. Como o mesmo evento (Evento B) aconteceu duas vezes, presumimos fraude, pois não é possível ter o mesmo evento duas vezes em uma sequência.

</Accordion>

<Accordion title="Exemplo 9">

**Regra definida**  
 O usuário foi identificado por Customer User ID (CUID).  
 O usuário deve executar os eventos nesta ordem:

* Evento A
* Evento B
* Evento C

**O que foi realmente executado**  
 O usuário dispara eventos em dois dispositivos usando o mesmo CUID:

* Dia 0: a instalação ocorreu no dispositivo 1
* Dia 0: a instalação ocorreu no dispositivo 2
* Dia 1: evento A enviado do dispositivo 1
* Dia 2: evento B enviado do dispositivo 2
* Dia 3: evento C enviado do dispositivo 1

**Resultado:**  
 Não é fraude. Como o usuário foi identificado por CUID, a avaliação da sequência abrange todos os IDs da AppsFlyer associados ao mesmo CUID e ao mesmo ID da regra. Os eventos A, B e C foram executados na ordem correta, independentemente de qual dispositivo os disparou.

</Accordion>

<Accordion title="Especificações e limitações">

* É possível definir até 100 eventos em cada regra.
* Ao atingir 80 eventos, um aviso é exibido. Ao atingir 100 eventos, o limite é alcançado e a regra precisa ser dividida para adicionar mais.
* O tempo mínimo que pode ser definido entre eventos consecutivos é de 1 segundo. Se nenhum intervalo de tempo for configurado para um par, o padrão de 1 segundo será aplicado automaticamente.
* O intervalo máximo de tempo configurável entre eventos é de 30 dias, alinhado à janela de avaliação.
* A janela de avaliação começa no dia 0 (data de criação da regra) e cresce diariamente até 30 dias, após o que se torna uma janela contínua de 30 dias, avançando todos os dias. Eventos disparados antes da data de criação da regra nunca são avaliados.
* Qualquer edição em uma regra redefine a janela de avaliação para o dia 0.
* Até 10 regras ativas podem ser definidas por conta.
* As regras de séries de eventos só podem ser usadas para tráfego não orgânico.
* Somente o tráfego de SDK é compatível. O tráfego S2S está fora do escopo da Fase 1.
* Sequências incompletas não são sinalizadas como violações.
* O mesmo evento não pode aparecer duas vezes em uma única sequência.
* Somente a lógica AND é compatível entre as condições. A lógica OR não é compatível.

</Accordion>

## Perguntas frequentes

<Accordion title="O que acontece após uma reinstalação?">

Se a reinstalação redefinir eventos que o usuário já concluiu, isso será tratado como uma violação. Se o usuário retomar de onde parou, nenhuma violação será sinalizada.

</Accordion>

<div data-zendesk-anchors="intro=introdu%C3%A7%C3%A3o h_01J2DZP5DWZ0V52PA0RGQ4PNHN=introdu%C3%A7%C3%A3o who-is-this-for=para-quem-%C3%A9-isso h_01J2E0CYHW4TBK6TQHMHYEVGEM=para-quem-%C3%A9-isso how-to-set-up-a-series-of-event-rule=como-configurar-uma-regra-de-s%C3%A9rie-de-eventos h_01J2E0MZYM7GZ2N6Z0NDRQQPTF=como-configurar-uma-regra-de-s%C3%A9rie-de-eventos h_01J2ED6016XRPDVJBJ0X388THJ=importante accessing-data=acesso-aos-dados h_01KWSHAXG3K8PQV334JHGC8A0G=acesso-aos-dados examples=exemplos h_01J2E0XXG85150ZBSSFVF98W83=exemplos faq=perguntas-frequentes h_01KWSHAXG4PFT77C0FWCXTF3AH=perguntas-frequentes" />
