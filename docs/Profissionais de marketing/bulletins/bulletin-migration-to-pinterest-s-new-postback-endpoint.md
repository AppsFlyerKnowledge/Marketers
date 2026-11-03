---
title: 'Novidade: migração para o novo endpoint de postbacks do Pinterest'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-10-20T03:54:39Z'
  id: 37418019002641
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/37418019002641
---

<Table>
  <thead>
    <tr>
      <th>
        Seção
      </th>
      <th>
        Detalhes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        O Pinterest migrou para um novo endpoint baseado na infraestrutura de Conversions API (CAPI). Assim, você deve fazer a atualização para continuar enviando eventos do seu aplicativo para o Pinterest. Vamos desativar o endpoint antigo em 30 de setembro de 2025.
      </td>
    </tr>
    <tr>
      <td>
        **Data de início**
      </td>
      <td>
        07/23/2025
      </td>
    </tr>
    <tr>
      <td>
        **O que você precisa saber**
      </td>
      <td>
        Este boletim inclui informações relacionadas à fase de migração para a CAPI. Para informações gerais sobre a integração do Pinterest, veja <Anchor target="_blank" href="/marketers/pt/docs/pinterest-create-a-mobile-app-integration#configurações-de-eventos-in-app">esse artigo</Anchor>.

        Essa atualização garantirá que a mensuração do Pinterest não seja interrompida. Além disso, ela inclui:

        * **Mais tipos de “eventos”**: acompanhe eventos adicionais de acordo com os seus objetivos, como eventos de Lead, Search, Category Viewed, Page Visit, User-defined e mais.
          * **Atenção**: os nomes dos eventos são diferentes no endpoint da versão 5. Se o dashboard não for atualizado seguindo as novas nomenclaturas, o relatório de eventos mostrará a mensagem "desconhecido". Revise as novas nomenclaturas de eventos abaixo.
        * **Melhoria na qualidade dos dados:** Aproveite uma correspondência melhorada e uma atribuição mais precisa.

        A nova integração requer tanto um **Ad Account ID** quanto um **Access Token**. Para manter a funcionalidade de postbacks, os parceiros devem fazer a transição para o novo endpoint até 30/09/25.   

        **Como encontrar o Ad Account ID da AppsFlyer no Pinterest**  
        Você pode encontrar o Ad Account ID para o relatório de conversões da AppsFlyer no **Business Manager** ou no relatório **Conversions** do Pinterest.

        1. Faça login na sua conta comercial do Pinterest (você deve ter um perfil comercial para ver as opções do hub).
        2. Digite ou cole https://www.pinterest.com/business/hub/ no seu navegador e pressione enter.
        3. Olhe para a coluna cinza-escura no lado esquerdo do hub. Se a coluna estiver recolhida, clique no ícone “≡” no canto superior esquerdo para expandi-la.
        4. Procure por "Manage business”.
        5. Clique em Conversions (logo abaixo de “manage business”). No dashboard de Conversions, você pode revisar as conversões que a AppsFlyer enviou para o Pinterest.
        6. Você encontra o Ad Account ID na URL.
        7. Se vários Ad Account IDs receberem conversões clonadas da AppsFlyer, verifique todos os Ad Account IDs disponíveis em Conversions no Business Manager do Pinterest. Certifique-se de que o Ad Account ID original seja selecionado para conversões da AppsFlyer.

        **Como encontrar o token de acesso da AppsFlyer no Pinterest**  
        Siga os passos descritos no Centro de Ajuda do Pinterest <Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">aqui</Anchor>. Em Conversions, no Pinterest, clique em **Conversions API** > **Set-up API**, e gere um novo token de acesso para a conta.  

        **Observação importante:** Se você já configurou a Conversions API para o Pinterest separadamente, fora da AppsFlyer, use o mesmo token de acesso para as conversões da AppsFlyer.
      </td>
    </tr>
    <tr>
      <td>
        **O que você precisa fazer**
      </td>
      <td>
        Siga as instruções abaixo para configurar e migrar postbacks de eventos in-app no dashboard da AppsFlyer.

        1. **Configurações de eventos in-app e parâmetros do dashboard**  
           Atualmente, oferecemos os seguintes parâmetros do dashboard para o mapeamento dos seus eventos da AppsFlyer com o Pinterest:

           * **Ad Account ID** (visível)
           * **Access Token** (visível)
           * **Tag ID** (não visível no dashboard, mas disponível no backend para ajudar com a transição para a versão 5. Quando a transição para o endpoint V5 for completada, o Tag ID também será removido do backend).

           **Atenção:**  
           Para a nova configuração de postbacks, você deve inserir tanto o **Ad Account ID** quanto o **Access Token** (que podem ser acessados no Pinterest, se ainda não estiverem disponíveis). **Se algum desses valores estiver faltando, o postback falhará**. Por favor, certifique-se de que ambos os parâmetros estejam preenchidos corretamente na página de **Active Integration** do Pinterest. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/pinterest-create-a-mobile-app-integration#configurações-de-eventos-in-app">esse artigo</Anchor>.  
           Sua cooperação é importante para garantir uma transição rápida e fácil. Agradecemos o seu apoio.
        2. **Mapeamento de eventos in-app e configurações de postbacks**
           1. Substitua e mapeie os nomes dos eventos atuais do Pinterest usando os novos nomes de eventos da Conversion API na seção **Partner event name**. Por exemplo, se você estiver usando `pin_add_to_cart` na seção de eventos do parceiro, substitua por `add_to_cart`. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/pinterest-create-a-mobile-app-integration#aba-permissões">esse artigo</Anchor>.

        | Nome do evento (legado) | Nome do evento (nova Conversions API) |
        | --- | --- |
        | pin\_add\_to\_cart | adicionar\_ao\_carrinho |
        | pin\_purchase | checkout |
        | pin\_search | search |
        | pin\_registration | signup |
        | pin\_sign\_up | signup |
        | pin\_category\_view | view\_category |
        | add\_cart | adicionar\_ao\_carrinho |
        | start\_checkout | checkout |
        | content\_view | view\_category |

              **Atenção:** se você não atualizar os nomes legados com os nomes corretos para a Conversion API, você verá a mensagem "Other" no lugar dos nomes dos eventos no Pinterest, e não terá visibilidade sobre os eventos certos.
           2. Selecione **in-app event postback window** em **Lifetime** para que o Pinterest possa receber o maior número possível de conversões para otimização de anúncios.
           3. Selecione **All media sources including organic** em **To users from** para que o Pinterest possa receber o maior número possível de conversões para otimização de anúncios. Para mais informações, acesse <Anchor target="_blank" href="/marketers/pt/docs/pinterest-create-a-mobile-app-integration#aba-permissões">esse artigo</Anchor>.
        3. **Processo de reversão em caso de problemas**  
           Recomendamos que você acompanhe as conversões de aplicativos da AppsFlyer no Pinterest para detectar quaisquer problemas de migração. Espere até 30 minutos para que os dados de conversões da AppsFlyer apareçam no Pinterest e faça um monitoramento regular por alguns dias para validar o sucesso da migração.  

           Você pode reverter para o endpoint legado omitindo um ou ambos os `account_id` e `access_token` na configuração da integração. 

           **Regras de comportamento:**

           * Tanto `account_id` quanto `access_token` estão ausentes → postbacks são enviados para o endpoint legado (antigo).
           * Apenas `account_id` é fornecido (ou seja, `access_token` está vazio) → postbacks são enviados para o endpoint legado.
           * Apenas `access_token` é fornecido (ou seja, `account_id` está vazio) → postbacks são enviados para o endpoint legado.
           * Tanto `account_id` quanto `access_token` são fornecidos → postbacks são enviados para o novo endpoint.

           Se você estiver enfrentando algum problema, entre em contato com o suporte da AppsFlyer através do support@appsflyer.com. Se identificar algum problema no Pinterest, entre em contato com api-support@pinterest.com ou com seu representante do Pinterest.
      </td>
    </tr>
  </tbody>
</Table>
