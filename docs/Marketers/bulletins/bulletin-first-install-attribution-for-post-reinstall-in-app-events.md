---
title: >-
  Boletín: atribución de primera instalación para eventos in-app posteriores a
  la reinstalación
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-05T15:04:01Z'
  edited_at: '2026-10-20T03:55:32Z'
  id: 25676426941457
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/25676426941457
---
| **¿Qué hay de nuevo?** | Esta mejora atribuye todos los <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#eventos-in-app">eventos in-app</Anchor> y las sesiones posteriores a un re-engagements o una <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#reattribution">re-attribution</Anchor> a la fuente de medios original que lo impulsó («primera instalación») en lugar de etiquetarlos como «orgánicos sin atribuir».<br /><br />![Screenshot 2024-06-11 at 8.44.30.png](https://files.readme.io/42a96ec533d217ee4dadad71592023d1fd0c977557308638f3553660a95fc7b5-25827620446353.png) |
| --- | --- |
| **Fecha de entrada en vigor** | 31 de julio de 2024. El modo de primera instalación se aplica automáticamente solo a las aplicaciones añadidas a AppsFlyer en/o después de la fecha de vigencia. Para las aplicaciones añadidas antes del 31 de julio de 2024, recomendamos contactar a AppsFlyer para migrar sus aplicaciones existentes al modo de primera instalación. |
| **Prerrequisitos** | None |
| **Acciones requeridas** | None |
| **¿Qué debo saber?** | Solo los usuarios que hayan dado su consentimiento para compartir su identificador de dispositivo (como el IDFA o GAID) con la aplicación, tanto para la instalación como para la reinstalación, tendrán sus eventos in-app atribuidos a la instalación original. De lo contrario, serán etiquetados como "orgánicos sin atribuir". |
| **¿Cuál es el impacto?** | <ul><li>Para las aplicaciones añadidas a AppsFlyer **después del 31 de julio de 2024**: sin impacto</li><li>Para las aplicaciones añadidas **antes del 31 de julio de 2024**, te recomendamos ponerte en contacto con AppsFlyer para migrar tus aplicaciones existentes al modo de primera instalación. Después de la migración, puede ocurrir lo siguiente:<ul><li>Un aumento potencial en la cantidad de eventos in-app y sesiones que se atribuyen a la primera instalación después de una reinstalación, junto con una disminución correspondiente en las atribuciones clasificadas como "orgánicas" para dichos eventos.</li><li>Un posible aumento en el recuento de MAU (usuarios activos mensuales) para las fuentes de medios atribuidas originalmente y una disminución en el recuento de MAU para las fuentes orgánicas.</li><li>El día en que la aplicación cambie al modo de primera instalación, el conteo de sesiones se duplica. Como resultado, la tasa de retención del día 1 para la cohorte es inusualmente alta.</li></ul></li></ul> |