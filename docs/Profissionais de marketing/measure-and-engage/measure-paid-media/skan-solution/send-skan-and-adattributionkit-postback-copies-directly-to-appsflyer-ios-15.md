---
title: Envie cópias de postback da SKAN diretamente para a AppsFlyer (iOS 15+)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2026-08-18T00:32:06Z'
  id: 4402320969617
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/4402320969617
---
> **Resumo:** a partir do iOS 15, configure seu aplicativo para enviar cópias de postback diretamente para a AppsFlyer, além de enviá-los para ad networks. Isso permite que a AppsFlyer valide o valor de conversão (CV) e verifique a integridade do postback. Configure a Push API da AppsFlyer para encaminhar simultaneamente cópias de postback para um endpoint adicional selecionado.

> 📘 **Atenção**
>
> Ao longo deste artigo, as referências a **SKAN** incluem tanto o **SKAdNetwork** quanto o framework mais recente **AdAttributionKit (AAK)**.

## Por que enviar cópias de postback para a AppsFlyer?

* Tenha todos os postbacks num só lugar: Postbacks contêm informações críticas para os anunciantes—mais especificamente, o valor de conversão (CV) usado para mensurar a qualidade do usuário. Em postbacks, o CV não é criptografado nem faz parte da assinatura do postback. Consequentemente, o CV, conforme relatado pela ad network, não pode ser validado e está sujeito à manipulação. A AppsFlyer encaminhará as cópias de postback usando a Push API para endpoints definidos por você.
  * Obrigatório para Apple Ads: o encaminhamento de postbacks é necessário para reportar o SKAN do AA (iOS 15+).
* Veja as métricas de redownload; algumas ad networks não compartilham dados de redownload com a AppsFlyer. A cópia do postback ajuda a completar a sua visão.
* Veja os dados do aplicativo do publisher
* Veja o engajamento por tipo de toque

**Atenção!** A AppsFlyer ainda deve receber postbacks de ad networks, pois eles contêm dados adicionais fornecidos pela ad network (por exemplo, nome da campanha).

## Configure seu aplicativo para enviar cópias de postback para a AppsFlyer

De acordo com a documentação da Apple, você pode definir um único endpoint para o postback da SKAN.

**Para registar o endpoint da AppsFlyer:**

1. Peça ao seu desenvolvedor do iOS para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">adicionar a AppsFlyer</Anchor> como um endpoint de postback da SKAN na próxima versão do aplicativo.
2. Envie o aplicativo para iOS.
3. Os postbacks serão enviados para a AppsFlyer quando a nova versão for publicada (não do TestFlight).
4. Você pode ver os postbacks recebidos no <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">relatório de cópia dos postbacks</Anchor>.

> 🚧 **Importante!**
>
> Aplicativos que não têm tráfego SKAN verão a seguinte mensagem, mesmo após completar a configuração: "seu aplicativo não está configurado para enviar cópias de postback do iOS (iOS 15+) para a AppsFlyer. Isso é necessário para garantir a integridade de sua mensuração na SKAN."

## Erros comuns

> 📘 **Não acredite em tudo o que você ouve!**
>
> Essas afirmações são verdadeiras ou falsas?
>
> ![TrueOrFalse.png](https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png)
>
> * Os anunciantes não dependem mais de ad networks para obter postbacks.
>   * **Falso.** O anunciante ainda depende da ad network para decodificar partes significativas de dados. Por exemplo, somente a ad network pode mapear o campaign ID da SKAN para o nome da campanha.
> * Assim que configuro um endpoint adicional, cópias de todos os postbacks são enviadas para lá.
>   * **Falso.** A funcionalidade de endpoint adicional só está disponível para dispositivos que com versões iOS 15+. As cópias de postback não são enviadas a partir de dispositivos com versões anteriores.

## Características e limitações

Depois que um aplicativo foi configurado para enviar cópias de postback para a AppsFlyer, pode demorar alguns dias até que elas apareçam no dashboard.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Desenvolvedor da Apple</Anchor>

<div data-zendesk-anchors="h_01KDSTGH21EG5MT0KFXZ40VMW1=aten%C3%A7%C3%A3o why-send-postback-copies-to-appsflyer=por-que-enviar-c%C3%B3pias-de-postback-para-a-appsflyer h_01HE7SV29Y7DNSKAAR91MJX986=por-que-enviar-c%C3%B3pias-de-postback-para-a-appsflyer configure-your-app-to-send-postback-copies-to-appsflyer=configure-seu-aplicativo-para-enviar-c%C3%B3pias-de-postback-para-a-appsflyer h_01HE7SV29YDFA5Z0X4WS87YK0Y=configure-seu-aplicativo-para-enviar-c%C3%B3pias-de-postback-para-a-appsflyer h_01HH9WCVH4C37ZGMRZRB7EQT6B=importante common-misconceptions=erros-comuns h_01HE7SV29YC855TGCXTCT4KHRN=erros-comuns h_01HE7SV29YMMTPH6EKYF3GQYEN=n%C3%A3o-acredite-em-tudo-o-que-voc%C3%AA-ouve traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HHH74CC5X0T5M1F86XWMNH9V=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HE7SX466CMCC03K99H68ZRBN=veja-tamb%C3%A9m" />
