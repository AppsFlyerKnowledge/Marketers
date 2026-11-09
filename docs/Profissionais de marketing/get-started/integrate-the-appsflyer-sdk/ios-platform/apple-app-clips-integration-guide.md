---
title: Guia de integração do Apple App Clips
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2026-08-18T00:14:47Z'
  id: 360014262358
  locale: pt
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/pt/articles/360014262358
---
> **Visão geral:** Os App Clips permitem que os usuários com iOS 14 ou posterior acessem e experimentem rapidamente seu aplicativo. A AppsFlyer habilita a atribuição de App Clips e redireciona os usuários que não podem usar App Clips (por exemplo, usuários do Android) conforme necessário.

<Image align="center" alt="app_clip_flow_3.png" src="https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png" />

<div id="app-clip-integration" />

## Integração do App Clip

* Os App Clips fornecem aos usuários do iOS 14 acesso rápido e conveniente a uma experiência de aplicativo, sem a necessidade de baixar o aplicativo completo.
* Os App Clips são instalados e iniciados a partir de uma invocação (por exemplo, um código QR ou uma tag NFC). **Observação**: Banners e links do Safari Smart App no Mensagens não são compatíveis.
* O SDK da AppsFlyer é necessário para a atribuição de cliques, instalações, eventos in-app e instalações completas do App Clip.
* Independentemente do SDK, o OneLink redireciona os usuários conforme necessário:
  * Usuários sem o aplicativo instalado:
    * Com o iOS 14 ou posterior são enviados para o App Clip.
    * Com iOS 13 ou anterior, ou Android, são redirecionados com base em suas configurações no OneLink (para a loja de aplicativos, etc).
  * Os usuários com o aplicativo instalado são enviados para o aplicativo com base na configuração do Universal Link ou do App Link no OneLink.

<div id="considerations" />

### Considerações

* Os App Clips podem ter até 10 MB de tamanho. O SDK da AppsFlyer tem ~1,5 MB.
* Não há identificadores de publicidade disponíveis.
* Os App Clips são excluídos pelo sistema operacional automaticamente após um período de inatividade de 30 dias.

<div id="example" />

> 📄 **Exemplo**
>
> Marcos é o profissional de marketing de uma rede de cafeterias. Ele pede para o seu desenvolvedor iOS criar um App Clip que permite que os clientes evitem a fila e façam pedidos em segundos. Eles simplesmente se identificam usando <Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Login da Apple</Anchor>, pedem o café e pagam usando o <Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>. O desenvolvedor adiciona o SDK da AppsFlyer e garante que ele funcione no aplicativo e no app clip.
>
> Mark cria um OneLink e publica o código QR na cafeteria, junto com o slogan "Evite a fila!".
>
> Os clientes escaneam o código QR e:
>
> * Se eles tiverem um dispositivo com iOS 14 ou posterior, o App Clip será aberto—com a unidade correta da cafeteria e um cupom de desconto preenchido.
> * Se eles já tiverem o aplicativo completo instalado, o aplicativo será aberto na página de pedidos de café.
> * Se eles não tiverem o aplicativo e tiverem um dispositivo com iOS 13 ou anterior, ou Android, a página da loja de aplicativos do aplicativo de cafeteria será aberta.
>
> Marcos usa o painel e os relatórios da AppsFlyer para ver quantos cliques e instalações o App Clip recebe - e quantos usuários continuam baixando o aplicativo completo.

<div id="metrics-and-reporting" />

## Métricas e relatórios

Os dados analíticos e brutos dos App Clips estão disponíveis na plataforma com base na atividade do usuário descrita na tabela a seguir.

| Ação do usuário | Evento AppsFlyer | Painel de visão geral e ferramentas analíticas | Dados brutos |
| --- | --- | --- | --- |
| Invocação (exemplo: código QR) | Nenhum evento | Nenhum evento | Nenhum evento |
| Clicks App Card e App Clip são abertos | Clique e instalação atribuídos à fonte de invocação | <ul><li>Cliques</li><li>Instalações</li></ul> | <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| Usa o App Clip | <ul><li>[Opcional] O desenvolvedor envia evento in-app</li><li>Após a primeira inicialização do App Clip, as inicializações seguintes são contadas como sessões.</li></ul> | <ul><li>Evento in-app</li><li>Sessão</li></ul> | <ul><li>Evento in-app enviado pelo desenvolvedor</li><li><Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| Baixar e iniciar o aplicativo completo | Evento in-app | Nome do evento no aplicativo= af\_app\_clip\_to\_full\_app | <ul><li>Nome do evento no aplicativo= af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| Uso contínuo do aplicativo completo | [Opcional] O desenvolvedor envia evento in-app | Evento in-app | <ul><li>Evento in-app enviado pelo desenvolvedor</li><li><Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**Painel de coorte**

Visualize o desempenho do App Clip no <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">Painel de coorte</Anchor>, onde você pode:

* Ver quanto tempo leva para os usuários irem do App Clip para a instalação completa do aplicativo.
* Usar a métrica de conversão in-app para comparar o desempenho de diferentes campanhas de invocação.

<div id="app-clip-implementation" />

## Implementação do App Clip

O procedimento a seguir detalha o que você e o desenvolvedor do iOS precisam fazer para desenvolver e integrar App Clips.

<div id="scope-of-work" />

#### Escopo do trabalho

| **Quem está envolvido**<ul><li>**Anunciante**:<ul><li>Configura Apple App Clips em templates do OneLink.</li><li>Coloca os links do OneLink no portal Apple App Store Connect.</li><li>Visualiza métricas no painel e nos relatórios da AppsFlyer.</li></ul></li><li>**Desenvolvedor iOS**:<ul><li>Cria o App Clip</li><li>Integra o SDK da AppsFlyer no App Clip.</li></ul></li></ul> |
| --- |
| **Pré-requisitos**<ul><li>Uma conta da AppsFlyer com pelo menos um aplicativo.</li><li>Um template do OneLink com Links Universais e um link do OneLink configurado para direcionar todos os usuários do aplicativo.<br />**Recomendação**: O template e a invocação de link que você usa para o App Clip enviam todos os usuários sem o aplicativo completo para o App Clip. Portanto, considere ter um template separado e um link personalizado para casos em que você deseja enviar esses usuários para a App Store, em vez do App Clip.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="Desenvolver App Clip">

Para obter instruções completas sobre como os desenvolvedores criam um App Clip para seu aplicativo, consulte o <Anchor target="_blank" href="https://developer.apple.com/app-clips/">Guia do App Clip para desenvolvedores</Anchor> da Apple.

Para obter um aplicativo de exemplo simplificado que demonstra o uso de App Clips e sua integração com um aplicativo completo, consulte o <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">Guia do App Clip da AppsFlyer</Anchor>.

</Accordion>

<div id="integrate-sdk" />

<Accordion title="Integrar SDK">

* O SDK é necessário para a atribuição da AppsFlyer de cliques, instalações, eventos no aplicativo e instalações completas do aplicativo App Clip.
* O OneLink redireciona os usuários independentemente da integração do SDK.

**Para instalar o SDK e configurar o SDK completo do aplicativo**:

Envie os seguintes links para o seu desenvolvedor iOS e diga a ele para seguir as instruções para:

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">Integração do SDK no App Clip</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">Configurar a atribuição de instalação de aplicativo de clipe para aplicativo completo</Anchor>
* [Opcional] <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">Configurar eventos in-app</Anchor>, se você ainda não tiver eventos in-app sendo medidos para seu aplicativo completo ou quiser usar eventos in-app diferentes para o App Clip.

</Accordion>

<div id="configure-onelink" />

<Accordion title="Configurar OneLink">

**Pré-requisitos**:

* <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Template do OneLink</Anchor> para seu aplicativo completo com links universais do iOS configurados.
* <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Link do OneLink</Anchor>.
* **Recomendação**: O template e a invocação de link que você usa para o App Clip enviam todos os usuários sem o aplicativo completo para o App Clip. Portanto, considere ter um template separado e um link personalizado para casos em que você deseja enviar esses usuários para a App Store, em vez do App Clip.

**Para configurar o template do OneLink para seu App Clip**:

1. No painel da AppsFlyer, acesse **Engajar** > **Gerenciamento OneLink**.
2. Selecione o ícone**Template do OneLink**que você usa para direcionar os usuários para seu aplicativo completo.
3. Verifique se o template do OneLink tem Links Universais configurados. (Veja <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Instruções</Anchor> para adicionar links universais.)
4. Clique em **Salvar**.  
   O arquivo AASA é atualizado para dar suporte ao App Clip.
5. No painel da AppsFlyer, acesse **Engajar** > **Gerenciamento OneLink**.
6. Selecione o ícone**Link personalizado do OneLink** com base no template configurado nas etapas 1 a 4 que você usa para direcionar os usuários para o App Clip.
7. Verifique se você tem um canal de mídia (pid) especificada.  
   O canal de mídia precisa ser especificada no URL (por exemplo: **pid=chartboost\_int**) ou contidos no link.

**Para verificar se o App Clips está ativado no AppsFlyer OneLink:**

1. Crie um URL para obter seu arquivo de associação. O URL é criado pegando o domínio do seu template OneLink e adicionando `/.well-known/apple-app-site-association`.   
   Por exemplo: `coffee.onelink.me/.well-known/apple-app-site-association`.
2. Vá para o URL do seu arquivo de associação.  
   O arquivo apple-app-site-association é baixado automaticamente.
3. Abra o arquivo apple-app-site-association com um editor de texto (por exemplo, Notepad).
4. Certifique-se de que o arquivo contenha a palavra "**appclips**". e que o ID do pacote termine com "**. Clip**". Por exemplo:  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app. Clip",
         ...
       ]
   ...
   }
   ```

   Em caso afirmativo, você configurou com êxito os App Clips no lado da AppsFlyer e o App Clip é implementado em qualquer template do OneLink com o mesmo subdomínio.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="Configurar o App Store Connect">

**Pré-requisitos**: Conclusão de [Configuração do template do OneLink para App Clips](/docs/apple-app-clips-integration-guide#configure-onelink)

**Para configurar seu App Clip para funcionar com o OneLink**:

1. Na página do seu aplicativo no App Store Connect, vá para **Construir** > **Status do domínio**.
2. Verifique se o domínio do OneLink é exibido em **Criar domínios** e que **Status do cache** e **Status de depuração** são ambos "validados".
3. No painel da AppsFlyer, acesse **Engajar** > **Gerenciamento OneLink**.
4. Passe o mouse sobre o ícone **Ações** do link que deseja testar e clique em **Obter URL**.
5. Registre o URL curto (ou o prefixo do URL longo).
6. Na página do seu aplicativo no App Store Connect, vá para **Clipe de aplicativo** > **Editar experiências avançadas** > **+Adicionar** > **Próximo**.
7. Em **URL da experiência do App Clip**, cole o URL personalizado do OneLink que você registrou na etapa 5.  
   **Observação**: Você pode anexar parâmetros de consulta após o URL personalizado principal, mas não pode alterar o caminho.
8. Clique em **Próximo**.  
   Seu App Clip agora está configurado para funcionar com o OneLink. Mais instruções sobre as configurações do App Store Connect estão disponíveis no <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">Guia do desenvolvedor da Apple</Anchor>.

</Accordion>

<div id="testing" />

<Accordion title="Testes">

**Pré-requisitos**: Um <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">Dispositivo de teste registrado</Anchor> com iOS 14 sem seu aplicativo completo instalado.

**Para testar sua integração OneLink/App Clip:**

1. No painel da AppsFlyer, acesse**Contratar** > **Gerenciamento OneLink**.
2. Passe o mouse sobre o ícone **Ações** do link que deseja testar e clique em **Obter URL**.
3. Escaneie o código QR com seu dispositivo.  
   O App Clip Card é exibido no seu dispositivo, indicando que a integração do OneLink/App Clip está configurada corretamente.

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

<div id="traits-and-limitations::26141033" />

<Accordion title="Características e limitações">

| Característica/limitação | Descrição |
| --- | --- |
| Métodos de invocação | <ul><li>Códigos QR e tags NFC são compatíveis.</li><li>Banners e links do Safari Smart App no Mensagens não são compatíveis.</li></ul> |
| Proteção contra fraudes | A funcionalidade SKAdNetwork não está disponível. Portanto, as instalações do App Clip são exibidas no painel da SKAdNetwork como orgânicas. |
| Os links diretos universais do OneLink | Apenas uma experiência avançada do App Clip é permitida por link personalizado do OneLink. Isso significa que você não pode adicionar caminhos adicionais ao OneLink no App Store Connect. |
| Os alertas do Protect360 são atualizados no horário UTC diário. | O Protect360 não é compatível com App Clips. |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">Solução de atribuição para Apple App Clips da AppsFlyer</Anchor>

<div data-zendesk-anchors="app-clip-integration=integra%C3%A7%C3%A3o-do-app-clip h_01HDNZQTCBXY0Y3QYCBNVH7EAW=integra%C3%A7%C3%A3o-do-app-clip considerations=considera%C3%A7%C3%B5es h_01HDNZQTCBPJWY6H2M452QH644=considera%C3%A7%C3%B5es h_01HDNZQTCB7NB682YTSMNCJSDP=exemplo metrics-and-reporting=m%C3%A9tricas-e-relat%C3%B3rios h_01HDNZQTCBNG3TYRAA7GVPF39P=m%C3%A9tricas-e-relat%C3%B3rios app-clip-implementation=implementa%C3%A7%C3%A3o-do-app-clip h_01HDNZQTCBJK7SB96G8A4DHR34=implementa%C3%A7%C3%A3o-do-app-clip scope-of-work=escopo-do-trabalho h_01HDNZQTCB1AKW9QFRRM9VVN4D=escopo-do-trabalho h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HDNZQTCCMW2YNK1G34EBM7DM=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=veja-tamb%C3%A9m" />
