---
title: Data Locker - 云存储工具设置说明
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2026-10-14T10:09:29Z'
  id: 360017603577
  locale: zh-cn
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/zh-cn/articles/360017603577
---
> **概要**：您可以通过自己的云存储工具来获取Data Locker的数据，本文说明了其中涉及的云存储工具设置方式。目前AppsFlyer支持的云存储平台包括GCS、AWS、BigQuery以及Snowflake。

您可以使用Data Locker将数据实时传输到您指定的自有存储工具中，无论是数据存储桶还是数据仓库都适用。下文针对这两类工具分别解释了设置流程，请根据您的实际使用场景参考对应的说明。

<div id="bucket-cloud-storage" />

## 云端数据存储

<div id="gcs-storage" />

<Accordion title="GCS存储">

开始之前，请注意以下事项：

* 本节所述流程必须由您的Google Cloud账户管理员完成。
* 在数据写入存储桶的25小时之后，您就可以将相关文件从Data Locker中删除，请勿提前删除。

**GCS账户管理员须知**

Data Locker是AppsFlyer提供的一种解决方案，用于将数据实时传输到您的存储工具中。

**配置要求**

* 创建一个专供 Data Locker 使用的 GCS 存储桶。也就是说没有其他服务商平台会在这个存储桶中写入数据。
* 推荐存储桶名称：`af-datalocker`。
* 按以下流程为Data Locker开放权限。

**请按以下方式为Data Locker开放权限：**

注意：请使用您为Data Locker创建的存储桶名称来替换掉流程说明中的示例名称`data-locker-example`。

1. 登入您的GCS Console。
2. 进入**Storage** > **Storage** browser。

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png" />
3. 选择您之前创建的Data Locker专用存储桶，例如`data-locker-example`。
4. 进入**授权**选项卡。
5. 点击 **+Add**。  
   界面会打开Add members窗口。
6. 请完成以下操作：
   1. 将以下代码片段复制粘贴到**New members**字段中。

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **选择一个角色**（Role）：**Cloud storage** > **Storage Object Admin**。

      <Image align="center" alt="mceclip0.png" src="https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png" />
7. 点击**Save**。

</Accordion>

<div id="aws-storage" />

<Accordion title="AWS存储">

开始之前，请注意以下事项：

* 本节所述流程必须由您的AWS账户管理员完成。
* 在数据写入存储桶的25小时之后，您就可以将相关文件从Data Locker中删除，请勿提前删除。

**AWS账户管理员须知**

Data Locker是AppsFlyer提供的一种解决方案，用于将数据实时传输到您的存储工具中。

**配置要求**

* 创建一个名为 af-datalocker -mybucket 的 AWS 存储桶。请注意，这里的存储桶名称必须带有前缀af-datalocker-，后缀则为自定义文本。
* 建议名称：af-datalocker-yyyy-mm-dd-hh-mm-free-text。其中yyyy-mm-dd-hh-mm是当前日期和时间，后接自定义文本，如下图所示。

**AWS界面截屏**

<Image align="center" alt="MyBucket.jpg" src="https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg" />

存储桶创建完毕后，请按以下步骤向AppsFlyer开放权限。

**请按以下方式创建数据存储桶并为AppsFlyer开放权限：**

1. 登入AWS Console。
2. 进入“S3 service”部分。
3. **请按以下步骤创建存储桶**：
   1. 点击**Create bucket**。
   2. 按以下方式填写**存储桶名称**：以`af-datalocker-`前缀开头，然后按上文说明添加相应文本。
   3. 选择一个[受支持的AWS](#支持的aws区域)区域。
   4. 点击**Create bucket**。
4. **向AppsFlyer授权的方式如下：**
   1. 选择相关存储桶。
   2. 进入**Permissions**选项卡。
   3. 在**Bucket policy**部分，点击**Edit**。   
      界面显示存储桶政策窗口。
   4. 将以下代码片段复制粘贴到该窗口中：

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. 请将上述代码片段中的`af-datalocker-my-bucket`替换为您创建的存储桶名称。
6. 【可选】添加KMS加密存储桶的配置支持。设置方式为：进入**Key Policy**部分，选择Switch to policy view，并将以下代码片段复制粘贴到Statement array中。

   ```json
   {
         "Sid": "Allow use of the key",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
   ```
7. 点击**Save changes**。
8. 完成<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#data-locker报告设置">Data Locker设置流程</Anchor>。

<div id="supported-aws-regions" />

#### **支持的AWS区域**

Data Locker支持以下AWS区域：

* 亚太地区（东京）： `ap-northeast-1`
* 亚太地区（首尔）： `ap-northeast-2`
* 亚太地区（孟买）： `ap-south-1`
* 亚太地区（新加坡）： `ap-southeast-1`
* 亚太地区（悉尼）： `ap-southeast-2`
* 加拿大（中央）： `ca-central-1`
* 欧盟（法兰克福）： `eu-central-1`
* 欧盟（爱尔兰）： `eu-west-1`
* 欧盟（伦敦）： `eu-west-2`
* 南美洲（圣保罗）： `sa-east-1`
* 美国东部（弗吉尼亚州北部）：`us-east-1`
* 美国东部（俄亥俄州）：`us-east-2`
* 美国西部（加利福尼亚州北部）：`us-west-1`
* 美国西部（俄勒冈州）：`us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Azure 存储">

开始之前，请注意以下事项：

* 本节所述流程必须由您的Azure Cloud账户管理员完成。
* 在数据写入存储桶的25小时之后，您就可以将相关文件从Data Locker中删除，请勿提前删除。

**Azure账户管理员须知**

Data Locker是AppsFlyer提供的一种解决方案，用于将数据实时传输到您的云存储账户中。

**请按以下方式为Data Locker配置一个云存储账户：**

1. [从您的Azure后台进入](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) <Image alt="Azure storage accounts" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />（存储账户）。然后点击**predict\_dashboard\_plus\_symbol.pngCreate ，生成一个新的云存储账户，专用于获取AppsFlyer侧的数据。**
2. **从Basic选项卡进入Project details**，根据实际使用场景从下拉菜单中选择一项：
   1. **Subscription**（订阅）。
   2. **Resource Group**（资源组）。  
      可选：如果没有现行的资源组，可以点击**Create new**，然后创建一个资源组。
3. 在**Instance details**下：
   1. 输入相关**Storage account name**（存储账户名称）。
   2. 从下拉菜单中选择一个**Region**（地区）。
4. 点击**Next：Advanced >**
5. 在**Security**选项卡中，选择**Enable Hierarchical namespace**。
6. **点击Review -> Create**。
7. 部署完成后，返回到您的[Azure 存储帐户](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)并选择新创建的帐户。
8. 进入**Access keys**部分，复制**storage account name**（存储账户名称）以及一个**key**（密钥）。
9. 进入**Storage browser -> Blob containers**，然后点击<Image alt="" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />alt**predict\_dashboard\_plus\_symbol.png**Add container（添加容器）。
   1. 为这个新建的container设置一个**名称**。
   2. 点击**Create**。
10. [启用完毕后，请从AppsFlyer面板进入Data Locker **-> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />新连接**](https://hq1.appsflyer.com/datalocker/overview)。
11. 在新连接创建窗口中：
    1. 为连接命名。
    2. **选择Azure Blob。**
    3. **在存储桶名称字段中输入您的AzureContainer名称（即您在第9步中使用的名称）。**
    4. **输入您在第8步中复制的Storage account name（存储账户名称）**。
    5. **输入您在第8步中复制的key（密钥）。**
    6. 点击**测试连接**。
    7. 保存

</Accordion>

<div id="yandex" />

<Accordion title="【Beta】Yandex云存储">

开始之前，请注意以下事项：

* 本节所述流程必须由您的Yandex Cloud账户管理员完成。
* 在数据写入存储桶的25小时之后，您就可以将相关文件从Data Locker中删除，请勿提前删除。

**Yandex账户管理员须知**

Data Locker是AppsFlyer提供的一种解决方案，用于将数据实时传输到您的存储工具中。

**请按以下方式创建数据存储桶并向Data Locker开放权限：**

1. 从<Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud后台</Anchor>进入**Service Accounts**（服务账户）选项卡，然后点击**Create service account**。
2. 为该服务账户命名，如`af-datalocker`。
3. 为该服务帐户创建static access key（静态访问密钥）。在该服务帐户的配置窗口中完成以下操作：
   1. 点击**Create a new key**（创建一个新密钥）。
   2. 选择**Create static access key**。
   3. 保存这个key的**Key ID**和**Secret key**。
4. 为您新建的服务账户开放**storage.editor**权限。
   1. 进入存储桶设置中的**Access Bindings**部分，然后点击**Assign bindings**。
   2. 为您新建的服务账户添加**storage.editor**角色，然后点击**保存**。
5. 请让您的AppsFlyer CSM为您在Data Locker中启用Yandex。
6. 启用完毕后，请使用您之前保存的Key ID和Secret Key完成<Anchor target="_blank" href="/marketers/zh/docs/data-locker-for-marketers#set-up-data-locker">Data Locker设置流程</Anchor>。

</Accordion>

<div id="data-warehouse-cloud-storage" />

## 云端数据仓库

<div id="bigquery" />

<Accordion title="BigQuery">

本节所述流程必须由您的BigQuery账户管理员完成。

**BigQuery账户管理员须知**

Data Locker是AppsFlyer提供的一种解决方案，用于将数据实时传输到您的存储工具中。

**配置要求**

* 创建BigQuery数据集：

**请按以下方式创建一个BigQuery数据集：**

1. 在BigQuery中创建一个Project（项目），也可使用现有项目。
2. 在该项目中，点击**CREATE DATASET**。[![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. 为该数据集设置一个合适的ID。

   <div id="note" />

   > 📘 **注意**
   >
   > 目标项目或数据集必须绑定有效的计费账号。若无计费账号，Data Locker将无法在BigQuery目标位置中创建或写入表格，连接设置过程可能会失败。

4. 为AppsFlyer开放该数据集的访问权限。<Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">详情请见</Anchor><Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">BigQuery说明文档</Anchor>。
   * 在**Add principal**部分，请使用以下AppsFlyer用户信息：[datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * 在**Assign roles**部分，请选择“BigQuery Data Editor”，
5. 根据您的实际需求完成其余部分的设置。

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

将Data Locker连接到您的Snowflake账户后，就可以将相关数据发送到Snowflake。这些数据会被保存在您指定的云存储空间中，持续供您使用。

**BI开发人员的注意事项**

* 这里的数据时效性与存储桶的时效性一致。
* 这里的表格及字段列结构与Data Locker数据桶中直接提供的数据结构相同。
* 随着 Snowflake 共享中行的增加，`_ingestion_time`该列以系统本地时区（而非 UTC）填充。为了确保数据各行的唯一性，并避免多次接入同一行数据，请按以下方式操作：
  1. 对于已接入的表格，分别保存其各自的`max_ingestion_time`。
  2. 每次接入数据时，仅取用`_ingestion_time > max_ingestion_time`的数据行。

请按照以下步骤将 Snowflake 连接到 Data Locker。

<div id="snowflake-connector-procedures" />

#### **Snowflake数据连接的设置流程**

**请按以下方式获取您的Snowflake账户ID及地区信息**：

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">登入您的Snowflake账户</Anchor>。
2. 在菜单栏中选择您的用户名称。  
   界面会显示您的账户ID和地区信息。

   <Image align="center" alt="Snowflake 账户详情" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />

**请按以下方式将Data Locker连接到Snowflake**：

1. 从AppsFlyer后台进入**报告** > **Data Locker**。
2. 选择Snowflake。
3. 使用您之前从 Snowflake 收到的信息输入 Snowflake 区域和账户定位符。
4. 点击**保存**。

**在Snowflake的相关Share中创建一个数据库**：

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">登入您的Snowflake账户</Anchor>。
2. 将您的角色切换为**Accountadmin**。详情请见Snowflake的<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share">数据库创建说明</Anchor>文档。
3. 选择**Shares**。
4. 选择 AppsFlyer 共享，例如 APPSFLYER\_ACC\_XXX\_DATA\_LOCKER。
5. 点击**Create Database from Secure Share**，然后根据您的实际情况填写详细信息。**注意事项**！由于共享数据库中的数据可用时长有限（目前为14天），因此请务必将共享数据库中的数据导入到您的表格中。
6. 数据库中将显示导入的表格。这里的表格名称和结构与Data Locker存储桶中的数据一致。

</Accordion>

<div id="traits-and-limitations" />

## 特点与局限性

| 特点 | 说明 |
| --- | --- |
| AppsFlyer云连接 | 报告无法以未压缩的方式存储 |
| BigQuery数据集位置变更 | 如果在BigQuery中更改了数据集位置，需重新保存连接设置。由于AppsFlyer连接配置并无实际变化，“Save” 按钮默认禁用。如需启用该按钮，可先进行一次临时修改并保存，再改回原设置并再次保存。 |
| Snowflake支持区域 | **AWS支持区域：**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-south-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**AWS支持区域：**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>西欧</li><li>west-us-2</li></ul>**GCP支持区域：**<ul><li>有限支持。请联系AppsFlyer支持团队，确认您所在区域是否可用。</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8 h_01HE2SPKYZWFXA63YD5NK4KJRD=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E5%AD%98%E5%82%A8 h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=%E6%94%AF%E6%8C%81%E7%9A%84aws%E5%8C%BA%E5%9F%9F h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=%E6%94%AF%E6%8C%81%E7%9A%84aws%E5%8C%BA%E5%9F%9F %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93 h_01HE2SPKYZ77X8WP9ZNRB1D05B=%E4%BA%91%E7%AB%AF%E6%95%B0%E6%8D%AE%E4%BB%93%E5%BA%93 h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=%E6%B3%A8%E6%84%8F h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=snowflake%E6%95%B0%E6%8D%AE%E8%BF%9E%E6%8E%A5%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B h_01HE2SPKYZ11B1MJYX2HRCS07D=snowflake%E6%95%B0%E6%8D%AE%E8%BF%9E%E6%8E%A5%E7%9A%84%E8%AE%BE%E7%BD%AE%E6%B5%81%E7%A8%8B traits-and-limitations=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7 h_01KYVRP8CVMD01EZY5561W2RCJ=%E7%89%B9%E7%82%B9%E4%B8%8E%E5%B1%80%E9%99%90%E6%80%A7" />
