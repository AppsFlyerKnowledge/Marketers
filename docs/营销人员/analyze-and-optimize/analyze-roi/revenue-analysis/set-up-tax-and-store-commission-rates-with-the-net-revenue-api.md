---
title: 使用Tax API调整净收入的衡量
metadata:
  keywords:
    - Revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-10-14T10:15:39Z'
  id: 30468586765841
  locale: zh-cn
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/zh-cn/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

## 净收入和税费衡量

净收入衡量是AppsFlyer ROI360应用内购买和订阅收入解决方案中的一层业务逻辑。AppsFlyer会按照这层逻辑对接收到的每一笔交易信息实时自动计算净收入值，并将这些数据纳入报告中。

**ROI360对于其衡量范围内的所有交易都会按默认税率上报税费数据。**

您可以使用这个税费专用的API**更改**税率配置。

如需进一步了解净收入衡量逻辑，请参考此处说明。

## 使用Tax API修改税率

**前期准备** ：您必须完成 ROI360 应用内购买和订阅收入测量设置 的第 1-2 步。

**如需使用该tax API修改税费配置，请按以下方式操作**：

1. 请向您的开发人员提供以下信息：
   * <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">API V2 token</Anchor>，作为授权密钥（authorization key）。
   * 相关参数和参数值，其中包含需要计算的税费信息，详见下表。
2. 让您的开发人员按照<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-tax-rate-rule">Tax API说明</Anchor>，创建税率计算规则。**请注意**：使用该API时，可以在Post请求体中传递JSON文件。请参考<Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">此处的JSON文件示例</Anchor>，其中包含所有适用的国家/地区及其默认税率。开发人员可以在示例文件的基础上进行修改，或直接按原样在API中使用该文件。

#### 可在该API中使用的参数和参数值

| 参数 | 是否必须配置 | 说明 | 参数值（开发人员记录用） |
| --- | --- | --- | --- |
| tax\_name | 是 | <ul><li>费用清单中用于表述具体税费类型的税费名称。</li><li>举例来说，销售税、增值税（VAT）、商品及服务税（GST）</li></ul> |  |
| tax\_rate | 是 | <ul><li>参数值必须大于0。</li><li>精确到小数点后4位的数字，代表税率百分点。</li><li>示例：7.25</li></ul> |  |
| tax\_exclusive | 否 | <ul><li>布尔型参数，仅有true或false两种值。</li><li>参数值为false时，表示总收入中包含税费。</li><li>参数值为true时，表示总收入中不包含税费，需要另行添加。比如在美国和加拿大等地区，零售价中不包含营业税，这时就需要用到这个参数。</li><li>默认为false。</li></ul> |  |
| country | 否 | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">由两个字符组成的ISO国家代码</Anchor>，用于说明收取税费的国家。</li><li>比如CA</li><li>请注意：英国的代码是UK而不是GB。</li></ul> |  |
| subdivision | 否 | <ul><li>部分国家可能需要区分州/细分区划。</li><li>这里使用<Anchor target="_blank" href="https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm">ISO 3166-2中的细分区划代码</Anchor>。</li><li>同时包含国家代码和细分区划代码。</li><li>示例：US-CA</li></ul> |  |
| postal\_code | 否 | <ul><li>由字母和/或数字组成的字符串，表示邮政编码</li><li>比如L4J8E3</li></ul> |  |
| deduction\_order | 否 | <ul><li>枚举型参数值，可以使用0、1或2中的任何一个值：<ul><li>0值表示首先从总收入中扣除商店抽成，然后从剩余金额中扣除税费。</li><li>0值表示首先从总收入中扣除商店抽成，然后从剩余金额中扣除税费。</li><li>2值表示同时从总收入中同时扣除税费和商店抽成。</li></ul></li></ul> |  |

<div data-zendesk-anchors="about-true-revenue-and-tax-measurements=%E5%87%80%E6%94%B6%E5%85%A5%E5%92%8C%E7%A8%8E%E8%B4%B9%E8%A1%A1%E9%87%8F h_01JDSGVGFB2AAZMZ87628WTAED=%E5%87%80%E6%94%B6%E5%85%A5%E5%92%8C%E7%A8%8E%E8%B4%B9%E8%A1%A1%E9%87%8F edit-tax-rates-using-the-tax-api=%E4%BD%BF%E7%94%A8tax-api%E4%BF%AE%E6%94%B9%E7%A8%8E%E7%8E%87 h_01JDSGYR29TPPA9BPKJJRWNWKB=%E4%BD%BF%E7%94%A8tax-api%E4%BF%AE%E6%94%B9%E7%A8%8E%E7%8E%87 parameters-and-values-to-use-in-the-api=%E5%8F%AF%E5%9C%A8%E8%AF%A5api%E4%B8%AD%E4%BD%BF%E7%94%A8%E7%9A%84%E5%8F%82%E6%95%B0%E5%92%8C%E5%8F%82%E6%95%B0%E5%80%BC 01H8VJJP1D8AZFRPEX7GYRH9CX=%E5%8F%AF%E5%9C%A8%E8%AF%A5api%E4%B8%AD%E4%BD%BF%E7%94%A8%E7%9A%84%E5%8F%82%E6%95%B0%E5%92%8C%E5%8F%82%E6%95%B0%E5%80%BC" />
