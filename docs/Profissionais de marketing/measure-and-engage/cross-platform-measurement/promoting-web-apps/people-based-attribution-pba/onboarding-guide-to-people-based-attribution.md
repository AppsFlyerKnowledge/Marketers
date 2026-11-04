---
title: Guia de integração para atribuição baseada em pessoas
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-08-18T00:23:40Z'
  id: 360013821097
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360013821097
---
> **Visão geral:** Checklist de configuração de PBA

<div id="setting-up-pba" />

## Configurando PBA

A configuração de PBA consiste em vários itens de ação descritos aqui e listados na tabela a seguir.

* Entre em contato com seu CSM ou representante de vendas da AppsFlyer para habilitar a PBA.
* Agrupe propriedades digitais de marca em um pacote de marcas.
* Integre o SDK da web em seu site e o SDK mobile em seu aplicativo.
* A AppsFlyer coleta e atribui os dados.
  * Os dados são coletados de várias fontes diferentes.
  * Os dados gravados são divididos em touchpoints e eventos.
  * Os eventos são atribuídos à última visita não direta nos últimos 30 dias.
  * Os anunciantes podem designar alguns eventos como eventos de conversão. Por exemplo, compras. Os eventos de conversão são analisados nos painéis.
  * Os dados brutos são usados para realizar análises de dados personalizadas.
* Analise as jornadas dos clientes para otimizar campanhas

<div id="pba-set-up-steps" />

### Etapas de configuração da PBA

Antes de começar, entre em contato com seu CSM ou representante de vendas da AppsFlyer para habilitar a PBA. Em seguida, comece a configuração. As tarefas de configuração são detalhadas na tabela. Faça o download desta <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">planilha</Anchor> para registrar o seu progresso.

**Prática recomendada:** Implemente o <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">CUID</Anchor> no aplicativo e no seu site. A AppsFlyer receberá o CUID quando um usuário se registrar ou fizer login.

<table><thead><tr><th> </th><th>Responsabilidade</th><th>Ações</th><th>Observações</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>AppsFlyer </p></td><td><ul><li> <span><a href="./adding-an-app-to-appsflyer" target="_blank">Adicionar um aplicativo web</a> à sua conta da AppsFlyer. O aplicativo web especifica o URL do site para o qual você deseja medir o tráfego e </span>é usado para evitar <a href="./pba-media-source-attribution-rules" target="_blank">auto-atribuição</a>.</li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">Configurar pacotes de marca</a>; eles combinam as propriedades digitais de uma marca (aplicativos móveis e um aplicativo web).</span> </li><li>Especificar <a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">domínios excluídos</a> adicionais.</li></ul></td><td><ul><li><span>Análises e relatórios são agregados dentro da marca.</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td> Webmaster </td><td><ul><li>Instalar o <a href="./pba-web-sdk-integration-guide" target="_blank">Web SDK</a> no site definido pelo aplicativo da web. </li><li>Configure o Web SDK para:  <ul><li>Registrar visitas</li><li>Registrar eventos</li><li><mark> Configurar <a href="./pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid" target="_blank">CUID</a> </mark></li><li>Teste a implementação com a <a href="./test-pba-web-sdk-integration" target="_blank">Ferramenta de teste de SDK</a> </li></ul></li></ul></td><td><ul><li><span>O SDK registra visitas e eventos.</span></li><li><span>A integração é totalmente compatível com o Google Tag Manager (GTM), Adobe ou Tealium.</span></li><li> <strong>Obrigatório:</strong>  Chame SetCustomerUserID() imediatamente após um usuário se registrar ou fazer login. Se você não tiver um CUID, pergunte ao seu CSM sobre alternativas. </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>AppsFlyer</p></td><td><p>Certifique-se de que o webmaster usou o <a href="./test-pba-web-sdk-integration" target="_blank">Ferramenta de teste de SDK</a> para verificar se o site do SDK está configurado para:</p><ul><li>Registrar visitas</li><li>Registrar eventos</li><li>Configurar o CUID</li></ul></td><td><p><mark> Anunciante! Não prossiga até que esta etapa seja concluída.  </mark></p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>Desenvolvedor e anunciante</p></td><td><p>[Opcional]<a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">API Servidor para servidor web</a></p></td><td>Reporta eventos relacionados à web como renovação automática de assinatura.</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>AppsFlyer</p></td><td><ul><li> <span>Marcar </span>eventos de conversão: <ul><li><span><a href="./pba-brand-bundles-and-settings#web-event-settings" target="_blank">Eventos web</a></span></li><li><span>[Opcional] <a href="./pba-brand-bundles-and-settings#inapp-event-settings" target="_blank">Eventos in-app para dispositivos móveis</a>.</span></li></ul></li></ul></td><td><ul><li><span>Aguarde até que o processamento diário\* seja concluído antes de fazer isso.</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>AppsFlyer</p></td><td><p>Comece a usar os painéis.</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Atribuição do site</a></li><li><a href="./pba-web-assisted-installs" target="_blank">Instalações Auxiliadas pela Web</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>AppsFlyer</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Configure o Data Locker</a></td><td><p>Fornece acesso a relatórios de dados brutos PBA, incluindo touchpoints, eventos padrão e de conversão, além de relatórios especializados para instalações auxiliadas pela web.</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>AppsFlyer</p></td><td><p>[Opcional]<br/>Começar a usar <a href="./pba-raw-data-reports" target="_blank">dados brutos</a></p></td><td><p>Os dados estão disponíveis após o processamento diário\*.</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* Devido ao processamento, os dados estão disponíveis 10 horas após a meia-noite UTC no dia do evento. Isso significa que os eventos de segunda-feira estão disponíveis terça-feira 10:00 UTC. </td></tr></tbody></table>

<div id="pba-data-acquisition-via-sdkapi" />

## Aquisição de dados PBA via SDK/API

|  | Plataforma web | Plataforma mobile (aplicativo) |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide">Web</Anchor><ul><li>SDK de tag JavaScript instalado no site</li><li>Reporta visitas ao site e eventos da web</li></ul> | <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">Mobile</Anchor><ul><li>SDK de aplicativo integrado ao iOS, Android, Unity, etc.</li><li>Reporta as instalações do aplicativo e as ações do usuário que ocorrem no aplicativo</li></ul> |
| API de servidor para servidor | <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s">Servidor para servidor web</Anchor><ul><li>Relata eventos que ocorrem em servidores back-end (não na web)</li><li>Exemplo: renovação de assinatura</li></ul> | <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">Servidor para servidor mobile</Anchor><ul><li>Reporta eventos que ocorrem em servidores back-end (não no aplicativo)</li><li>Exemplo: renovação de assinatura</li></ul> |

<div data-zendesk-anchors="setting-up-pba=configurando-pba 01H8V1XPAHGFVJRKM56S2ZQTBD=configurando-pba pba-setup-steps=etapas-de-configura%C3%A7%C3%A3o-da-pba 01ECF26CMN668ZZV6XNZA3W692=etapas-de-configura%C3%A7%C3%A3o-da-pba pba-dataacquisition-via-sdkapi=aquisi%C3%A7%C3%A3o-de-dados-pba-via-sdkapi 01H8V1XPAH23BV25ZCMFR7MM9Q=aquisi%C3%A7%C3%A3o-de-dados-pba-via-sdkapi" />
