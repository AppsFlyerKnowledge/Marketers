---
title: 'Boletín: el framework iAd se eliminará del SDK de iOS'
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-13T10:20:29Z'
  edited_at: '2026-10-20T03:56:01Z'
  id: 19329934807569
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/19329934807569
---
| **¿Qué hay de nuevo?** | Apple anunció que cualquier aplicación que contenga código del framework iAd dejará de iniciarse en iPhone y iPad dentro de dos años. iAd framework was mandatory for iOS apps working with Apple Search Ads (ASA) in the past before it was replaced by the Apple Ads Attribution API.<br /><br />Desde la versión 6.10.1, el SDK de iOS de AppsFlyer ya no utiliza el framework iAd y se basa únicamente en la API de atribución de Apple Ads. Sin embargo, el código del framework seguía incluido en el SDK.<br /><br />Sin embargo, la próxima versión del <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes">SDK de iOS</Anchor> de AppsFlyer (6.12.3) cumplirá los requisitos de Apple y no contendrá ningún código del framework iAd. Se espera que la versión 6.12.3 llegue a mediados de noviembre y recomendamos encarecidamente adoptarla.<br /><br />**Ten en cuenta que, aunque no actualices tu SDK a la versión 6.12.3, Apple ofrece un periodo de gracia de 2 años antes de bloquear el inicio de tu app.** |
| --- | --- |
| **Fecha de entrada en vigor** | La futura fecha de lanzamiento del SDK de iOS 6.12.3 (noviembre de 2023) |
| **Esto afecta a** | La atribución no se ve afectada. De hecho, desde la versión 6.10.1 el SDK de AppsFlyer utiliza el framework AdServices más reciente de ASA y no depende del framework iAd, que ya está obsoleto. |