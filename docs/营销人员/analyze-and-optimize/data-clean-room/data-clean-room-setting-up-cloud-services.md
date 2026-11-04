---
title: 数据净室——云存储工具设置指南
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-10-14T10:11:31Z'
  id: 4591167507217
  locale: zh-cn
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/zh-cn/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 概要：您可以设置一个或多个数据仓库（BigQuery、Snowflake）和/或云端数据存储桶（Amazon S3、GCS），用于与数据净室共享数据，并从其中接收报告。

<div id="overview" />

## 速览

使用数据净室（DCR）之前，您需要先设置以下内容：

* DCR读取您系统（自定义数据源）中的第一方数据时所使用的云服务/位置。这些位置信息用于创建**数据传入连接**。
* DCR处理完数据后传输报告时使用的云服务/位置。这些位置信息用于创建**数据传出连接**。

创建数据传入或传出连接时需要完成以下2个步骤：

* **第1步—** 启用DCR前，通过您选用的云服务平台完成相应的准备工作（即本文内容）。
* **第2步—** 通过AppsFlyer平台将云服务连接到DCR（参见<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-connections">数据净室——数据连接使用指南</Anchor>）。

<div id="note" />

> 📘 **注意**
>
> 如需全面了解AppsFlyer对自定义来源数据的要求，请参见<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#source-format">数据净室——数据连接使用指南</Anchor>：
>
> * 表格栏位*（适用于数据仓库中的数据源）*
> * 文件名称和格式*（适用于云存储桶中的数据源）*

<div id="supported-cloud-services" />

### 适配的云服务

DCR的数据传入和传出连接支持两种类型的云服务：

您可以使用这些服务中的任意一种或多种组合，来创建数据传入和传出连接。

<div id="important" />

> 🚧 **重要提示！**
>
> * 如果您需要在一个报告中使用多个自定义数据源，必须将这些数据源都放在云端数据存储桶中。
> * 使用Amazon S3或GCS上的同一个数据存储桶同时用于数据的传入和传出是非常普遍的做法。请务必按照[这种设置的专用说明](/docs/data-clean-room-setting-up-cloud-services#同时用于数据传入和传出的存储桶设置)进行操作。

<div id="setting-up-cloud-services-for-inbound-connections" />

## 向DCR传入数据的云服务连接设置

请根据下文各小节的说明，针对向DCR传入数据的云服务完成相应的前期配置。

<div id="data-warehouses--bigquery-and-snowflake" />

### 数据仓库：BigQuery和Snowflake

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**请注意：** 请注意：这部分流程必须由您的Google Cloud管理员完成。

**请按以下步骤创建数据集并向DCR授权：**

1. 登入Google Cloud Console。
2. 进入BigQuery页面。
3. 在新建或现有的Google Cloud项目中创建一个DCR专用的数据集：

   2. 选择**Create dataset**。

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. 界面会打开**右侧**边栏，请在其中输入数据集的名称，并根据实际需求选择其他选项。
      * 您可以选用任何一个适合您要求的名称，但其中仅可包含字母、数字和下划线（\_）。
        * **建议：** 推荐方法：建议在该数据集名称中使用可表示数据传入连接的字样。
      * 强烈建议您**不要**使用**Enable table expiration**选项，因为若选择了此选项，DCR就无法在表格过期后读取该数据源中的数据。
4. 向DCR开放该数据集的权限：

   2. 点击**Share**。
   4. `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. 在**Assign roles**部分中，选择**BigQuery > BigQuery Data Viewer**。

      <Image alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. 点击**保存**。
   7. 点击**CLOSE**，关闭右侧边栏。

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**请注意：** 请注意：以下流程必须由Snowflake账户管理员（**Accountadmin**）完成。

**请按以下方式创建DCR专用的私人共享：**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">登入相关的Snowflake账户</Anchor>，确保该账户中包含您需要与DCR共享的数据。
2. 将您的角色切换为**Accountadmin**。
3. 在左侧边栏中选择Private Sharing。
4. 界面打开的新页面中选择Shared By Your Account选项卡。

   snowflake\_private\_sharing.png
5. <Image alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. 选择您需要与DCR共享的表格和/或视图，然后点击Done。
7. 根据实际需求更改Secure Share Identifier并添加额外说明。
8. 在Add accounts in your region by name字段中根据您的Snowflake账户地区输入对应的AppsFlyer Snowflake账户： 

| Region | AppsFlyer账户 |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. 点击**Create Share**按钮。

</Accordion>

<div id="code-snippet" />

<div id="step-4" />

<div id="cloud-storage-buckets--amazon-s3-and-gcs" />

### 云端数据存储桶——Amazon S3和GCS

您可以使用一个或多个存储桶向DCR上传数据（Amazon S3和/或GCS）。但大部分情况下，在同一个云服务平台中使用单个数据存储桶是最为简便的设置。

* 您可以使用同一个存储桶来进行数据的传入和传出，具体操作请见[下文说明](/docs/data-clean-room-setting-up-cloud-services#同时用于数据传入和传出的存储桶设置)。

<span id="both-cloud-services"></span>在AWS和GCS上创建数据存储桶时都需要符合以下要求：

* 使用该存储桶必须仅供AppsFlyer数据净室专用，不能同时让其他服务方在其中写入数据。
* 授权您必须为AppsFlyer的DCR服务开放存储桶权限。各云平台的权限开放方式请见下文相关小节。
* **姓名：** 存储桶名称必须以af-dcr-开头
  * 示例：`af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>DCR命名规则以下命名规则适用于所有的DCR数据实体（即数据存储桶、文件夹和文件）：
  * 最多可包含1000个字符。
  * 有效字符：

    * 数字`(0-9)`（0-9）(0-9)，*不能作为名称中的第一个字符*
    * 分号`(-)`（-）(-)，不能作为名称中的第一个字符
    * 无效字符：
      * 空格
      * 所有其他符号和特殊字符
    * 具有特定用途的字符：
      * * 等号`(=)`（=）(=)，*仅在标识*<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">文件夹日期和版本时使用</Anchor>
        * 下划线`(_)`（\_）(\_)，*仅在标识*<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#file-format">分卷的GZIP文件</Anchor>*或为*<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESS文件</Anchor>命名时使用
        * 点`(.)`（.）(.)，*仅在文件名后缀前使用*`(.csv, .gzip)`（如.csv、.gzip）(.csv,>

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**请注意：** 请注意：这部分流程必须由您的AWS管理员完成。

**请按以下方式创建数据存储桶并为AppsFlyer开放权限：**

1. 登入AWS Console。
2. 进入“S3 service”部分。
3. 请按以下步骤创建存储桶：
   1. 点击**Create bucket**。
   2. 填写**Bucket name**，以`af-dcr-`af-dcr-af-dcr-或`af-datalocker-`af-datalocker-af-datalocker-开头，并按上文的[DCR命名要求](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements)在后面接上您为其赋予的名称。
   3. 点击**Create bucket**。
4. 为AppsFlyer开放存储桶权限：
   1. 选择您为DCR创建的存储桶。
   2. 进入**Permissions**选项卡。
   3. 在**Bucket policy**部分，点击**Edit**。   
      界面会打开Edit bucket policy/strong>窗口。
   4. 将以下代码片段复制粘贴到该窗口中：

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
              ]
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-dcr-mybucket",
              "arn:aws:s3:::af-dcr-mybucket/*"
            ]
          }
        ]
      }
      ```
5. 将上述代码中的*`af-dcr-mybucket`af-dcr-mybucketaf-dcr-mybucket*（两行代码）替换成该存储桶的名称。  
   **注意：** 替换代码中的存储桶名称时，切勿覆盖*第二行的存储桶名称里的*`/*`/*/*。
6. 点击**保存更改**。

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**请注意：** 请注意：这部分流程必须由您的Google Cloud管理员完成。

**请按以下方式创建数据存储桶并为AppsFlyer开放权限：**

1. 登入您的GCS Console。
2. 进入Cloud Storage Browser页面。
3. 请按以下步骤创建存储桶：
   1. 点击**Create bucket**。
   2. 请在**Create a bucket**（创建存储桶）页面中输入您的存储桶信息，包括
   3. 点击**下一步**。
   4. 点击**创建**。
4. 为AppsFlyer开放存储桶权限：
   1. 选择您为DCR创建的存储桶。
   2. 进入**授权**选项卡。
   3. 进入权限部分，点击 **+添加**。 **界面打开Add members窗口。**
   4. `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. 从**角色**列表中选择**云存储** > **存储工具管理员**。  

      ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
   6. 点击**保存**。

</Accordion>

<div id="setting-up-cloud-services-for-outbound-connections" />

## 向DCR传出数据的云服务连接设置

DCR会通过<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>向您选定的云服务平台发送DCR报告。

* **请注意：** 请注意：接收DCR报告不需要Data Locker的付费功能。如果您需要通过Data Locker接收其他的AppsFlyer报告，请联系您的CSM或发送邮件至[hello@appsflyer.com](mailto:hello@appsflyer.com)咨询详情。

我们可以向您云服务平台中的一个或多个位置发送DCR报告（无论您是否同时使用该平台向DCR传入数据）。请根据下文各小节的说明，为用于数据传出的云服务平台完成相应的前期配置。

<div id="data-warehouses--bigquery-and-snowflake-1" />

### 数据仓库：BigQuery和Snowflake

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

**请注意：** 请注意：这部分流程必须由您的Google Cloud管理员完成。

**请按以下方式创建数据集并向Data Locker开放权限：**

1. 登入Google Cloud Console。
2. 进入BigQuery页面。
3. 在新建或现有的Google Cloud项目中创建一个Data Locker专用的数据集：

   2. 选择**Create dataset**。

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. 界面会打开**右侧**边栏，请在其中输入数据集的名称，并根据实际需求选择其他选项。
      * 您可以选用任何一个适合您要求的名称，但其中仅可包含字母、数字和下划线（\_）。
        * **建议：** 推荐方法：建议在该数据集名称中使用可表示数据传出连接的字样。
      * 强烈建议您**不要**使用**Enable table expiration**选项，因为若选择了此选项，Data Locker就无法在表格过期后向该数据集中写入数据。
4. 向Data Locker开放该数据集的权限：

   2. 点击**Share**。
   4. `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. 在**Assign roles**部分中，选择**BigQuery > BigQuery Data Editor**。

      <Image alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. 点击**保存**。
   7. 点击**CLOSE**，关闭右侧边栏。

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

在Snowflake中完成数据传出连接的前期配置时，还需要<Anchor target="_blank" href="/marketers/zh/docs/data-clean-room-working-with-connections#snowflake-outbound">创建数据传出连接</Anchor>本身，这两个流程是同时进行的。

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs-1" />

### 云端数据存储桶——Amazon S3和GCS

为云端存储桶完成数据传出连接的前期配置与[传入连接](/docs/data-clean-room-setting-up-cloud-services#向dcr传入数据的云服务连接设置)的前期配置（包括针对两种云存储服务平台的操作说明）十分相似。

下文各小节说明仅适用于云存储桶的**数据传出连接**。

* 如果您使用同一个数据存储桶同时用于数据的传入和传出，请按[这种设置的专用说明](/docs/data-clean-room-setting-up-cloud-services#同时用于数据传入和传出的存储桶设置)进行操作。

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

请按说明创建[用于传入数据的Amazon S3存储桶](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound)（勿更变该流程）。

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

请按说明创建[用于传入数据的GCS存储桶](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound)。  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Accordion>

<div id="setting-up-the-same-cloud-storage-bucket-for-both-inbound-and-outbound-connections" />

## 同时用于数据传入和传出的存储桶设置

如前文所述，使用Amazon S3或GCS上的同一个数据存储桶同时用于数据的传入和传出是非常普遍的做法。

这部分的设置操作与[传入连接](/docs/data-clean-room-setting-up-cloud-services#向dcr传入数据的云服务连接设置)的前期配置非常相似，仅稍有不同。 配置操作的不同之处取决于您是否：

* 创建新桶，用于DCR的数据传出和传入；***还是***
* 将之前专用于Data Locker的存储桶进行修改，以用于DCR的数据传出和传入

这两种场景的操作说明请见下文对应的小节：

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

<div id="creating-a-new-bucket-for-inboundoutbound-connections" />

#### 创建新的数据存储桶用于数据的传入/传出

请按说明创建[用于传入数据的Amazon S3存储桶](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound)（勿更变该流程）。

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker" />

#### 对之前专用于Data Locker的存储桶进行修改

对之前专用于Data Locker的存储桶进行修改时需要更改存储桶权限（将访问权限同时开放给DCR和Data Locker）。

**请按以下方式更改存储桶权限：**

1. 登入AWS Console。
2. 进入“S3 service”部分。
3. 选择之前专用于Data Locker的存储桶。
4. 进入**Permissions**选项卡。
5. 在**Bucket policy**部分，点击**Edit**。   
   界面会打开Edit bucket policy/strong>窗口。
6. **将窗口中的内容替换为**以下代码段：

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```

   * 将上述代码中的*`af-dcr-mybucket`af-dcr-mybucketaf-dcr-mybucket*（两行代码）替换成该存储桶的名称。
   * **注意：** 替换代码中的存储桶名称时，切勿覆盖*第二行的存储桶名称里的*`/*`/*/*。
7. 点击**保存更改**。

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

<div id="creating-a-new-bucket-for-inboundoutbound-connections-1" />

#### 创建新的数据存储桶用于数据的传入/传出

请按说明创建[用于传入数据的GCS存储桶](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound)。  
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker-1" />

#### 对之前专用于Data Locker的存储桶进行修改

对之前专用于Data Locker的存储桶进行修改时需要更改存储桶权限（将访问权限同时开放给DCR和Data Locker）。

**请按以下方式更改存储桶权限：**

1. 登入您的GCS Console。
2. 进入Cloud Storage Browser页面。
3. 选择之前专用于Data Locker的存储桶。
4. 进入**授权**选项卡。
5. 进入权限部分，点击 **+添加**。  
   界面打开**Add members**窗口。
6. `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. 从**角色**列表中选择**云存储** > **存储工具管理员**。  

   ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
8. 点击**保存**。

</Accordion>

<div data-zendesk-anchors="overview=%E9%80%9F%E8%A7%88 h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=%E9%80%9F%E8%A7%88 h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=%E6%B3%A8%E6%84%8F supported-cloud-services=%E9%80%82%E9%85%8D%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1 h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=%E9%80%82%E9%85%8D%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1 h_01J6Y2P4CM8VDWCD5XH91DJPYX=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA setting-up-cloud-services-inbound=%E5%90%91dcr%E4%BC%A0%E5%85%A5%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE h_01J6Y2P4CM61DEXMWB626X25TT=%E5%90%91dcr%E4%BC%A0%E5%85%A5%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE data-warehouses-inbound=%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93bigquery%E5%92%8Csnowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93bigquery%E5%92%8Csnowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs h_01J6Y2P4CMCJDT2W6C52MF71TB=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound code-snippet=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound step-4=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs setting-up-cloud-services-outbound=%E5%90%91dcr%E4%BC%A0%E5%87%BA%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=%E5%90%91dcr%E4%BC%A0%E5%87%BA%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BA%91%E6%9C%8D%E5%8A%A1%E8%BF%9E%E6%8E%A5%E8%AE%BE%E7%BD%AE data-warehouses-outbound=%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93bigquery%E5%92%8Csnowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93bigquery%E5%92%8Csnowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6amazon-s3%E5%92%8Cgcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=%E5%90%8C%E6%97%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E4%BC%A0%E5%85%A5%E5%92%8C%E4%BC%A0%E5%87%BA%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%AE%BE%E7%BD%AE h_01J6Y2P4CN2ARMJKRSAFZNN59G=%E5%90%8C%E6%97%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E4%BC%A0%E5%85%A5%E5%92%8C%E4%BC%A0%E5%87%BA%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%AE%BE%E7%BD%AE h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BC%A0%E5%85%A5%E4%BC%A0%E5%87%BA h_01J6Y2P4CN216K0VZSWRP699TF=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BC%A0%E5%85%A5%E4%BC%A0%E5%87%BA modifying-an-existing-bucket-previously-used-only-for-data-locker=%E5%AF%B9%E4%B9%8B%E5%89%8D%E4%B8%93%E7%94%A8%E4%BA%8Edata-locker%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%BF%9B%E8%A1%8C%E4%BF%AE%E6%94%B9 h_01J6Y2P4CNDW888XTMKAMZAFCS=%E5%AF%B9%E4%B9%8B%E5%89%8D%E4%B8%93%E7%94%A8%E4%BA%8Edata-locker%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%BF%9B%E8%A1%8C%E4%BF%AE%E6%94%B9 h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BC%A0%E5%85%A5%E4%BC%A0%E5%87%BA-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=%E5%88%9B%E5%BB%BA%E6%96%B0%E7%9A%84%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8%E6%A1%B6%E7%94%A8%E4%BA%8E%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BC%A0%E5%85%A5%E4%BC%A0%E5%87%BA-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=%E5%AF%B9%E4%B9%8B%E5%89%8D%E4%B8%93%E7%94%A8%E4%BA%8Edata-locker%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%BF%9B%E8%A1%8C%E4%BF%AE%E6%94%B9-1 h_01J6Y2P4CNYCTVGN6CH0748S24=%E5%AF%B9%E4%B9%8B%E5%89%8D%E4%B8%93%E7%94%A8%E4%BA%8Edata-locker%E7%9A%84%E5%AD%98%E5%82%A8%E6%A1%B6%E8%BF%9B%E8%A1%8C%E4%BF%AE%E6%94%B9-1" />
