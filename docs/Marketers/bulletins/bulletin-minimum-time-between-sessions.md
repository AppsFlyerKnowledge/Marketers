---
title: 'Boletín: Tiempo mínimo entre sesiones'
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
  edited_at: '2026-10-20T03:57:01Z'
  id: 360016827858
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360016827858
---

<Table>
  <tbody>
    <tr>
      <td>
        **¿Qué hay de nuevo?**
      </td>
      <td>
        Cambio en el cálculo de la métrica de sesiones
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        15 de febrero de 2021
      </td>
    </tr>
    <tr>
      <td>
        **Qué ha cambiado**

        **![Information_icon.png](https://files.readme.io/2fc0f0d0337ac9902e20f69605e25331e17a370008c72ae52a79e09d916dba21-360015660197.png)**
      </td>
      <td>
        La métrica de sesiones se calcula contando las sesiones que reporta el SDK en la aplicación.

        A partir de la Fecha de entrada en vigor, después de las primeras 5 sesiones, la métrica de sesiones se calcula teniendo en cuenta un temporizador de tiempo mínimo entre sesiones. Esto significa que algunas sesiones no se contabilizan, como se muestra en el ejemplo siguiente. 

        El temporizador tiene una duración predeterminada de 10 minutos y los valores posibles son: 

        * 1-60 minutos
        * 1-24 horas

        ![MinimumTimeBetweenSessions_us-en.jpg](https://files.readme.io/12bc7191a11dda474f57055a6cf5ce6bb69b3772ad33a2a0c7bfabc51e4c07ce-360015918477.jpg)

        **Ejemplo: recuento de sesiones con un tiempo mínimo entre sesiones de 10 minutos.**

        En este ejemplo, las horas de reporte de las sesiones se indican como minutos transcurridos desde las 00:00

        | Ejemplo | Horas de reporte de las sesiones | Número de sesiones contabilizadas | Sesiones ignoradas |
        | --- | --- | --- | --- |
        | A | 0, 10, 20, 30 | 4 | None |
        | B | 0, 1, 9, 11 | 2 | 1, 9 |
        | C | 0, 10, 15, 21 | 3 | 15 |

        **Impacto del cambio**

        * Espera una reducción de la métrica de sesiones a partir de la Fecha de entrada en vigor en las herramientas de Analytics y en los raw data de sesiones disponibles para los clientes que tienen Data Locker.
        * Partners de ad network: si consumes el evento de sesión a través de postback, espera una reducción debido a este cambio.
      </td>
    </tr>
    <tr>
      <td>
        **Qué sigue igual**
      </td>
      <td>
        La implementación de este cambio (con la configuración predeterminada de 10 minutos) no afectará a ninguna de las siguientes métricas:

        * Métricas:
          * DAU (Daily active users)
          * Usuarios activos mensuales (MAU)
          * Retencion
          * Usuarios fieles que usan la configuración predeterminada de 3 aperturas de la aplicación
        * Conversiones de re-engagement
        * Datos históricos (sesiones) registrados antes de la Fecha de entrada en vigor

        Sin embargo, de ahora en adelante ten en cuenta que, si el tiempo mínimo entre sesiones se aumenta a más de una hora y los usuarios no abren la aplicación muchas veces al día, algunas métricas de retención pueden verse afectadas. Esto es especialmente cierto en el caso de las aplicaciones en las que los usuarios suelen abrir la aplicación una vez al día.
      </td>
    </tr>
    <tr>
      <td>
        **[Opcional] Cambio de configuración**

        **![Action_icon.png](https://files.readme.io/f6066b9dee413eea63c6a0bf04b627e3cef6a6fb21a6ca23634e615d3be1950d-360015730138.png)**
      </td>
      <td>
        Si lo necesitas, puedes cambiar la configuración predeterminada de 10 minutos por otra que se adapte al comportamiento de tus usuarios y a su forma de interactuar con la aplicación.

        **Para cambiar la duración del tiempo mínimo entre sesiones:**

        1. En AppsFlyer. ve a **Configuración** > **Configuración de la app**.
        2. Configura el **tiempo mínimo entre sesiones.**
        3. Haz clic en **Guardar configuración.**   
           El cambio entra en vigor en el transcurso de una hora.
      </td>
    </tr>
  </tbody>
</Table>
