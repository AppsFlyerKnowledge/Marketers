---
title: Configurar a Biblioteca de verificação de licenças (LVL) do Google
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2026-08-18T00:07:55Z'
  id: 17329535522961
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** Proteja seus aplicativos contra o uso não autorizado adicionando a Biblioteca de verificação de licença (LVL) do Google para lidar com toda a comunicação relacionada a licenças com o Google Play.

## Visão geral

A Biblioteca de verificação de licença (LVL) é uma biblioteca que você pode adicionar aos seus aplicativos (disponível para download a partir do SDK do Android) que lida com toda a comunicação relacionada ao licenciamento com o serviço de licenciamento do Google Play.

Ela adiciona outra camada de proteção, além dos algoritmos do Protect360, permitindo a verificação de que as instalações são provenientes de usuários reais do Google Play. Isso ajuda a reduzir as discrepâncias entre o número de instalações visíveis no Google Play e o painel da AppsFlyer.

* O LVL está disponível apenas para clientes do Protect360. Sem o pacote P360, o módulo não valida licenças.
* O LVL evita a perda de receita decorrente do uso não autorizado do aplicativo, garantindo compliance e protegendo seu investimento.

O serviço de licenciamento do Google Play determina se o usuário está licenciado para usar um aplicativo ou não. O Google Play considera que os usuários são licenciados se forem compradores registrados do aplicativo. A licença é exclusiva por aplicativo e pode ser usada para proteção aprimorada. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">Saiba mais</Anchor>

O SDK da AppsFlyer coleta os dados do lado do cliente e o Protect360 executa a verificação de licença do lado do servidor, bloqueando instalações fraudulentas que falham na verificação para instalações orgânicas e não orgânicas. O "Motivo do bloqueio" que você verá no painel do Protect360 e os relatórios serão "Bots".

## Configurar LVL

<div id="add-lvl" />

<Accordion title="Processo de configuração">

No momento, este é um processo manual onde você precisará passar as informações abaixo para o seu CSM AppsFlyer para que eles possam adicioná-lo manualmente.

**Para adicionar o LVL:**

1. Defina uma propriedade no arquivo gradle.properties chamada:

   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
   ```
2. Faça referência à propriedade dinamicamente no arquivo build.gradle:

   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3. Para usuários de Kotlin DSL:

   ```http
   dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```

   > 📘 **Atenção**
   >
   > Você pode definir uma variável local na seção dependencies. Isso fará com que as versões do LVL e do SDK da AppsFlyer sejam iguais, garantindo que ambos os módulos tenham as mesmas versões.

4. Obtenha o Licenciamento e o faturamento in-app do aplicativo:  
   No Google Play Developer Console (Selecione o aplicativo -> Ferramentas de desenvolvimento -> Serviços e APIs).

   ```http
   Chave pública RSA codificada em Base64
   ```
5. Forneça ao seu CSM as seguintes informações:

* chave pública
* app-id
* versão mínima do aplicativo na qual o LVL está integrado
* Uma captura de tela da implementação do LVL (Biblioteca de Verificação de Vitalidade)

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Próximas etapas">

Assim que recebermos sua solicitação, a equipe do Protect360 configurará a verificação LVL no modo STAGING. Nesta fase, o sistema apenas reportará os resultados da verificação LVL internamente para o AppsFlyer. Alguns dias depois, verificaremos nossos dados.

**Se tudo estiver correto:**

* Vamos definir a verificação LVL para o modo de produção e ele começará a bloquear o tráfego.
* A equipe do Protect360 notificará o CSM.

**Se algo não estiver certo** (por exemplo, se não virmos informações LVL nos eventos de instalação):

* Deixaremos a verificação LVL no modo STAGING.
* Seu CSM irá notificá-lo e ajudá-lo a solucionar problemas de implementação no aplicativo.

</Accordion>

<div id="setup-process" />

<Accordion title="Testar e solucionar problemas">

Ao depurar o aplicativo, você deve ser capaz de ver informações LVL sobre a carga útil que é enviada para a AppsFlyer, como o exemplo abaixo:

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Trabalhe com sua equipe de suporte/SDK caso não haja informações de LVL na mensagem de instalação.

</Accordion>

## Perguntas frequentes

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="E se um aplicativo for instalado a partit de uma loja diferente do Google Play?">

A validação LVL não verificará e não bloqueará instalações provenientes de lojas que não sejam do Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="Quanto tempo leva para configurar o LVL?">

Depois de obter as informações, demora alguns dias úteis para configurar o LVL e verificar os dados. Veja detalhes sobre o [processo de configuração](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="O LVL afeta a funcionalidade do aplicativo?">

Não, a funcionalidade do aplicativo não é afetada.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="Qual é a diferença entre LVL e referenciador de GP?">

A verificação de licença usando LVL difere dos algoritmos de verificação de referência de GP, pois o LVL lida com a verificação de licença para o próprio aplicativo (licença por aplicativo), enquanto o referenciador de GP é usado para obter a fonte de redirecionamento da instalação para a Google Play Store com o URL de referência do pacote instalado (os carimbos de data/hora de quando um clique de referência aconteceu, quando a instalação começou, a versão do aplicativo, etc). Resumindo, enquanto o LVL é usado para verificar se o usuário está licenciado para usar o aplicativo, o referenciador de GP é usado para verificar se os detalhes da instalação não foram falsificados.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H7YJ35YKDHJ2MDZSSYKMDCJ4=vis%C3%A3o-geral set-up-lvl=configurar-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=configurar-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01JGK7NK10ZDD6CM6Y4631FB4Q=aten%C3%A7%C3%A3o 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=perguntas-frequentes 01H7YJ35YMR8PBTTSHD77WZ4AE=perguntas-frequentes 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
