---
title: SKAN conversion schema templates
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-10-06T09:58:43Z'
  edited_at: '2026-10-13T01:27:55Z'
  id: 28968432692241
  locale: zh-cn
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/zh-cn/articles/28968432692241
---
> **At a glance:** SKAN conversion schema templates are ready-to-use templates. Simplifying the SKAN setup by offering templates based on a combination of industry and specific app data, offering industry insights and best practices. SKAN conversion schema templates can be found in the Conversion Studio.

## Key benefits

* These templates streamline the SKAN set up by enabling the creation of a conversion schema in just a few clicks.
* By utilizing industry best practices and insights, marketers can refine their schema and increase confidence in its effectiveness by using templates based on industry data combined with app-specific data.

## How to get started

1. From the left-hand menu, Go to **Settings > SKAN Conversion Studio**
2. Click the **Industry templates** button
3. The template window will open
4. Select from the list of industries and verticals on the left-hand side
5. The right-hand side of the screen displays how the suggested conversion schema looks
   1. Use the **SKAN 4 mode** toggle to turn on or off SKAN 4 support  
      **Note:** With SKAN 4, three activity windows are suggested, along with coarse conversion values for the first window. With it off, only fine conversion values for the first window are suggested.
   2. Use the ? icons next to each measurement to see an explanation of why that event or measurement was suggested, along with benchmark information
6. Click **Select & customize**  
   **Note:** This will not save your settings yet
7. You will be redirected to the **Conversion Studio** edit page
   1. Use the Conversion Studio’s <Anchor target="_blank" href="/marketers/zh/docs/skan-conversion-studio#衡量维度">standard features and tools</Anchor> to customize the template according to your app’s needs

## What Are SKAN conversion schema templates?

SKAN conversion templates suggest mappings of conversion values for meaningful user post-install activities, tailored by industry and vertical. The suggestions can be customized to fit specific app needs, combining data-driven insights and industry expertise.

### Template structure

* **Strategy**: This defines whether to focus on in-app events, revenue measurement, or a combination of both. The strategy is pre-defined but can be customized in the Conversion Studio edit page.
* **SKAN Version**: Indicates which version of SKAN is supported, either SKAN4 or earlier versions. By default, SKAN 4 is supported. If SKAN 4 is turned off, coarse conversion value measurements are disabled, and the Conversion Studio switches to "custom" mode.
* **Measurements**: The template suggests specific post-install activities to measure. This includes specific events or revenue ranges, as well as the use of features like Funnel and Single Source of Truth (SSOT), which is suggested by default.
  * The suggested measurements can be customized in the Conversion Studio edit page.
  * Pre-selected events are tailored for each template.
  * Revenue ranges are customized based on app-specific data using advanced revenue recommendation models  When there isn't enough historical data, industry data is used to make suggestions.

## What is SKAN conversion schema?

The SKAN conversion schema defines the measurement setup for the SKAdNetwork (SKAN) framework. It specifies which user engagement metrics (e.g., in-app events or revenue) will be measured and reported. SKAdNetwork does not directly report post-install engagement with the app. Instead, it reports "Conversion Values" which are mapped by the app developer to meaningful post-install activities. This mapping is known as the SKAN conversion schema.

## What are these templates based on?

The templates are based on a data-driven analysis of conversion schemas by vertical, along with qualitative research and insights from industry experts. Some of the suggestions are based on app-specific data, as outlined below.  
The key steps of the template creation process:

1. **Sampled leading apps**: We identified sample apps for quantitative analysis. Using internal and external datasets, we classified apps into vertical hierarchies. For each sub-vertical, we analyzed dozens of leading apps and ranked them by the volume of SKAN traffic they generated.
2. **Defined the strategy**: Based on industry benchmark data, we established a standardized strategy tailored to each vertical. After analyzing the percentage of apps in each vertical that measure events, revenue, or both, we selected a strategy for each vertical. We also considered the average event count and the volume of apps utilizing the funnel feature to determine the number of events per template and whether a funnel is appropriate.
3. **Created collective event groups**: We mapped the various event names, as defined by apps, into pre-defined groups, with each group reflecting a collection of similar business events.
4. **Suggested events**: We identified the most recommended business events to measure within each vertical. Using the event groups created in the previous step, we analyzed the percentage of apps measuring each event. After review by industry experts and validation against dozens of conversion schemas from leading apps, we selected the best combination of events for each sub-vertical.
5. **Defined revenue ranges**: We suggested the best revenue ranges to maximize the accuracy of reported revenue. When a user opens the template dialog, we check in real-time whether the app is eligible for revenue recommendations based on our advanced models. If so, the model creates custom revenue ranges using the app’s data. If not, we suggest revenue ranges based on industry data derived from applying our revenue recommendation models to the data of leading apps in the vertical.
6. **Mapped app-specific events**: After the app applies a specific template, we match the relevant in-app events to the predetermined business event names within the vertical’s template. The app should then verify that the correct events have been selected.

<div data-zendesk-anchors="intro=key-benefits h_01J9GM9NV7HDA1N9WZH4Y6K1VH=key-benefits h_01J9GME5K3C0BMPVK6K1D46HT0=how-to-get-started h_01J9GMP733JQSY60AJH22FGPRS=what-are-skan-conversion-schema-templates h_01J9GMPACY2TY0MYNEEJNW39Z5=template-structure h_01J9GMQX4R8BMSQQ3XW4C97VEJ=what-is-skan-conversion-schema h_01J9GMR0FTV2Q75N9N5FQZW98F=what-are-these-templates-based-on" />
