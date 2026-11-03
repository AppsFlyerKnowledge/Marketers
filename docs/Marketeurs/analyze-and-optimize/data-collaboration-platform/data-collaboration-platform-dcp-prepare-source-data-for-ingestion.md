---
title: Data Collaboration Platform (DCP) - Prepare source data for ingestion
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-07-27T10:44:15Z'
  id: 43205325114897
  locale: en-us
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/43205325114897-Data-Collaboration-Platform-DCP-Prepare-source-data-for-ingestion
---
> **At a glance:** Prepare your source data to maximize match rates between collaborator datasets and optimize collaboration outcomes.

## About data preparation

The AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP)</Anchor> is designed to ingest and process large-scale transactional data, user-level data, or a combination of both from multiple collaborators. Once ingested, the DCP can match users across datasets using shared identifiers (for example, hashed email or hashed phone) and enable collaboration workflows based on that data.

This article outlines:

* The kinds of data the DCP can process (transactional, user-level, or a combination)
* How to structure data to maximize match rates between collaborators, and for optimal matching by activation partners
* Which data structures are recommended and which aren't
* How to handle multi-value identifiers when using CSV files

## Understand data types

Most sources used in collaborations involve one or both of the following data types:

* **User-level (identity) data**
  * **Goal:** Represent each user and the identifiers used for matching
  * **Recommended structure:** One row per user
* **Transactional (event) data**
  * **Goal:** Represent user actions (purchases, visits, transactions)
  * **Typical structure:** Multiple rows per user (because a user can have many transactions)

## Data structuring guidelines

This section outlines DCP data structuring guidelines and best practices.

<div id="workflow-and-structuring-guidelines" />

<Accordion title="Recommended data structures">

**To structure your source data for optimal ingestion and maximum outcomes in DCP:**

1. Ensure it <Anchor target="_blank" href="/marketers/fr/docs/data-collaboration-platform-dcp-create-and-manage-sources#source-data-requirements">meets source data formatting requirements</Anchor>.
2. For best results, **structure identity data as one row per user and include all available identifiers for that user.** See [Recommended identifier structures](#recommended-identifier-structures).
   * If users have multiple email addresses or phone numbers, use array-based formats (such as Parquet, BigQuery, or Snowflake).
3. Check that [hashing guidelines](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner) are followed.
4. For transactional datasets (and other data types where applicable), **use the DCP Data View tool** to create a business-oriented, privacy-safe subset of your data optimized for collaboration, and share it instead of raw tables. [Why Data Views are recommended](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended).

While other structures can be used, they may not be ideally suited for getting the most out of DCP. See [Data structures that aren't recommended](#data-structures-that-arent-recommended).

#### Recommended identifier structures

To maximize match rates, it's recommended to send user-level identity data as a single row per user whenever possible and to include all available identifiers in a structure that accurately reflects how users are represented.

**Option 1: One row per user, one value per identifier type**

**Simple and effective.**

Use this when each user has at most one hashed email address, one hashed phone number, and so on.

**Example**

| User ID | Hashed Email | Hashed Phone |
| --- | --- | --- |
| 123 | 5d41402 | 152d234b70 |
| 456 | 7d793037 |  |
| 789 |  | 0e6e5414 |

**Why this is recommended**

* Simplest to prepare and ingest
* Easy to validate and troubleshoot
* Strong matching performance when identifiers are complete and consistent (for matching with collaborator datasets and activation media partner matching)

**Best fit**

* Great for CSV-based uploads
* Also works well in Parquet / BigQuery / Snowflake

**Option 2: Arrays (lists) of identifiers for multi-value fields**

**Best for accuracy when users have multiple emails and phones.**

Use this when a user can have multiple values of the same identifier type, such as:

* Multiple hashed emails
* Multiple hashed phones

This structure should be represented as **native arrays**.

**Example**

| User ID | Hashed Emails | Hashed Phones | MAID |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**Why this is preferred**

* Reflects how identity data is often stored internally
* No need to guess how many “email columns” might be needed
* Avoids ongoing schema changes
* Maximizes matching potential (for collaborator datasets and for activation media partner matching) by allowing multiple identifiers per user

**Best fit**

* Parquet (S3/GCS)
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="Practical checklist for data structuring">

#### Identity (user-level) dataset checklist

* One row represents one user.
* Include all available identifiers (hashed email, hashed phone, MAID, and so on).
* If multiple values exist (for example, multiple emails), use native arrays where possible.
* Avoid lists in cells, avoid “email\_1/email\_2/email\_3,” and avoid multi-row identity structures.

#### Transactional (events) dataset checklist

* Keep event/transaction rows as-is. See [Transactional data examples](#appendix-a-transactional-data-examples)
* Use [Data Views](#appendix-c-why-dataviews-matter-and-recommended) to create collaboration-ready user-level summaries when appropriate.

#### Data Views checklist

* Build business-oriented [Data Views](#appendix-c-why-dataviews-matter-and-recommended) (audience-ready, summarized, standardized).
* Share Data Views instead of raw sensitive tables whenever possible.
* Minimize shared fields to only what’s needed (for privacy and business protection).
* Consider aggregations to reduce access to sensitive data and improve efficiency.

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="Supported ingestion cloud services and formats">

The DCP supports ingestion through multiple cloud services, such as:

* AWS S3
* GCS (Google Cloud Storage)
* BigQuery
* Snowflake

#### Format guidance

* Use **CSV (comma-separated)** when each user has **one value per identifier type** (one email, one phone, and so on).
* When users can have **multiple values** of the same identifier type (for example, multiple hashed emails), prefer **array-capable formats**:
  * Parquet (common in big data)
  * BigQuery (arrays are built-in)
  * Snowflake (arrays are built-in)

**Notes:**

* “Arrays” just means “a list of values.”
* Parquet and arrays in BigQuery/Snowflake are standard, and most data teams can support this naturally.

See [Connector-specific example assets (AWS S3, GCS, BigQuery, Snowflake).](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)

<div id="data-structures-that-arent-recommended" />

<Accordion title="Data structures that aren't recommended">

Certain types of data structuring are ideally suited for ingestion into DCP, and others are not. The following is a list of data structures that **are not recommended**:

#### Avoid: Multiple columns for the same identifier type

Examples like “primary/secondary/third email” are discouraged.

**Example to avoid**

| User ID | Email Hash 1 | Email Hash 2 | Email Hash 3 |
| --- | --- | --- | --- |
| 123 | a1b2 | c3d4 |  |
| 456 | z9y8 |  |  |

**Why to avoid**

* The number of values per user is unpredictable
* Leads to column proliferation and schema maintenance issues

#### Avoid: “Lists inside a single cell” (free text)

Even if it looks convenient, it’s error-prone.

**Example to avoid**

| User ID | Hashed Emails (text) |
| --- | --- |
| 123 | a1b2 · c3d4 · e5f6 |

**Why to avoid**

* Not a true array type
* Formatting/escaping issues are common
* Small inconsistencies can break ingestion

#### Avoid: Multiple rows per user for identifiers (when your goal is a user identity table)

Don’t split identity data across rows when you can keep one row per user.

**Example to avoid**

| User ID | Identifier Type | Identifier Value |
| --- | --- | --- |
| 123 | hashed\_email | a1b2 |
| 123 | hashed\_email | c3d4 |

**Why to avoid**

* Requires extra processing to reconstruct users
* Higher risk of duplicates and inconsistencies
* Less efficient at scale

**Note:** Multiple rows per user are normal for transactional tables, but not ideal for the identity (user-level) table used for matching.

</Accordion>

</Accordion>

## Additional information

This section provides additional, in-depth information on relevant topics.

<div id="appendix-a-transactional-data-examples" />

<Accordion title="Transactional data examples">

Transactional/event data may have multiple rows per user:

| Transaction ID | User ID | Transaction Date | Amount | Category |
| --- | --- | --- | --- | --- |
| t\_001 | 123 | 2025-12-01 | 120.00 | Grocery |
| t\_002 | 123 | 2025-12-15 | 45.00 | Pharmacy |
| t\_003 | 456 | 2025-12-20 | 300.00 | Electronics |

**Recommended**

* Ingest transactional data in its natural structure
* Use the Data View tool to produce a collaboration-ready user-level view (for example, spend in last 30 days, category affinity, recency/frequency summaries)

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="Connector-specific example assets (AWS S3, GCS, BigQuery, Snowflake)">

### What does “array/list of identifiers” mean?

Sometimes a single user can have more than one email or phone (for example, a personal and a work email). Instead of forcing these into extra columns or messy text fields, we represent them as a list of values.

| User ID | Hashed Emails (List) |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

### 1. AWS S3 and GCS connector (Parquet)

**What the identity sample should contain (schema)**

| Field | Type | Notes |
| --- | --- | --- |
| user\_id | string | One row per user |
| hashed\_emails | array of strings | Multi-value identifier (recommended) |
| hashed\_phones | array of strings | Multi-value identifier (recommended) |
| maid | string | Optional additional identifier |

Parquet supports lists natively, which is why it’s recommended when users have multiple emails/phones.

### 2. BigQuery connector (table preview and schema screenshot)

**Example identity schema (BigQuery)**

| Field | Type | Mode |
| --- | --- | --- |
| user\_id | STRING | NULLABLE |
| hashed\_emails | STRING | REPEATED (ARRAY) |
| hashed\_phones | STRING | REPEATED (ARRAY) |
| maid | STRING | NULLABLE |

Arrays are native in BigQuery (REPEATED fields). This is the recommended approach when multiple emails/phones exist.

### 3. Snowflake connector (table preview and schema screenshot)

**Example identity schema (Snowflake)**

| Field | Type | Notes |
| --- | --- | --- |
| USER\_ID | VARCHAR | One row per user |
| HASHED\_EMAILS | ARRAY | Multi-value identifier |
| HASHED\_PHONES | ARRAY | Multi-value identifier |
| MAID | VARCHAR | Optional |

Snowflake supports list-like fields (arrays). This is preferred over creating email\_1/email\_2/email\_3 columns.

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="Why Data Views are recommended">

<Anchor target="_blank" href="/marketers/fr/docs/data-collaboration-platform-dcp-create-customized-data-views">Data views</Anchor> are customized subsets of your existing data sources that you can create without changing the original dataset. They let you perform functions that modify, refine, and summarize the data so you can share only what’s relevant in collaborations, keeping the data you share clear and focused, and all other data private and secure. Use Data Views in collaborations because they:

#### Are business-oriented and easier to collaborate with

* Data Views let you present the data in a clean, business-friendly structure (for example, “Customer Identity View”, “Eligible Audience View”, “Purchase Summary View”) rather than raw logs or complex transactional schemas.
* They help standardize definitions (for example, “active customer”, “total spend last 30 days”) so both sides are aligned and using the same logic.

#### Are more privacy-safe by design

* Data Views support data minimization: you can share only the fields and rows needed for the collaboration, instead of exposing full raw datasets.
* They reduce privacy risk by allowing you to:
  * Exclude unnecessary attributes
  * Limit granularity (for example, share aggregated metrics instead of line-level transactions)
  * Share only the identifiers needed for matching (and not additional sensitive columns)

#### Protect sensitive business data

* Raw transactional tables can contain highly sensitive business signals (for example, detailed purchase behavior, pricing patterns, merchant relationships, internal IDs).
* Data Views let you share only what’s required for the collaboration:
  * Example: share category-level aggregates instead of item-level details
  * Example: share spend buckets or summary metrics instead of exact line items
* This reduces the risk of unintentionally revealing competitive or proprietary information.

#### Can make your data more cost-effective and performant

Data Views can be structured to be lighter and more efficient, which often reduces:

* Data scanned
* Processing time
* Compute costs

Pre-structuring a collaboration-ready view (especially aggregated views) may make collaboration faster and more operationally predictable.

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="Multiple IDs/keys upload and matching behavior by platform">

**DCP identifiers upload**

| Partner/Platform | Supported Identifier Types | Upload Mode | Upload Behavior | Identifier Priority (for single-type partners) |
| --- | --- | --- | --- | --- |
| Meta | Email, Phone, IDFA, GAID, Android ID, First Name, Last Name, DOB, City, State, Zip, Country | All supported types | Uploads all supported identifier types | N/A - uploads all |
| Google | Email, Phone, IDFA, GAID, Android ID, Customer ID | Single type | Uploads one identifier type per audience | 1. Email 2. Phone 3. Mobile IDs 4. Customer ID |
| TikTok | Email, Phone, IDFA, GAID, Android ID | All supported types | Uploads all supported identifier types | N/A - uploads all |
| Pinterest | Email, Phone, IDFA, GAID | Single type | Uploads one identifier type per audience | 1. Email 2. Phone 3. Mobile IDs |
| Infillion | Email, Phone, IDFA, GAID, MM-UUID | All supported types | Uploads all supported types grouped into up to 3 files | N/A - uploads all |
| TheTradeDesk | Email, Phone | Single type | Uploads one identifier type per audience | 1. Email 2. Phone |
| AppsFlyer Data Locker | All available identifiers | All types combined | Delivers all identifiers in a single combined file | N/A - delivers all |

| Platform | Can you send multiple IDs per user? | Can they match on any of them? | Can they combine multiple IDs? | Matching model (practical) | Notes |
| --- | --- | --- | --- | --- | --- |
| Meta | Yes | Yes | Yes | Deterministic, any-ID / combo | Email, phone, MAID, fbp/fbc all evaluated; strongest “any-of-them” behavior |
| Google | Yes | Limited | No | Deterministic, prioritized | One ID resolves the user; IDs are not combined to form a match |
| TikTok | Yes | Yes | Yes | Deterministic, any-ID / combo | Very similar to Meta; ttclid strong for events |
| Pinterest | Yes | Partial | Limited | Deterministic, ID-centric | Primarily email + MAID; limited cross-ID reinforcement |
| The Trade Desk (TTD) | Yes | Via ID graph | Yes (via graph) | Deterministic via identity graph | UID2 + MAID + cookies resolved through EUID/UID2 graph |
| Infillion | Yes | Via ID graph | Yes (via graph) | Deterministic via partner graph | Relies on OmniID / partner identity resolution |

**Takeaways for activation planning**

* **Meta and TikTok**
  * Send everything you have
  * True “any-ID” behavior
  * Best platforms for identity-rich clean room activation
* **Google**
  * Send multiple IDs for coverage
  * Do not expect cross-ID reinforcement
  * Email/phone dominance is real
* **TTD and Infillion**
  * Matching quality depends more on identity graph participation
  * UID2 / OmniID coverage matters more than raw identifier count
* **Pinterest**
  * Behaves closer to Google than Meta
  * Limited upside beyond email + MAID

**TL;DR**

* Only Meta and TikTok do “any-of-them” matching natively
* Google is deterministic but single-ID resolved
* Open web platforms match via identity graphs, not raw IDs

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="Hashed data formatting guidelines by media partner">

**Universal normalization rules:**  
Before hashing any data, almost all platforms require the following normalization steps to ensure matching accuracy:

* **Text:** Convert to lowercase and trim all leading/trailing whitespace.
* **Phone:** Convert to E.164 format (e.g., +15551234567)
* **Hashing:** SHA-256 is the industry standard, though some platforms accept MD5 or SHA-1.

| Media Partner | Email Guidelines | Phone Number Guidelines | Mobile ID (MAID) Guidelines | Specific Platform Nuances & Matching Logic | Relevant Reference |
| --- | --- | --- | --- | --- | --- |
| Google Ads / DV360 | Format: Lowercase, trim whitespace. Include domain. Gmail Rule: For @gmail.com / @googlemail.com, remove periods (.) before the "@" and suffixes after (+). Hashing: SHA-256 (Hex encoded). | Format: E.164 (e.g., +16505551212). Must include country code. Hashing: SHA-256. | Format: IDFA (iOS) or GAID (Android). Hashing: Do not hash. | Matching Priority: Deterministic and prioritized (1. Email, 2. Phone, 3. Mobile IDs). It does not combine multiple IDs to form a match (single-ID resolution). DV360 PAIR: DV360 also supports the PAIR protocol for secure publisher-advertiser reconciliation. | <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/remarketing/audience-segments/customer-match/get-started">Get started with Customer Match (Google Ads API)</Anchor> |
| Meta (Facebook/ Instagram) | Format: Lowercase, trim whitespace. Hashing: SHA-256 required.<br /><br />**Note:** Meta doesn't remove dots from email addresses as part of its hashing normalization. Only lowercase + whitespace trimming should be applied before hashing for Meta. Sending a dot-stripped hashed email ("Hashed email (no dots)" in DCP source mapping) won't match Meta's own hash and will result in reduced match rates for email-domain users. This identifier variant is intended for partners that do require dot-removal (e.g., Google Ads) and should not be used for Meta/Facebook activations. | Format: Remove symbols, letters, and leading zeros. Include country code (e.g., 16505551212). Hashing: SHA-256. | Format: IDFA or GAID. Hashing: Do not hash. Lowercase, keep hyphens. | Matching Logic: Uses "any-of-them" logic; combines multiple IDs (Email, Phone, MAID, etc.) to resolve a user, providing strong cross-ID reinforcement.<br /><br />CAPI: Requires unhashed client\_ip\_address and client\_user\_agent for browser matching. | <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters/">Customer Information Parameters - Conversions API</Anchor> |
| TikTok | Format: Lowercase, remove all spaces. Hashing: SHA-256. | Format: E.164 (+[country code][number]). Also accepts without +. Hashing: SHA-256. | Format: GAID (Android) or IDFA (iOS). Case: All upper or all lower. Hashing: SHA-256 or MD5. | Matching Logic: Similar to Meta, uses "any-of-them" deterministic matching logic where any single valid ID is sufficient.<br /><br />Audience Size: Requires a minimum of 1,000 matched users to activate a Custom Audience. | <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-create-a-custom-audience-with-a-customer-file">How to create a Custom Audience with a customer file</Anchor> |
| The Trade Desk (UID2) | Format: Same "Gmail Rule" as Google (remove dots/plus). Encoding: Base64-encode the raw bytes (result is 44 chars). | Format: E.164. Hashing: SHA-256. Encoding: Base64-encode the raw bytes. | Format: AAID (lowercase) / IDFA (uppercase). Hashing: SHA-256, MD5, or SHA-1. | Matching Logic: Deterministic via identity graph. Matching depends on graph participation rather than raw ID coverage.<br /><br />Critical Nuance: You must base64-encode the raw bytes of the hash. Encoding the hex string will fail. |  |
| Pinterest | Format: Must include "@". Hashing: SHA-256, MD5, or SHA-1. | Format: E.164. Remove special characters (spaces, hyphens). Hashing: SHA-256, MD5, or SHA-1. | Format: IDFA or GAID. Hashing: SHA-256, MD5, or SHA-1. | Matching Logic: "ID-Centric." Matching is primarily driven by Email and MAID. There is "limited upside" to providing other IDs as cross-ID reinforcement is weak compared to Meta. Upload Behavior: Uploads one identifier type per audience. | DCP Data Ingestion and Structuring Guidelines |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=about-data-preparation h_01KFX4HVTT50TZMY2YF37B1C4R=about-data-preparation data-types=understand-data-types h_01KFX4HVTTAMFEGJQEYXXWG9PT=understand-data-types data-ingestion-recommendations=data-structuring-guidelines h_01KFX4HVTT2Q2EV4GAC6M8R4A2=data-structuring-guidelines h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines h_01KFXB0KEF59QCYET0R8XNH84D=recommended-identifier-structures h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=identity-user-level-dataset-checklist h_01KFZNGRC0XX7YYBYT09M49YFA=identity-user-level-dataset-checklist h_01KFZNJ7YKCT1YFYE400CNY6SP=transactional-events-dataset-checklist dataviews-checklist=data-views-checklist h_01KFZNKBXJQ4S89YHCGKP8J5F4=data-views-checklist h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats h_01KFX6XSNACVR9JWZWZW12F6C4=format-guidance h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended h_01KFX72MNYH1CSKWZAGZ2XETXY=avoid-multiple-columns-for-the-same-identifier-type avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=avoid-lists-inside-a-single-cell-free-text h_01KFX70V3BHNK93SKCRGGDVY3W=avoid-lists-inside-a-single-cell-free-text h_01KFX70V3BJE2PR7132QE27C4V=avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table h_01KFZJ2PNKB4X962VKCKSYVFFB=additional-information h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=what-does-arraylist-of-identifiers-mean h_01KFX4HVTVPHZQFNRWDH9VCEZQ=what-does-arraylist-of-identifiers-mean h_01KFX4HVTVNQZY9A8AGEBBHF6Y=1-aws-s3-and-gcs-connector-parquet h_01KFX4HVTVCMB0H1B76TCK36SF=2-bigquery-connector-table-preview-and-schema-screenshot h_01KFX4HVTVN9MSWFB7ZRT9MVCG=3-snowflake-connector-table-preview-and-schema-screenshot h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=are-business-oriented-and-easier-to-collaborate-with h_01KFX4HVTV43QFEQARSB2N49Z5=are-business-oriented-and-easier-to-collaborate-with are-more-privacysafe-by-design=are-more-privacy-safe-by-design h_01KFX4HVTVJA8Q3FTQB8A94MA1=are-more-privacy-safe-by-design h_01KFX4HVTVF8A0PM90FA6XA0V5=protect-sensitive-business-data can-make-your-data-more-costeffective-and-performant=can-make-your-data-more-cost-effective-and-performant h_01KFX4HVTVJ70HV606Y8KE4JD1=can-make-your-data-more-cost-effective-and-performant h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />
