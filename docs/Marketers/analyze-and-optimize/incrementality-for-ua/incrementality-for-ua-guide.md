---
title: Incrementality for UA Guide
excerpt: >-
  Run an Incrementality experiment to understand the true impact of your User
  Acquisition (UA) campaigns.
metadata:
  keywords:
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2025-11-18T06:58:45Z'
  edited_at: '2026-07-30T09:04:57Z'
  id: 41021758795025
  locale: en-us
  section: Incrementality for UA
  section_id: 40761623209873
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/41021758795025-Incrementality-for-UA-Guide
---
<Embed title="Incrementality for UA Guide" typeOfEmbed="youtube" url="https://www.youtube.com/embed/vGrLyOvgdN0?si=91ZV8Xw25mmShB_F" providerUrl="https://www.youtube.com" />

## About Incrementality for UA

In today's omnichannel marketing environment, understanding true campaign effectiveness requires more than one lens. Last-touch attribution remains essential for real-time performance monitoring and granular insights, but it doesn't provide insight into whether a campaign caused true causal lift. Incrementality for UA adds a critical layer by measuring whether campaigns actually drive new user growth.

**Incrementality for UA** does this by complementing attribution with scientifically rigorous geo-experiments. These automated experiments measure the real causal lift of your campaigns, enabling smarter budget allocation and more confident decision-making.  
As the trusted marketing cloud leader, AppsFlyer offers Incrementality for UA—a powerful way to measure the true impact of your campaigns. This solution delivers critical, trustworthy insights alongside attribution, enabling complete and seamless measurement in one unified platform.

**Why use Incrementality for UA?**  
User acquisition teams today face complex challenges, including fragmented user journeys, increasing privacy restrictions, and gaps in visibility across various channels. Incrementality for UA helps you overcome these barriers by revealing the actual business impact of your campaigns.

**With Incrementality for UA, you can:**

* **Focus on true performance:** Get additional insights beyond ad engagement and attributed conversions. Understand which campaigns truly drive growth—extending the view provided by attribution.
* **Perform head-to-head comparisons:** Test multiple campaigns or media sources simultaneously with automated test/control group allocation and native support from major ad platforms like Meta, Google Ads, and TikTok.
* **Optimize budget allocation:** Shift spend away from low-impact campaigns and reinvest in those that drive real user growth.
* **Automate experiment workflows:** Skip the manual setup and avoid BI dependencies. AppsFlyer automates experiment design, execution, and analysis.
* **Measure with privacy in mind:** Experiments run on aggregated geo-level data, compliant with privacy regulations like GDPR and Apple's ATT.

**About geo-experimentation**

Incrementality for UA uses a geo-based experimental design. Geographical regions are divided into statistically similar groups, based on the app's historical installs or event behavior. One group is exposed to your UA campaign and the other is withheld from exposure. After the experiment runs for a defined period, the difference in performance between the two groups is analyzed to reveal incremental lift. Geo-experimentation is privacy-safe, bias-resistant, and doesn't rely on user-level data.

Incrementality for UA provides the insights you need to understand the true incremental value of your marketing campaigns, unhindered by inconsistent user-level data or targeting overlaps. This will give you the true picture of your campaigns' effectiveness and help you make better, data-driven decisions.

## Experiment design and insights

This section explains how Incrementality for UA experiments are structured, how to work with them, and how they generate reliable, causal insights into campaign performance.

<div id="understanding-geo-experimentation-explainer" />

<Accordion title="Understanding geo experimentation">

Incrementality for UA uses geo-based experimentation to measure true campaign impact in a scientifically rigorous way. Instead of segmenting users, we segment geographic areas into statistically similar exposed and holdout regions. These regions are selected based on size and historical app behavior. Ads run only in the exposed regions, while the holdout regions receive no exposure. By comparing the behavior of the two groups during the holdout period, we can measure the actual causal effect — not just correlation.

**Geo-experiments follow a structured timeline:**

* **Pretest:** Both groups are equally exposed to ads from the measured campaigns. During this time, we collect baseline data and build a model that captures the historical relationship between the exposed and holdout regions.
* **Intervention (the experiment):** Campaigns are activated in the exposed regions only. Holdout regions are prevented from viewing ads from the measured campaigns.
* **Causal effect calculation**: The difference between the observed outcomes in the holdout regions and the exposed regions during the experiment is summed over time and used to determine the cumulative impact.

**Time-Based Regression (TBR)**

At the heart of our geo-experimentation is Time-Based Regression (TBR). TBR is used to calculate the marketing lift by predicting what would have happened in the absence of a marketing intervention. This involves comparing the observed outcomes in an exposed region (where the intervention is made) with the predicted outcomes based on the historical relationship between a holdout region (not exposed to the intervention) and the exposed region.

**How it works:**

* Creating geo-designs of holdout and exposed regions:
  * Per app, AppsFlyer analyses historical app install or in-app event behaviour and uses TBR (explained in the next steps) on thousands of randomized sets of geographical holdout/exposed regions over multiple time periods to find the ones with the smallest difference.
* Pretest period:
  * During this time, before the intervention starts, data is collected for both the holdout and exposed regions.
  * A regression model is built to capture the relationship between the time series of the exposed region and the holdout region.
* Prediction of counterfactuals:
  * Using the model developed in the pretest period, the expected outcomes for the holdout region (if no intervention occurred) are predicted during the test period. These are called "counterfactuals".
* Test period:
  * For the campaigns that are part of the Incrementality experiment, the predetermined holdout regions are automatically excluded from viewing ads for the duration of the experiment.
* Causal effect calculation:
  * The causal effect of the intervention at each time point is the difference between the observed outcome in the holdout region and its counterfactual prediction.
* Cumulative effects:
  * These differences are summed up over time to determine the cumulative impact of the intervention (e.g., total increase in installs or conversions).
* Marketing lift:
  * The marketing lift is the cumulative effect that quantifies the incremental results driven by marketing activity compared to what would have been expected without it.

</Accordion>

<div id="use-cases" />

<Accordion title="Use cases">

Incrementality for UA helps you solve key growth challenges by revealing the true business impact of your campaigns. Below are some common use cases where geo-based incrementality testing adds critical value.

1. **Optimize budget allocation across ad platforms**  
   **Challenge:** Attribution metrics show similar performance across multiple platforms, but you're unsure which is actually driving growth. **Solution:** Run parallel incrementality tests using multiple cells across platforms. Use the results to identify which platform causes real uplift and shift budget accordingly.
2. **Validate performance of new channels or formats**  
   **Challenge:** You're testing a new channel or ad platform, but early metrics are inconsistent or inflated due to targeting overlap. **Solution:** Use geo-testing to isolate the impact of the new channel from others in your mix. Determine whether it contributes net new installs or just cannibalizes existing ones.
3. **Understand impact of branded campaigns**  
   **Challenge:** Branded campaigns perform well in attribution reports, but you're not sure if users would have converted anyway. **Solution:** Geo-experiments can reveal whether branded search or display ads are actually influencing user behavior, or if they're capturing existing demand.
4. **Compare campaign strategies within the same platform**  
   **Challenge:** You want to test two creative strategies (e.g., video vs. carousel) or bidding types (e.g., maximize installs vs. ROAS) within the same network. **Solution:** Run a multi-cell experiment with each strategy assigned to a different cell. Compare the incremental lift of each and choose the winner.
5. **Reallocate spend from saturated to scalable markets**  
   **Challenge:** Mature markets show diminishing returns and rising acquisition costs, but attribution data doesn't clarify if you're reaching new users. **Solution:** Geo-lift tests show whether campaigns in these markets are still incremental. If not, shift budget to untapped or undervalued regions with higher potential.

</Accordion>

<div id="selecting-campaigns" />

<Accordion title="Selecting what to measure">

This section discusses the best campaigns to select for your experiments. Here are a few things to consider:

* **Impact:** Which test could influence your overall strategy the most? Often, that means starting with your largest initiatives since having a deeper understanding of how they affect growth will lead to meaningful optimizations.
* **Conversion volume:** Strong experiments need enough data. For each measured campaign, aim for a minimum of 5000 monthly app installs or events, according to the main KPI you would like to measure
* **Exploration:** Incrementality is an amazing tool when testing something new, such as entering a new market or launching a new channel.
* **Having a clear hypothesis or test question:** Like any other scientific experiment, spending some time on phrasing your main question will contribute to the effectiveness and actionability of your Incrementality experiment. For example, do you expect one channel to be more incremental than the other? How will it affect your marketing strategy if your hypothesis is proved or disproved?

</Accordion>

<div id="understanding-experiment-results" />

<Accordion title="Understanding experiment results and using the insights">

**Key experiment KPI outputs include:**

* **Lift (%):** The causal impact of the measured marketing activity, measured as the additional conversions (e.g., installs or in-app events) your campaign actually drove, above and beyond what would have happened without it.
* **Incremental conversions:** The number of installs or events that are caused by the measured campaign.
* **Cost per incremental install** / **Cost per incremental event:** The average cost of each incremental conversion, based on the campaign's ad spend.
* **Incrementality factor:** The ratio between incremental installs or events (as measured by the experiment) to the classic attribution installs or events (as measured in AppsFlyer's classic attribution).

See the full list of experiment KPIs in the [dashboard section.](#a-tour-of-the-dashboard)

To make Incrementality insights actionable, AppsFlyer provides both the Lift % and campaign-level Incrementality KPIs for effective marketing decisions.

**Optimizing based on Lift %:**

**A. No lift:**  
The ultimate goal of marketing is to generate incremental outcomes. If your campaign was measured to have no lift (holdout regions are performing at the same level as exposed regions), this means it is not adding value beyond what would have happened without it and requires further optimization in order to be meaningful for growth. If your campaign has no lift, consider the following:

* Shift budgets to more incremental campaigns or channels.
* Optimize: As with any other low-performing campaign, you can work to improve it by adjusting bids, goals, target audience, creatives, and other relevant factors. You can then run another Incrementality experiment following the update to monitor if incrementality has improved.
* Diagnose what factors might be causing low lift by checking tech setup, targeting, channel mix, placements, budgets, keywords, creatives, or campaign overlap. These learnings will be highly beneficial for optimizing towards incremental outcomes in the future.

**B. Positive lift:**  
Positive lift means your campaign is generating incremental outcomes beyond what is achieved without it. As an initial step, you should validate that all your marketing efforts are generating positive lift. When lift is positive, consider the following:

* Increase investment in platforms/channels/campaigns to scale what's proven to drive growth.
* Broaden reach by expanding audiences or locations to amplify impact.
* Identify growth factors to duplicate success and prioritize winning strategies.
* Compare campaigns or channels based on lift: Lift is a relative measure calculated by comparing holdout and exposed regions. As such, comparing campaigns based on lift is challenging. For example, if both campaigns have the same impact but one of them is reaching a significantly higher number of users or has a significantly higher amount of spend, its lift will be higher.  
  When comparing, try and compare campaigns that are similar in spend and reach and are generally targeting the same geographical regions.
* If you are just starting out with Incrementality measurement for your app or business, you may not yet have a solid benchmark to determine the exact level of positive lift expected from a given campaign, channel, or investment. In this case, it is recommended to optimize using AppsFlyer's campaign-level Incrementality KPIs, as described below.

**Optimizing based on campaign-level incrementality KPIs:**

**A. Total incremental conversions and cost metrics:**  
In the same way it is used with classic attribution, the overall volume of incremental conversions and the ad spend invested to generate these conversions provide clear and actionable metrics for optimization. You can use the campaign-level incrementality conversions count and cost per incremental conversion to determine if the campaign meets your volume and ROI goals, and how it performs against other campaigns or channels.

**B. Leveraging classic attribution and incrementality data side-by-side**  
For both the count of campaign-level conversions and cost per conversion, the Incrementality dashboard presents classic (last-touch) attribution data AND incrementality data side-by-side so you can learn the relationship between the two models and action your learnings at a larger scale.  
When looked at separately, classic ("last-touch") attribution and incrementality are two different attribution models, each one with its own advantages and disadvantages:

* Classic ("last-touch") attribution is real-time, standardized, highly scalable, and granular. Therefore, it enables user-level optimization both from the advertiser end and through real-time ad platform algorithms. However, it is biased towards bottom-funnel engagement and does not provide scientific causal proof.
* Incrementality is a great tool to scientifically prove causal impact and is ideal for omnichannel measurement. However, it provides aggregated (campaign level) insights, and is periodic and harder to scale.

When used together, the two models provide a holistic view of marketing performance. AppsFlyer's Incrementality Factor presents the relationship between classic attribution data that is the "baseline" used for ongoing marketing optimization, and incrementality data that is used to measure causal impact. Here is how you can use incrementality factors for optimization:

* **Incrementality factor above 100%:** Incrementality has measured more conversions than the conversions measured in classic attribution for the same campaign. For example, a 110% rate means incremental conversions are 10% higher than conversions measured using classic attribution. This increase in conversions also translates to a decrease in cost per conversion, since more conversions are generated for the same amount of spend.  
  If the incrementality factor is above 100%, consider the following:
  * Re-evaluate budget allocation in accordance with the decrease in cost per incremental conversion.
  * Re-evaluate bids and optimization goals in accordance with cost per incremental conversion and incremental return on ad spend.
  * Implement the factor to similar campaigns ahead of making future marketing decisions. For example, if your video campaigns consistently show ~110% incrementality factor for app installs when measured in incrementality experiments, you can treat classic attribution app installs for similar campaigns as 10% higher when making marketing decisions (i.e., each 100 classic attribution installs are in fact closer to 110 installs).
* **Incrementality factor below 100%:** Incrementality has measured fewer conversions than the conversions measured in classic attribution for the same campaign. For example, a 90% rate means incremental conversions are 10% lower than conversions measured using classic attribution. This decrease in conversions also translates to an increase in cost per conversion, since fewer conversions are generated for the same amount of spend. If the incrementality factor is below 100%, consider the following:
  * Re-evaluate budget allocation in accordance with the increase in cost per incremental conversion.

* * Re-evaluate bids and optimization goals in accordance with cost per incremental conversion and incremental return on ad spend.
  * Implement this factor in similar campaigns to inform future marketing decisions. For example, if your video campaigns consistently show a ~90% incrementality factor for app installs when measured in incrementality experiments, you can treat classic attribution app installs for similar campaigns as 10% lower when making marketing decisions (i.e., each 100 classic attribution installs are in fact closer to 90 installs).

</Accordion>

<div id="pausing-or-extending-experiments" />

<Accordion title="Pausing or extending experiments">

**Consider pausing experiments (before the default 30 days) if:**

* Lift, Incrementality Factor, and Cost metrics have remained stable for over 7 days.
* There's a business justification to obtain faster results at the expense of potentially less accurate or less "normalized" Incrementality metrics.

**Consider extending experiments (beyond the default 30 days) if:**

* Campaign volume was lower than expected and is anticipated to increase beyond the minimum requirement of daily incremental conversions.
* The conversion window for the measured event is exceptionally long, requiring additional time for users to convert.

</Accordion>

## Get started

To get started with Incrementality for UA, follow the steps below:

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Prerequisites**

* An AppsFlyer [account](https://www.appsflyer.com/sign-up/) with an **Incrementality for UA** subscription (ask your CSM to enable it).
* The [AppsFlyer SDK](/docs/basic-sdk-integration-guide) installed in your mobile apps.
* Your app must have at least 120 days of install data.

<div id="create-the-experiment-" />

<Accordion title="Step 1. Create the experiment">

The first step is creating the experiment.

**To create the experiment:**

1. Access Incrementality for UA by clicking **Optimize** > **Incrementality for UA**, in the AppsFlyer side menu.

   ![Click Inc for UA new.png](https://files.readme.io/4170287cc98e038272fd91ee36cbf775a33b8a418920c7fabe54e32cff5789cd-41021731857041.png)
2. Click **+ New experiment**.
3. **Fill out the experiment form:**
   1. **Enter experiment name** - Create a descriptive name for the experiment, then click **Next**.
   2. **Define your geo design** — Select the app, country, and main metric you want to measure. AppsFlyer uses this to calculate the optimal allocation of exposed and holdout regions for your experiment.

      ![step 2 geo design.png](https://files.readme.io/3a901bd4dcccb788b1d0cc8f118cbdb0c682b570b470d13deba4f6ce0f852c3b-41021758781713.png)

      After you submit, AppsFlyer reviews your geo design — this usually takes just a few minutes. Your geo design will either be ready to use, or unavailable:

      * **Ready** — Your geo design is approved and ready to use. You can proceed with the experiment.
      * **Unavailable** — The geo design doesn't currently meet the requirements for a valid experiment, based on the data available for the selected app, country, and metric combination. You can try resubmitting after 30 days, as eligibility may change as your app collects more data.

        <br /><br />**Note**<br />


      #### Note

      If geo design rules exist for the selected app and country, they're automatically applied when the geo design is calculated. See [Geo design policy](#h_01_geo-design-policy) to learn more.



      > 📘 **Note**
      >
      > Each country has a certain number of **cells** available for your experiment. A cell consists of an exposed and holdout group pair that are structured to be similar to each other and to the entire country. You can use multiple cells in one experiment for a head-to-head comparison of different campaigns across media sources, or use them individually in separate experiments.
      >
      > The number of available cells per country depends on the country's geographic size, population distribution, and app activity levels—factors that affect the ability to create statistically valid exposed/holdout pairs. Countries with more granular, active regions support more cells, enabling more experimentation.

      * **Select app** - Select the relevant app for the experiment.
      * **Select country** - Then, select the country where you want to run the experiment. Click **Next**.
      * Select the **Main metric** you want to measure. This can be installs or an in-app event.
   3. **Set campaign details:**

* You'll need to select a **Media source** connection for each experiment cell. This is the media source where your campaign runs. If there are no connections, you can [create a new connection.](#Connections)
* Then select the relevant campaigns to measure in the experiment.  
  Incrementality experiments can be set to measure individual campaigns (for example, "How is the Google campaign performing vs. the Meta campaign") or the entire media source by selecting multiple campaigns within a single experiment cell (for example, "How is Google performing vs. Meta?").  

  Choose between:  
  **Campaign level:** to measure the impact of a single campaign within a media source  
  **Channel level:** to measure the joint impact of multiple campaigns within a media source

  **Note:** If multiple campaigns are selected within one cell:

  * All selected campaigns will share the same holdout regions.
  * Incrementality insights will be presented at the cell level, and not at the individual campaign level.

    ![Inc for UA - Set campaign details .png](https://files.readme.io/c92c2b785ea80d2c89fd06033b008a3618e04d88a3cc286e923acf88b5924261-45947468030097.png)
* Once a geo design is approved, you’ll see the experiment breakdown:
  * **Holdout regions** - The regions held out from exposure to your campaigns during the experiment
  * **Exposed regions** - The regions exposed to your campaigns, used as the measurement baseline
  * **Geo design rules** - Your active rules and the regions they cover. [Learn more](#h_01_geo-design-policy)
* When selecting a campaign name, below you'll see the minimum number of incremental installs or events (based on your selected main metric) required to measure your campaign's positive impact with high statistical confidence. This is known as the "Minimum Detectable Effect" of the experiment. Make sure the selected campaign is expected to generate at least this number of conversions.

  **Tip:** Choose a campaign that regularly meets or exceeds this minimum to ensure reliable, statistically valid results.
* You can add additional experiment cells if you want. To add: Click **+ Experiment cell** and select the relevant connection and campaign. A cell consists of an exposed and holdout group pair that are structured to be similar to each other and to the entire country. You can use multiple cells in one experiment for a head-to-head comparison of different campaigns across media sources.  

  After setting up the cells, click **Next**.

4. **Review summary** - Check that the experiment summary looks good, then click **Launch experiment**.  
   The experiment begins. Initial results will display within 24 hours.

   > 📘 **Note**
   >
   > Once the experiment is over, the connected campaigns will return to their previous geo-targeting settings. This ensures campaign continuity and consistency and lets you resume UA activities without needing to reconfigure targeting manually.
   >
   > **Example**  
   > Let's say you ran an experiment in the United States using three designated exposed cities. During the experiment, your campaign was restricted to only those cities. When the experiment ends, the campaign will automatically resume its original targeting—such as "United States (all locations)"—as it was configured before the experiment began.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="Step 2. Analyze the results and gain insights">

<span id="zd-access-the-experiment-dashboard"></span>You can see the experiment results on the experiment dashboard.

#### Access the experiment dashboard

1. Go to your Incrementality for UA experiments by clicking **Optimize** > **Incrementality for UA**, in the AppsFlyer side menu. 

   ![from Oprimize click Incrementality UA.png](https://files.readme.io/922e084c955b3220a5bc3ac82079515f2c07bc4bc1bc3861343132452cc4fc08-41021731858321.png)
2. Click the specific experiment to access the experiment dashboard.

   ![Experiments table (1).png](https://files.readme.io/ffc37ed1e7381c73883933cb0de7a84495dd737e050849760e427e36d2b9918d-41021758785041.png)

#### A tour of the dashboard

[**![New Incrementality dashboard.png](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)**](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)

**The top of the dashboard displays 2 visual graphs:**

* The **Lift: Exposed vs. holdout regions** graph - Shows the incremental lift per experiment cell.
* The **Experiment timeline: Exposed vs. holdout regions** graph - Shows a side-by-side comparison of incremental installs per day of the experiment date range, per cell.

The middle section of the dashboard displays the **Experiment KPIs** by campaign cell, media source, and campaign:

* **Classic attribution installs -** The number of installs the campaign contributed, as measured by classic attribution.
* **Incrementality installs -** The number of installs the campaign contributed, as measured by the experiment.
* **Incrementality factor -** The ratio between incremental installs (measured by the experiment) to classic attribution installs. For example, a 110% rate means incremental installs are 10% higher than installs measured using classic attribution.
* **Classic attribution cost per install -** The average cost of every attributed install, based on the campaign's ad spend.
* **Incrementality cost per install -** The average cost of every incremental install, based on the campaign's ad spend.
* **Lift** - How many more installs occurred because of your campaign, compared to what would have happened without it. Calculated as: Lift (%) = (actual performance in exposed group (excluded regions) - predicted performance in exposed group) / predicted performance in exposed group * 100 * -1.
* **Confidence** - The level of statistical confidence that the lift is greater than zero.  

  For guidance on how to read the results, see [Understanding experiment results and using the insights.](#understanding-experiment-results)

The bottom of the dashboard is the **Cumulative incremental installs** graph which shows the cumulative incremental installs per cell.

**Note:** If **Channel level** measurement is selected (multiple campaigns within one cell):

* All selected campaigns will share the same holdout regions.
* Incrementality insights will be presented at the cell level, and not at the individual campaign level.

[![Channel level experiments dashboard cropped narrower.png](https://files.readme.io/4bcf80c6427e58d13b7ab0380033cb7e34852bd402150b2c05c075e5db3604a3-small-46014061198353.png)](https://files.readme.io/4bcf80c6427e58d13b7ab0380033cb7e34852bd402150b2c05c075e5db3604a3-small-46014061198353.png)

</Accordion>

## Manage

This section explains how to manage your connections, geo design policy, and experiments.

<div id="Connections" />

<Accordion title="Connections">

Connections refer to the integration between Incrementality for UA and your media partners. They make it possible to link campaigns and run experiments with connected platforms.

**To add media source connections:**

1. Access Incrementality for UA by clicking **Optimize** > **Incrementality for UA**, in the AppsFlyer side menu.
2. Click the **Connections** tab, then **+ New connection**.

   ![from Connections tab click +New connection w arrow.png](https://files.readme.io/e9df79d34ec3d94e89f51f42b132f8ba475225b46246d044d2a720991b0900e0-41021731865745.png)
3. Select a media source to connect to.

   ![Add connection.png](https://files.readme.io/c9eab02131220cd28683a717745bff852da28847a4164fa27b5be4780cd98018-41021731866897.png)
4. Enter your credentials to log in and create the connection.

</Accordion>

<div id="h_01_geo-design-policy" />

<Accordion title="Geo design policy">

The geo design policy lets you define geographic experiment design rules at the account level. Rules are set per app and country, and are automatically applied to all geo designs calculated after the rule is saved.

Use geo design rules to accommodate legal restrictions, protect high-value markets, or isolate regions affected by parallel tests.

#### Geo design rule types

Three rule types are available:

| Rule type | What it does | Example use case |
| --- | --- | --- |
| **Don't holdout** | These regions are never placed in holdout groups, but can still be in exposed groups. Your campaigns in these regions are never paused or interrupted by the experiment. | A top-performing market that must stay active at all times. |
| **Don't target** | These regions are excluded from campaign targeting entirely. They won't appear in exposed or holdout groups. | A market where advertising is legally restricted. |
| **Exclude from analysis** | These regions will stay in the campaign targeting to maintain normal advertising activity, but won’t be included in exposed or holdout groups. | <ul><li>Regions running parallel geo-lift tests that could skew results.</li><li>Regions running parallel geo-lift tests or expected local marketing efforts that could skew results.</li></ul> |

#### Set up a geo design rule

**To set up a geo design rule:**

1. In Incrementality for UA, click the **Advanced settings** tab.
2. In the **Geo design policy** section, click **+ New geo design rule**.
3. In the **New geo design rule** dialog, select the **app** and **country** this rule applies to.
4. Under **Rules**, configure each rule:
   1. Select the **Geo design rule** type: Don't holdout, Don't target, or Exclude from analysis.
   2. Select the **regions** (states or sub-state regions, depending on the country). You can search by name or code.
5. To add another rule type for the same app and country, click **+ Add rule**.
6. Review the **Summary** panel on the right, which updates in real time as you make selections.
7. Click **Save**.

The rule is now active and will be applied to all geo designs calculated for the selected app and country going forward.

#### Delete a geo design rule

**To delete a geo design rule:**

1. In the **Geo design policy** section, find the rule you want to remove.
2. Open the actions menu and select **Delete**.
3. Confirm in the **Delete rule?** dialog.

> 📘 **Note**
>
> Deleting a rule doesn't affect active experiments. If there were previous rules (or no rules), that is what remains in effect for any experiment already running. Deleting a rule only removes it from future geo designs/experiments.

#### View geo design rules in an experiment

Once a geo design is approved and you're setting up your experiment, you'll see a region breakdown section (marked **Rules apply**) showing:

* **Holdout regions** - The regions held out from exposure to your campaigns during the experiment
* **Exposed regions** - The regions exposed to your campaigns, used as the measurement baseline
* **Exclusion rules** - The active rules (Don't holdout, Don't target, Exclude from analysis) and the specific regions they cover

In the experiment report, you can view the full geo breakdown by selecting **Geo design breakdown** from the actions menu. This shows the same breakdown as above, showing the rules that were active when the experiment was created. To manage your rules, click **Manage geo design policy** at the bottom of the panel.

#### Traits and limitations

Keep the following in mind when working with geo design rules:

| Trait | Description |
| --- | --- |
| Scope | Rules apply per app and country combination. |
| Geographic granularity | Regions are defined at the state or sub-state level, depending on the country. |
| Rule persistence | Rules remain active until deleted. |
| Retroactivity | Rules apply only to geo designs calculated after the rule was saved. Active experiments are not affected. |

</Accordion>

<div id="Experiments" />

<Accordion title="Experiments">

You can view and manage all your experiments in one place.

**To view and manage your experiments:**

In **Incrementality for UA**, click the **Experiments** tab.

[![Experiments table.png](https://files.readme.io/61958568e19f243855237465d132935a339ab18f24b5a8c8318d411239b7fd8b-41021758787089.png)](https://files.readme.io/61958568e19f243855237465d132935a339ab18f24b5a8c8318d411239b7fd8b-41021758787089.png)

For each experiment, you can see the:

* **Experiment name**
* **App** - sortable
* **Country** - sortable
* **Media source**
* **Dates** - The experiment date range
* [**Status**](#status-column) - You can see the number of days left in the experiment or when it's completed.
* **Lift**

#### **Status column**

* **Completed** - Experiment period has ended
* **Active** - Experiment is currently running
* **Pending** - Experiment pending results (first 24 hours)
* **In review** - Design in review (up to 24 hours until answer)
* **Ready** - Design was reviewed and found eligible
* **Unavailable** - Design was reviewed and wasn't found eligible

Hover on the experiment to access the![action menu.png](https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png) actions icon.

![Experiments menu.png](https://files.readme.io/5e25e2b4b7f9651ad6a510916b9ee2b2a45d4064a0801a24baa6e3d62bde81a0-41021731868049.png)

From here you can:

* View experiment details
* Extend experiment duration
* Stop experiment

</Accordion>

<div id="extend-experiment" />

<Accordion title="Extend experiment">

**To extend an experiment:**

From the experiment, click the![action menu.png](https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png) actions icon (on the upper-right) and select **Extend experiment duration**.

![Extend experiment.png](https://files.readme.io/191463618d7bcdba2210e71bf38719c8d5af9951a5282a98cc1e3bc87a7e853b-41021731869329.png)

This will extend the experiment by an additional 14 days.

</Accordion>

<div id="stop-experiment" />

<Accordion title="Stop experiment">

**To stop an experiment:**

From the experiment, click the ⠇actions icon (on the upper-right) and select **Stop experiment**.

![Stop experiment.png](https://files.readme.io/2622bca9bafa7894d4ca967f13d6626eb3cd53554720d134d8092ebb0d561740-41021731870609.png)

</Accordion>

## Traits and limitations

This section outlines some key traits and limitations of Incrementality for UA.

<div id="key-traits-and-limitations" />

<Accordion title="Key traits and limitations">

| Trait | Description |
| --- | --- |
| Supported countries | Incrementality for UA currently supports experiments in the United States, India, Mexico, Brazil, Japan, and Germany. Additional countries will be added as they become available. |
| Supported campaign geo-targeting | Incrementality for UA supports campaigns that target a single, entire country. Campaigns that target multiple countries or specific regions within a country (for example, states or cities) aren't supported. |
| Historical app engagement data | The app must have at least 120 days of install and/or in-app event data available. |
| Minimum monthly non-organic installs | Each measured app must generate at least 10,000 non-organic installs per month to run a valid experiment. |

</Accordion>

<div data-zendesk-anchors="overview=about-incrementality-for-ua h_01HBB6EJ8SQ3776WCVQZA4MJ6M=about-incrementality-for-ua get-started=experiment-design-and-insights h_01JZQ4N4PEKTP1TZTDQ191ZDM3=experiment-design-and-insights h_01JZQ4Q1C035S9EXVJX8YR3PEA=understanding-geo-experimentation-explainer h_01K049CDW93B3C7VZSNFQ1AD0N=use-cases h_01JZQ4Q1C0BZAH7E0J2T1SCPD0=selecting-campaigns h_01JZQ4Q1C0Z3M002TWYKB8SS3M=understanding-experiment-results h_01JZQ4Q1C0NWWVD8ENVJB50RMD=pausing-or-extending-experiments h_01HBB6EJ8S2T9JHKVWH1JK1FPD=get-started h_01HBB6EJ8SVV71R5W9Z96D7WCG=create-the-experiment- h_01K2F27SEQF8N38FMCW8PSFB36=note h_01KVA5SPC58YXP67G86Z2CHGDF=note-1 h_01K2F1FQ0NN5YPWK5026Y7935D=note-2 01JV7F4ECQAY0PJNV2A94E5GA9=analyze-the-results access-the-experiment-dashboard=zd-access-the-experiment-dashboard h_01JZJ70C1C0ZRD8WMCKZBHKCEP=access-the-experiment-dashboard h_01JZJ70K0QTGZ2V3T1TJ1VG08H=a-tour-of-the-dashboard h_01JZ88Y5TQJCYQ2057RASHCP9D=manage h_01HBB6EJ8T4RRKJY632180KZWM=Connections geo-design-policy=h_01_geo-design-policy h_01KVA5SPC5PCR7BAK971PGHMCW=geo-design-rule-types h_01KVA5SPC5X3VRK60AJ74TJFCS=set-up-a-geo-design-rule h_01KVA5SPC54N4ECEMHJW2PV9K7=delete-a-geo-design-rule h_01KVA5SPC5GY7SVPT8BAFF1BPT=note-3 h_01KVA5SPC5K7M0AEYVGVCAMY4W=view-geo-design-rules-in-an-experiment geo-design-policy-traits-and-limitations=traits-and-limitations h_01KVA5SPC61N9H7PEKYRX01M9Y=traits-and-limitations h_01K2HQ7M74PGY2BC2X1KJ1F0Z4=Experiments h_01K9VPG89HGV9BK8W94WC7WH8Q=status-column h_01K2HMD3QVJX9KYPQ7GS91KQ6Y=extend-experiment h_01JZ894VWK49JW8M97GMTC5JPX=stop-experiment traits-and-limitations=traits-and-limitations-1 h_01KAZQSWB0H9SM7W9PADRJ9B3N=traits-and-limitations-1 h_01KAZQQMBP5AHE8KQ5V71TCVAY=key-traits-and-limitations" />
