---
title: Gerenciar criativos
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2025-09-17T12:01:55Z'
  edited_at: '2026-10-08T00:02:43Z'
  id: 39137008313105
  locale: pt
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/pt/articles/39137008313105
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** A gestão de criativos te ajuda a centralizar, revisar e lançar criativos com mais rapidez. Use-a para sincronizar os criativos do seu armazenamento de criativos, conferir o status da atividade em diferentes fontes de mídia, encontrar criativos relevantes e enviá-los diretamente para suas campanhas de fonte de mídia compatíveis.

<div id="about-creative-management" />

## Sobre a solução

A gestão de criativos é um hub centralizado para gerenciar assets de criativos durante todo o ciclo de vida, desde a sincronização do armazenamento até o upload das fontes de mídia.

Use a solução para:

* Sincronizar criativos do armazenamento de criativos.
* Buscar e revisar facilmente criativos em uma galeria centralizada.
* Conferir o status da atividade em todas as fontes de mídia.
* Priorizar os criativos com uma avaliação pré-lançamento orientada por IA.
* Enviar criativos diretamente para campanhas através das fontes de mídia.
* Verificar os resultados do upload e quais criativos foram enviados com sucesso ou apresentaram falhas.

Desenvolvida para escalar, a gestão de criativos ajuda as equipes de marketing e de criativos a reduzir o trabalho manual, otimizar o tempo de lançamento e aumentar a performance das campanhas.

<div id="get-started" />

## Iniciar

**Pré-requisitos**

Uma conta da AppsFlyer que assina a <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide">otimização de criativos</Anchor>. Para se inscrever, fale com o seu CSM ou envie uma mensagem para [hello@appsflyer.com](mailto:hello@appsflyer.com). Você também pode fazer um teste gratuito.

**Para começar a usá-la, siga os passos abaixo:**

<div id="sync-creatives-from-the-creative-storage" />

<Accordion title="Sincronizar criativos do armazenamento de criativos">

A gestão de criativos pode sincronizar criativos do armazenamento conectado. Depois de salvar a conexão, ela extrai criativos do armazenamento conectado e mantém a biblioteca atualizada à medida que criativos novos são adicionados.

Atualmente, a gestão de criativos é compatível com Google Drive e Dropbox. Cada fonte tem um fluxo de conexão diferente.

**As conexões de armazenamento compatíveis incluem:**

* [Google Drive](#conectar-o-google-drive)
* [Dropbox](#conectar-o-dropbox)

<div id="connect-google-drive" />

#### Conectar o Google Drive

**Para conectar uma pasta do Google Drive:**

1. Na AppsFlyer, vá para **Otimizar > Gestão de criativos**.

**<Image alt="Click Creative Management New.png" src="https://files.readme.io/c4ae98a4409b0766c9bd41e2f153d67c3d6168d31af82dadd1f43f345678878e-40988213459217.png" width="35.83%" />**

2. Clique em **Conexões de criativos**.

<Image alt="clique em Creative connection.png" src="https://files.readme.io/a1ba600e90389351dc119bb00a358d14909eb92a3fc0b8391e3efa7650992ae2-small-48939135740689.png" width="150%" />

3. Clique em **Adicionar conexões**.
4. Selecione **Google Drive**.
5. No Google Drive, permita que a AppsFlyer acesse a pasta que contém seus criativos. Para isso, compartilhe a pasta com permissões de leitura para a conta de serviço da AppsFlyer: `creative-google-account-drive@creative-prod.iam.gserviceaccount.com`.
   * A gestão de criativos sincroniza os criativos das pastas selecionadas e suas respectivas subpastas.
6. Volte à gestão de criativos e insira o URL da pasta.
7. Selecione o aplicativo correspondente. Essa etapa é opcional, mas recomendamos segui-la para organizar e combinar os criativos da maneira correta.
8. Clique em **Adicionar URL**.
9. Repita as duas etapas anteriores para conectar várias pastas de uma só vez.

<Image alt="image (49).png" src="https://files.readme.io/c29dab5dc76470b5e99e8efd8accaec7bfd1c6878f3bcfe8d58d7b650063065b-48939152741393.png" width="92.07%" />

10. Clique em **Conectar**.

<div id="connect-dropbox" />

#### Conectar o Dropbox

Antes de conectar o Dropbox, verifique se você fez login no Dropbox com a conta que tem acesso às pastas dos criativos correspondentes.

**Para conectar as pastas do Dropbox:**

1. Na AppsFlyer, vá para **Otimizar > Gestão de criativos**.
2. Clique em **Conexões de criativos**.
3. Clique em **Adicionar conexões**.
4. Selecione **Dropbox**.
5. No pop-up de login do Dropbox, conecte-se à conta do Dropbox.
6. No modal de conexão, clique em **Escolher pastas** e depois selecione as pastas que deseja conectar.
   * A gestão de criativos sincroniza os criativos das pastas selecionadas e suas respectivas subpastas.

<Image alt="clique em Choose folders.png" src="https://files.readme.io/13d62001deedecfb95a202aa54d36a1d7948d36aa76ac2a93b056be54d2ffe01-48939135745937.png" width="84.64%" />

7. Selecione o aplicativo correspondente para cada pasta. Essa etapa é opcional, mas recomendamos segui-la para organizar e combinar os criativos da maneira correta.
8. Clique em **Conectar**.

Depois de criar a conexão, a gestão de criativos começa a extrair e processar os criativos. Quando o processamento é concluído, os criativos aparecem na galeria com metadados como tipo de criativo, data de sincronização, data de lançamento, status e versões disponíveis.

</Accordion>

<div id="browse-and-select-creatives" />

<Accordion title="Explorar e selecionar criativos">

A galeria de gestão de criativos é onde você revisa, busca, filtra e seleciona os criativos.

Cada card representa um criativo. Um criativo pode incluir várias versões, como diferentes resoluções ou formatos. A partir do card, você descobre rapidamente se um criativo é novo e se está ativo ou inativo em todas as fontes de mídia. Você também consegue visualizar metadados de alto nível, como quando um criativo foi lançado pela primeira vez e quando foi sincronizado com a gestão de criativos. Cada criativo novo é automaticamente analisado e pontuado para te ajudar a escolher os melhores assets antes do lançamento. As pontuações variam de C (menos provável de sucesso) a A (maior chance de sucesso), ajudando a priorizar os criativos de melhor performance com confiança.

<Image alt="image (52).png" src="https://files.readme.io/a295ed00e01564b04bd32a7ce515cf41012a62324a8fcd350d1b4b9113e0cacb-small-48939135746577.png" width="150%" />

<div id="filter-creatives" />

#### Filtrar criativos

Use a barra de pesquisa e os filtros para encontrar os criativos relevantes por:

* **Barra de pesquisa:** busque criativos por ID ou nome.
* **App:** encontre criativos relacionados a um aplicativo específico.
* **Fonte de mídia:** encontre criativos ativos ou inativos em uma ad network específica.
* **Tipo de criativo:** filtre por imagem, vídeo ou HTML.
* **Status do criativo:** filtre por criativos novos, ativos ou inativos.
* **Pontuação do criativo:** encontre novos criativos com uma pontuação de IA específica.
* **Data de sincronização:** encontre criativos adicionados à gestão de criativos durante um período específico.
* **Data de lançamento:** encontre criativos lançados pela primeira vez durante um período específico.
* **Resolução:** encontre criativos com uma versão específica disponível.

Por padrão, os criativos são classificados por data de sincronização, assim os criativos adicionados recentemente aparecem primeiro. Você também pode classificá-los por data de lançamento ou nome do criativo.

</Accordion>

<div id="upload-creatives-to-media-sources" />

<Accordion title="Fazer upload de criativos para fontes de mídia">

Quando quiser lançar seus criativos, selecione um ou mais criativos na galeria e clique em **Fazer upload para fonte mídia**.

Atualmente, a gestão de criativos é compatível somente com envios para campanhas de promoção de aplicativos. A configuração de upload muda com base na fonte de mídia selecionada porque cada ad network tem requisitos e estruturas de destino diferentes.

Para todas as fontes de mídia compatíveis, você pode enviar criativos para vários destinos de uma só vez.

**Os canais de mídia compatíveis incluem:**

* [Google Ads](#google-ads)
* [Meta Ads](#meta-ads)
* [TikTok Ads](#tiktok-ads)
* [Mintegral](#mintegral)
* [Unity Ads](#unity-ads)
* [AppLovin](#applovin)

#### Google Ads

No caso do Google Ads, você pode enviar criativos para grupos de anúncios de promoção de aplicativos existentes.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Escolha o Google Ads.
4. Selecione os detalhes do destino: conta do Google e grupos de anúncios.
   * Você pode usar o filtro de campanha para restringir a pesquisa por grupos de anúncios específicos.
   * Não é necessário adicionar o canal do YouTube.
5. Se o upload incluir vídeos, informe se os vídeos enviados são destinados a crianças.
6. Selecione os criativos na seção **Todos os criativos** e atribua-os aos grupos de anúncios.
7. Se um criativo tiver várias versões, selecione as correspondentes.
8. Revise a configuração e todas as mensagens de validação.
9. Clique em **Fazer upload para Google Ads**.

<Image alt="clique em Fazer upload para Google Ads.png" src="https://files.readme.io/5280a1a396584e6874d8a2c24882fb9be4b25747d322fab607944da57a8fcdc9-48939152742545.png" width="100%" />

<div id="note" />

> 📘 **Atenção**
>
> Antes de enviar um lote grande pela primeira vez, recomendamos fazer um teste com um único criativo para confirmar se ele aparece corretamente na fonte de mídia.

#### Meta Ads

No caso do Meta Ads, você pode criar anúncios dentro de conjuntos de anúncios existentes.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Escolha o Meta Ads.
4. Selecione os detalhes do destino: conta do Meta Ads e conjuntos de anúncios.
   * Você pode usar o filtro de campanha para restringir a pesquisa por grupos de anúncios.
5. Crie todos os anúncios novos necessários.
   * Se tiver selecionado vários conjuntos de anúncios, cada anúncio será criado em cada conjunto de anúncios.
6. Selecione os criativos na seção **Todos os criativos** e atribua-os aos anúncios.
7. Se um criativo tiver várias versões, selecione as correspondentes.

<Image alt="Meta Ads.png" src="https://files.readme.io/56c387af74f4904921770abdee23e0d27a92e8f26c40d2d4fa46a4c42a4e2bb0-48939152743441.png" width="1838px" />

8. Revise a configuração e todas as mensagens de validação.
9. Clique em **Próximo**.
10. Configure os campos no nível do anúncio: página do Facebook, perfil do Instagram, texto principal, título, CTA, status de lançamento e permissões de melhorias dos seus criativos para o Meta Ads.
    * Por padrão, essa configuração aplica-se a todos os anúncios novos criados. Você pode editar anúncios específicos ao escolhê-los na lista suspensa **Personalizar um anúncio específico**.
11. Clique em **Criar anúncios no Meta**.

<Image alt="image (55).png" src="https://files.readme.io/95125f551e731428a8d18a7ba1162246a867cdff4e0d34aee3950e08446c5eeb-48939152744209.png" width="1840px" />

#### TikTok Ads

No caso do TikTok Ads, você pode enviar criativos para anúncios de promoção de aplicativos existentes.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Escolha o TikTok.
4. Selecione os detalhes do destino: conta do TikTok Ads e anúncios.
   * Você pode usar os filtros de campanha e grupo de anúncios para restringir a pesquisa por anúncios específicos.
   * Não é necessário adicionar o canal do YouTube.
5. Selecione os criativos na seção **Todos os criativos** e atribua-os aos anúncios.
6. Se um criativo tiver várias versões, selecione as correspondentes.
7. Revise a configuração e todas as mensagens de validação.
8. Clique em **Fazer upload para TikTok**.

#### Unity Ads

<div id="note-1" />

> 📘 **Atenção**
>
> No caso do Unity Ads, você pode enviar criativos apenas para a biblioteca de criação do Unity. O upload direto para as campanhas será adicionado em breve.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Escolha **Unity Ads**.
4. Selecione o aplicativo ao qual os criativos serão associados e o idioma dos criativos (opcional).
5. Se um criativo tiver várias versões, selecione as correspondentes.
6. Clique em **Fazer upload para Unity Ads**.

#### Mintegral

<div id="note-2" />

> 📘 **Atenção**
>
> No caso da Mintegral, você pode enviar criativos apenas para a biblioteca de criação da Mintegral. O upload direto para as campanhas será adicionado em breve.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Escolha **Mintegral**.
4. Selecione a conta da Mintegral à qual os criativos serão associados.
5. Se um criativo tiver várias versões, selecione as correspondentes.
6. Clique em **Fazer upload para Mintegral**.

#### AppLovin

<div id="note-3" />

> 📘 **Importante!**
>
> O acesso à API de gestão de campanhas da AppLovin está disponível para anunciantes selecionados. Para solicitar acesso ou saber mais sobre a elegibilidade, entre em contato com seu representante da AppLovin.

Na AppLovin, você pode fazer upload de criativos para conjuntos de criativos existentes ou criar novos conjuntos de criativos.

1. Selecione criativos da galeria.
2. Clique em **Fazer upload para fonte de mídia**.
3. Selecione a AppLovin.
4. Escolha entre criar novos conjuntos de criativos ou fazer upload para os existentes.

**Para criar um novo conjunto de criativos:**

1. Selecione a conta da AppLovin.
2. Selecione as campanhas nas quais você quer criar o conjunto de criativos.
3. Insira um nome para o conjunto de criativos.
4. Selecione o status de lançamento.
5. Clique em **Adicionar**. Você pode criar quantos conjuntos de criativos forem necessários.
6. Selecione os criativos na seção **Todos os criativos** e atribua-os aos conjuntos de criativos.
7. Se um criativo tiver várias versões, selecione as correspondentes.
8. Revise a configuração e todas as mensagens de validação.
9. Clique em **Fazer upload para AppLovin**.

**Para fazer upload para um conjunto de criativos existente:**

1. Selecione a conta da AppLovin.
2. Selecione os conjuntos de criativos para os quais você quer fazer upload.
   * Você pode usar o filtro de campanha para restringir a pesquisa por conjuntos de criativos específicos.
3. Selecione os criativos na seção **Todos os criativos** e atribua-os aos conjuntos de criativos.
4. Se um criativo tiver várias versões, selecione as correspondentes.
5. Revise a configuração e todas as mensagens de validação.
6. Clique em **Fazer upload para AppLovin**.

</Accordion>

<div id="review-upload-results" />

<Accordion title="Revisar os resultados do upload">

Depois de iniciar um upload, a janela de upload se fecha automaticamente e a gestão de criativos continua o processo em segundo plano enquanto você trabalha.

Para revisar os resultados do upload, clique em **Histórico de uploads** na galeria da gestão de criativos.

O histórico de uploads mostra os trabalhos de upload anteriores e seus resultados, incluindo:

* Fonte de mídia e destino.
* Status do upload: concluído, concluído parcialmente ou falha no upload.
* Número de criativos enviados a partir do total selecionado.
* Horário de conclusão do upload.
* Detalhes dos criativos que falharam.

Se um upload for parcialmente concluído ou falhar, a gestão de criativos indicará no histórico de uploads para que você possa analisar o problema. Nos detalhes, os criativos que falharam aparecem com o motivo da falha.

</Accordion>

<div id="creative-activity-status" />

<Accordion title="Status da atividade">

O status dos criativos ajuda você a entender onde um criativo é utilizado nas suas fontes de mídia conectadas.

Na galeria, cada criativo pode exibir:

* **Novo:** o criativo ainda não foi lançado.
* **Ativo:** o criativo está em execução no momento.
* **Inativo:** o criativo estava ativo antes, mas não está em execução no momento.

A gestão de criativos também ajuda você a descobrir onde os seus criativos ativos estão em execução no momento. Clique em um card para abrir o painel, onde você pode ver exatamente em quais campanhas e grupos de anúncios o criativo está ativo.

Use as informações sobre o status para responder a perguntas como:

* Quais criativos novos devo enviar a seguir?
* Quais criativos estão ativos em uma fonte de mídia e podem ser testados em outra?
* Quais criativos já foram testados e podem valer a pena relançar?
* Quais criativos estão ativos em uma campanha de teste e devem ser enviados para mais campanhas?

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Descrição |
| --- | --- |
| Escopo da campanha | Atualmente, a gestão de criativos é compatível somente com campanhas de promoção de aplicativos. |
| Fontes de armazenamento compatíveis | Atualmente, a sincronização de repositório é compatível com Google Drive e Dropbox. |
| Os destinos de upload variam de acordo com a ad network | Os destinos de upload compatíveis e os campos obrigatórios variam de acordo com a fonte de mídia. |
| O método de upload varia de acordo com a ad network | O método de upload varia de acordo com a ad network.  <br />O Google Ads, o Meta Ads e o TikTok são compatíveis com o envio direto para campanhas (como anúncios ou conjuntos de criativos); atualmente, o Unity Ads e a Mintegral são compatíveis apenas com o envio para suas bibliotecas de criação. |
| Requisitos de assets | Os formatos, as dimensões, a duração e o tamanho dos assets de criativos devem atender aos requisitos de cada ad network. |
| Escopo do histórico de uploads | O histórico de uploads reflete o resultado dos uploads, não o status atual da veiculação ou moderação de um criativo. |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide">Guia para a otimização de criativos</Anchor>

<div data-zendesk-anchors="about-creative-management=sobre-a-solu%C3%A7%C3%A3o get-started=iniciar h_01KXDN2V1R9SRPFSRGZZ4ZA62S=sync-creatives-from-the-creative-storage connect-google-drive=conectar-o-google-drive h_01KXDN2V1RGCDYJ074FV4KJY8T=conectar-o-google-drive connect-dropbox=conectar-o-dropbox h_01KXDN2V1R75971RE5ECTDM8TM=conectar-o-dropbox h_01KXDN2V1RAA882M55HK9152D6=browse-and-select-creatives filter-creatives=filtrar-criativos h_01KXDN2V1RHJJZC67ZM84TNT0Y=filtrar-criativos h_01KXDN2V1R8CXZ4XGTX656XRWF=upload-creatives-to-media-sources h_01KXDN2V1RE8748NWSCJP824PD=google-ads h_01KXDN2V1R31MABH1A3G0T9B84=aten%C3%A7%C3%A3o h_01KXDN2V1RG25RR7BXYAFVEAT7=meta-ads h_01KXDN2V1RBANB482286YP1QSY=tiktok-ads h_01KXDN2V1R52Y91AZNVGPPWW44=unity-ads h_01KXDN2V1RF9TZ25DFYQ91RVRC=aten%C3%A7%C3%A3o-1 h_01KXDN2V1REED32CRW83W7MMC9=mintegral h_01KXDN2V1SVWASV4KGJJ2VC162=aten%C3%A7%C3%A3o-2 h_01KXDN2V1RSFB2GHDPN95S90EJ=applovin h_01M1H2RMVW2CYMV7KBBSHJ9686=importante h_01KXDN2V1S8NZP8F4QN51NS3XP=review-upload-results h_01KXDN2V1SC0PHRY810NJG6QY3=creative-activity-status traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KXDN2V1SDNR1Z5FTKEJNDZF3=veja-tamb%C3%A9m" />
