---
title: 'Boletim: Tempo mínimo entre sessões'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
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
    - Ad Networks
  created_at: '2021-01-03T11:28:55Z'
  edited_at: '2026-10-20T03:57:05Z'
  id: 360016827858
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/360016827858
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        Mudança no cálculo da métrica de sessões
      </td>
    </tr>
    <tr>
      <td>
        **Data de início**
      </td>
      <td>
        15 de fevereiro de 2021
      </td>
    </tr>
    <tr>
      <td>
        **O que vai mudar?**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        A métrica de sessões é calculada contando as sessões reportadas pelo SDK no aplicativo.

        A partir da Data de Vigência, após as 5 primeiras sessões, a métrica de sessões é calculada levando em conta um temporizador de tempo mínimo entre sessões. Isso significa que algumas sessões não são contadas, como ilustrado no exemplo a seguir. 

        O temporizador tem duração padrão de 10 minutos, e os valores possíveis são: 

        * 1-60 Minutos
        * 1 a 24 horas

        ![MinimumTimeBetweenSessions_us-en.jpg](https://files.readme.io/12bc7191a11dda474f57055a6cf5ce6bb69b3772ad33a2a0c7bfabc51e4c07ce-360015918477.jpg)

        **Exemplo: contagem de sessões com tempo mínimo entre sessões de 10 minutos.**

        Neste exemplo, os horários de reportar as sessões são indicados como os minutos decorridos desde 00:00

        | Exemplo | Horários de reportar as sessões | Número de sessões contadas | Sessões ignoradas |
        | --- | --- | --- | --- |
        | E | 0, 10, 20, 30 | 4 | Nenhuma. |
        | B | 0, 1, 9, 11 | 2 | 1, 9 |
        | C | 0, 10, 15, 21 | 3 | 15 |

        **Impacto da mudança**

        * Espere uma redução na métrica de sessões a partir da Data de Vigência nas ferramentas de Analytics e nos dados brutos de sessões disponíveis para clientes que têm Data Locker.
        * Parceiros de ad network: se você consome o evento de sessão via postbacks, espere uma redução devido a essa mudança.
      </td>
    </tr>
    <tr>
      <td>
        **O que se mantém igual**
      </td>
      <td>
        A implementação dessa mudança (usando a configuração padrão de 10 minutos) não afetará nenhuma das métricas a seguir:

        * Métricas:
          * Usuários diariamente ativos (DAU)
          * Usuários ativos mensais (MAU)
          * Retenção
          * Usuários fidelizados que usam a configuração padrão de 3 aberturas do aplicativo
        * Conversões de reengajamento
        * Dados históricos (sessões) registrados antes da Data de Vigência

        No entanto, daqui para frente, considere que, se o tempo mínimo entre sessões aumentar para mais de uma hora, e os usuários não abrirem o aplicativo muitas vezes por dia, algumas métricas de retenção poderão ser impactadas. Isto é especialmente verdadeiro no caso dos apps em que os usuários abrem o app normalmente uma vez por dia.
      </td>
    </tr>
    <tr>
      <td>
        **[Opcional] Alteração de configuração**

        **![Action_icon.png](https://files.readme.io/f6066b9dee413eea63c6a0bf04b627e3cef6a6fb21a6ca23634e615d3be1950d-360015730138.png)**
      </td>
      <td>
        Se necessário, você pode alterar a configuração padrão de 10 minutos para outra que se adapte ao comportamento e ao estilo de interação dos seus usuários com o aplicativo.

        **Para alterar a duração do tempo mínimo entre sessões:**

        1. Na AppsFlyer. vá para **Configuração** > **Configurações do aplicativo**.
        2. Definir o **Tempo mínimo entre sessões.**
        3. Clique em **Salvar configurações**.   
           A alteração entra em vigor no prazo de uma hora.
      </td>
    </tr>
  </tbody>
</Table>
