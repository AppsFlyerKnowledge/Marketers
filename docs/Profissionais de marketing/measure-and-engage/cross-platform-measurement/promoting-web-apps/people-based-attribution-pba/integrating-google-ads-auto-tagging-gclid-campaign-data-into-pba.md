---
title: >-
  Integração de dados de campanha da codificação automática (gclid) do Google
  Ads ao PBA
metadata:
  keywords:
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-08-02T05:47:05Z'
  edited_at: '2026-08-18T00:23:37Z'
  id: 360011487937
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360011487937
---
> **Em resumo:** Enriqueça os dados do PBA com informações de campanha do gclid de codificação automática ao se conectar ao Google Ads.

![](https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png)

## Como integrar dados de campanha do Google Ads ao PBA

Conecte sua conta do Google Ads (1 ou mais) ao seu pacote de marcas. Os dados de campanha do Google Ads melhoram os recursos analíticos do dashboard e enriquecem ainda mais os relatórios de dados brutos.

* Se o **gclid** estiver presente em uma URL de visita na web, o PBA obtém os seguintes dados do Google usando o GCLID. Nota! A solução GCLID não é oficialmente suportada pelo Google Ads, que poderá descontinuar o parâmetro no futuro.
* A integração enriquece os seguintes campos. A disponibilidade dos campos depende do dashboard do PBA e dos Relatórios de dados brutos.
  * Nome da campanha e ID de campanha
  * Nome do conjunto de anúncios e ID do conjunto de anúncios
  * Nome do grupo de anúncios e ID do grupo de anúncios
* Os dados fornecidos pela integração têm prioridade e substituem os dados do nome da campanha extraídos dos campos UTM. A campanha e o ID da campanha estão disponíveis nos relatórios de dados brutos.
* Se você tiver várias contas do Google Ads, conecte as contas que executam campanhas que direcionam tráfego ao seu site.

**Dashboard de Atribuição do site com hierarquia de campanha preenchida**

![PBAWebSite.png](https://files.readme.io/46004298b827d3f4eaa4adae9fb2a8676867e6b5dde44a7ff087fe1bda07f054-4403138621713.png)

Os dados de hierarquia de campanha e anúncios estão disponíveis nos dashboards e nos dados brutos da seguinte forma:

* **Painéis**
  * **Atribuição do site:** Níveis compatíveis: campanha > conjunto de anúncios > anúncio.
  * **Instalações assistidas pela web:** nível de campanha
* **Dados brutos:**
  * **Web-to-app:** web\_googleads\_campaign\_id, web\_googleads\_campaign\_name

**Para se conectar ao Google Ads:**

1. Na AppsFlyer, no menu lateral, selecione **Configurações**> **Pacotes de marcas**
2. Acesse a aba **Integração do Google Ads**.
3. Clique em **Conectar conta.** Abre-se a página de login do Google Ads.
4. Faça login na sua conta do Google Ads. Conclua o processo para conceder à AppsFlyer acesso.

**Gerenciar conexões do Google Ads**

Na página de integração do Google Ads, as seguintes ações estão disponíveis:

* Excluir conexão
* Ativar/desativar a conexão

### Mensagens de status do PBA — Google Ads

| Estado | Significado | Observações/ação necessária |
| --- | --- | --- |
| Ativa | A conexão está em ativa e extraindo dados | N/D |
| Inativos | A conexão foi desativada manualmente | Ative a conexão para voltar a extrair dados |
| Nunca sincronizado | A configuração está completa | A configuração está completa. A AppsFlyer pode levar até 24 horas para obter dados do Google Ads pela primeira vez. Se esta mensagem persistir por mais de 24 horas, entre em contato com o suporte da AppsFlyer. |
| Sem dados | A conexão foi bem sucedida | O Google Ads não retornou nenhum dado para nossa consulta. Verifique se todas as contas relevantes do Google Ads estão conectadas ao PBA. |
| Sem resposta | Não conseguimos entrar em contato com os servidores do Google Ads | No momento, não conseguimos nos conectar aos servidores do Google Ads. Se este status persistir por mais de 24 horas, entre em contato com o suporte da AppsFlyer. |
| Credenciais inválidas | A AppsFlyer não pode obter os dados, pois as credenciais não são válidas. | Verifique se as credenciais corretas estão definidas na página de integração do Google Ads. Tente se conectar novamente usando as credenciais mais recentes. Se o problema persistir, entre em contato com o suporte da AppsFlyer: support@appsflyer.com |
| Erro geral |  | Se este status persistir por mais de 24 horas, entre em contato com o suporte da AppsFlyer |

<div data-zendesk-anchors="integrating-google-ads-campaign-data-in-pba=como-integrar-dados-de-campanha-do-google-ads-ao-pba h_01HKW2V24JE5V959999TJDR2RX=como-integrar-dados-de-campanha-do-google-ads-ao-pba pba%E2%80%94google-ads-status-messages=mensagens-de-status-do-pba--google-ads h_01HKW2V24KM85CCC2F0CZHY359=mensagens-de-status-do-pba--google-ads" />
