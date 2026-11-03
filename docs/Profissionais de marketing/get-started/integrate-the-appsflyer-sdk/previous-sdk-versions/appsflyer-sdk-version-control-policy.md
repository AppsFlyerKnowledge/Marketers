---
title: Política de controle de versão do SDK da AppsFlyer
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Advertisers
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
  created_at: '2021-11-30T10:43:19Z'
  edited_at: '2026-08-18T00:15:28Z'
  id: 4412316953105
  locale: pt
  section: Previous SDK versions
  section_id: 6551300280977
  url: https://support.appsflyer.com/hc/pt/articles/4412316953105
---
> **Resumo:** saiba mais sobre a política de controle de versão do SDK da AppsFlyer e quais versões serão mantidas.

## Sobre o controle de versão

Ao longo dos anos, a AppsFlyer lançou diversas versões do SDK. Cada uma delas faz chamadas para uma versão específica da API. Assim, o intuito da política de controle é definir por quanto tempo uma API será mantida ativa para certas versões do SDK.

## Por que precisamos do controle de versão?

O objetivo do controle de versão é o seguinte:

* Ele te ajuda a saber com antecedência quando uma API para as versões do SDK integradas aos seus aplicativos será desativada. Isso é importante porque a adoção da versão leva tempo, o que significa que pode demorar até que seus usuários atualizem para uma versão mais recente do aplicativo.
* Melhora a estabilidade (a compatibilidade com versões anteriores é de 2,5 anos), eliminando erros inesperados ao usar versões muito antigas do SDK.
* Permite que você aproveite os novos recursos que exigem atualizações do SDK.

## Ciclos de vida das versões do SDK

Uma versão da API funciona por 2,5 anos. Sempre que uma nova versão principal ou secundária do SDK for lançada, a AppsFlyer definirá uma data de expiração para a versão secundária anterior (incluindo todas as suas versões de patch).

**No próximo ciclo fixo de seis meses, as versões legadas do SDK para iOS e Android deixarão de ter suporte.** O objetivo desse ciclo é trazer um aviso prévio para que as equipes se planejem com antecedência e garantam a funcionalidade do aplicativo, evitando interrupções. A atualização para a versão mais recente do SDK garante acesso aos novos recursos, além de uma estabilidade aprimorada e suporte contínuo.

> 🚧 **Importante!**
>
> Para garantir uma transição fácil, recomendamos que os desenvolvedores de aplicativos atualizem para a versão mais recente do SDK antes da data final.

## Data final de suporte vs. data de desativação

A AppsFlyer faz uma distinção entre o status **desativada** e **sem suporte** para diferenciar o nível de suporte e o impacto na mensuração de dados.

* **Versões desativadas:** versões do SDK que não são mais recomendadas devido a problemas conhecidos, como bugs críticos. Essas versões ainda podem enviar dados para a AppsFlyer, mas o uso contínuo não é recomendado. Queremos ressaltar a importância da atualização para uma versão mais recente.
* **Versões sem suporte:** versões do SDK para as quais a mensuração foi totalmente interrompida em todas as plataformas. Para Android e iOS, instalações, sessões e eventos in-app deixam de ser mensurados. O tráfego vindo dessas versões retorna um código de status 400 (a menos que ele seja especificamente excluído pela AppsFlyer), o que significa que o SDK tentará enviar chamadas de API que serão rejeitadas pelos servidores da AppsFlyer, impedindo o processamento dos dados.

## O que acontece quando uma versão do SDK chega à sua data de expiração?

Quando isso acontece, os servidores da AppsFlyer deixam de mensurar instalações, sessões e eventos in-app. Os eventos que chegarem a esses endpoints serão simplesmente rejeitados.

Como a adoção leva tempo, é **altamente recomendável** que seu desenvolvedor atualize para a versão mais recente do SDK com bastante antecedência da data de expiração.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-android-sdk-release-notes">Notas de versão do Android SDK da AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">Notas de lançamento do iOS SDK da AppsFlyer</Anchor>

<div data-zendesk-anchors="about-versioning=sobre-o-controle-de-vers%C3%A3o h_01HE7RHYC4YGZWF9EKK96RPMAN=sobre-o-controle-de-vers%C3%A3o why-do-we-need-version-control=por-que-precisamos-do-controle-de-vers%C3%A3o h_01HE7RHYC4QSVTA4ZCHTKYQSAT=por-que-precisamos-do-controle-de-vers%C3%A3o sdk-version-lifecycles=ciclos-de-vida-das-vers%C3%B5es-do-sdk h_01HE7RHYC41QN657ZTEQ0P45GD=ciclos-de-vida-das-vers%C3%B5es-do-sdk h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o h_01JVHEKR4MTFV0FDHMTQW00BCS=data-final-de-suporte-vs-data-de-desativa%C3%A7%C3%A3o what-happens-when-an-sdk-version-is-sunset=o-que-acontece-quando-uma-vers%C3%A3o-do-sdk-chega-%C3%A0-sua-data-de-expira%C3%A7%C3%A3o h_01HE7RHYC4EVSNA2F4DQ1594DH=o-que-acontece-quando-uma-vers%C3%A3o-do-sdk-chega-%C3%A0-sua-data-de-expira%C3%A7%C3%A3o h_01HE7RPQBD858TQSF27NFGGP43=veja-tamb%C3%A9m" />
