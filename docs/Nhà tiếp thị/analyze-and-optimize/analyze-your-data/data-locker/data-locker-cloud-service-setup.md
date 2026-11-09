---
title: Data Locker—thiết lập dịch vụ đám mây
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
  edited_at: '2023-11-08T09:57:04Z'
  id: 360017603577
  locale: vi
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/vi/articles/360017603577
---
> **Khái quát**: Thiết lập dịch vụ đám mây của bạn để nhận dữ liệu từ Data Locker: GCS, AWS, BigQuery hoặc Snowflake.

Data Locker cho phép bạn truyền dữ liệu đến giải pháp lưu trữ mà bạn đã chọn và sở hữu, cho dù đó là bộ chứa hay kho dữ liệu. Thiết lập dịch vụ đám mây bằng một trong các quy trình sau.

<div id="supported-aws-regions" />

<div id="bucket-cloud-storage" />

## Bộ lưu trữ đám mây có bộ chứa

<div id="gcs-storage" />

<Accordion title="Bộ lưu trữ GCS">

* Quy trình trong phần này cần được thực hiện bởi quản trị viên Google Cloud của bạn.
* Bạn có thể xóa các tệp tin khỏi Data Locker sau 25 giờ trở lên kể từ thời điểm ghi. Không xóa các tệp tin trước lúc đó.

**Thông tin dành cho quản trị viên GCS**

Data Locker là giải pháp AppsFlyer để truyền dữ liệu đến bộ lưu trữ.

**Yêu cầu**

* Tạo một bộ chứa trên GCS để sử dụng riêng Data Locker. Sử dụng riêng nghĩa là không có dịch vụ nào khác ghi dữ liệu vào bộ chứa.
* Tên bộ chứa được đề xuất: `af-datalocker`.
* Cấp quyền cho Data Locker thông qua quy trình sau.

**Cách cấp quyền cho Data Locker:**

Trong quy trình này, thay thế `data-locker-example` bằng tên của bộ chứa mà bạn đã tạo trước đó cho Data Locker.

1. Đăng nhập vào bảng điều khiển GCS của bạn.
2. Đi đến **Storage** > **Storage** **browser**.  

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png" />
3. Chọn bộ chứa bạn đã tạo trước đó, ví dụ `data-locker-example`.
4. Đi tới tab **Permissions** (Quyền).
5. Nhấp vào **+Add**.  
   Cửa sổ Add members sẽ mở ra.
6. Hoàn thành như sau:
   1. **New members**, hãy dán đoạn mã sau.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Chọn một vai trò**: **Cloud storage** > **Storage Object Admin**.   

      <Image align="center" alt="mceclip0.png" src="https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png" />
7. Nhấp vào **Save** (Lưu).

</Accordion>

<div id="aws-storage" />

<Accordion title="Bộ lưu trữ AWS">

* Quy trình trong phần này phải do quản trị viên AWS của bạn thực hiện.
* Bạn có thể xóa các tệp tin khỏi Data Locker sau 25 giờ trở lên kể từ thời điểm ghi. Vui lòng không xóa các tệp tin trước lúc đó.

**Thông tin dành cho Quản trị viên AWS**

Data Locker là giải pháp AppsFlyer để truyền dữ liệu đến bộ lưu trữ.

**Yêu cầu**

* Tạo một bộ chứa AWS có tên af-datalocker-mybucket. Tiền tố af-datalocker- là bắt buộc. Hậu tố là văn bản tự do.
* Chúng tôi đề xuất theo dạng af-datalocker-yyyy-mm-dd-hh-mm-free-text. Trong đó yyyy-mm-dd-hh-mm là ngày và giờ hiện tại, và bạn thêm bất kỳ văn bản nào khác mà bạn muốn như được mô tả trong hình bên dưới.

**Giao diện người dùng trong bảng điều khiển AWS**

<Image align="center" alt="MyBucket.jpg" src="https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg" />

Sau khi tạo bộ chứa, hãy cấp quyền cho AppsFlyer bằng quy trình sau đây.

**Để tạo bộ chứa và cấp quyền cho AppsFlyer:**

1. Đăng nhập vào giao diện điều khiển AWS.
2. Đi tới dịch vụ S3.
3. **Để tạo bộ chứa**:
   1. Nhấp vào **Create bucket** (Tạo bộ chứa).
   2. Hoàn thành **Bucket name** (Tên bộ chứa) như sau: Bắt đầu bằng `af-datalocker-` và sau đó thêm bất kỳ văn bản nào khác như đã mô tả trước đó.
   3. Nhấp vào **Create bucket** (Tạo bộ chứa).
4. **Để cấp quyền cho AppsFlyer:**
   1. Chọn bộ chứa.
   2. Đi tới tab **Permissions** (Quyền).
   3. Trong phần **Bucket policy** (Chính sách bộ chứa), hãy nhấp vào **Edit** (Chỉnh sửa).   
      Cửa sổ Chính sách bộ chứa mở ra.
   4. Dán đoạn mã sau vào cửa sổ.

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
5. Trong đoạn mã, thay thế `af-data-locker-my-bucket` bằng tên bộ chứa bạn đã tạo.
6. [Tùy chọn] Thêm hỗ trợ cho các bộ chứa được mã hóa KMS. Để làm được như vậy, trong phần **Key Policy**, chọn **Switch to policy view** và dán đoạn mã sau vào **mảng Statement.**  

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
7. Nhấp vào **Save changes** (Lưu thay đổi).
8. Hoàn thành <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers#set-up-data-locker">quy trình Thiết lập Data Locker.</Anchor>

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="[Beta] Bộ nhớ Azure">

* Quy trình trong phần này cần được thực hiện bởi quản trị viên Azure Cloud của bạn.
* Bạn có thể xóa các tệp tin khỏi Data Locker sau 25 giờ trở lên kể từ thời điểm ghi. Không xóa các tệp tin trước lúc đó.

**Thông tin dành cho quản trị viên Azure**

Data Locker là giải pháp AppsFlyer để truyền dữ liệu tới tài khoản lưu trữ của bạn.

**Để xác định tài khoản lưu trữ cho Data Locker:**

1. Hãy truy cập [Tài khoản lưu trữ Azure](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)
2. Tạo tài khoản lưu trữ mới để nhận Dữ liệu Appsflyer của bạn
3. Tùy chọn: Tạo nhóm nguồn mới (nếu chưa có nhóm nguồn)
4. Chọn đăng ký, đặt tên cho tài khoản lưu trữ mới của bạn và chọn khu vực có liên quan của bạn
5. Kích hoạt vùng tên phân cấp
6. Liên hệ với CSM của bạn để bật Azure trong Data Locker (sau khi bật, bạn sẽ cần tên tài khoản lưu trữ nêu trên và mã khóa để nhập vào trình hướng dẫn kết nối mới của Data Locker)

</Accordion>

<div id="yandex" />

<Accordion title="[Thử nghiệm] Bộ lưu trữ Yandex Cloud">

* Quy trình trong phần này cần được thực hiện bởi quản trị viên Yandex Cloud của bạn.
* Bạn có thể xóa các tệp tin khỏi Data Locker sau 25 giờ trở lên kể từ thời điểm ghi. Không xóa các tệp tin trước lúc đó.

**Thông tin dành cho quản trị viên Yandex**

Data Locker là giải pháp AppsFlyer để truyền dữ liệu đến bộ lưu trữ.

**Để tạo bộ chứa và cấp quyền cho Data Locker:**

1. Trong <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud console</Anchor> của bạn, đi đến thẻ **Service Accounts** và nhấp vào **Create service account**.
2. Đặt tên cho tài khoản dịch vụ, ví dụ: `af-datalocker`.
3. Tạo khóa truy cập tĩnh cho tài khoản dịch vụ. Trong tài khoản dịch vụ:
   1. Nhấp vào **Create a new key**.
   2. Chọn **Create static access key**.
   3. Lưu **Key ID** và **Secret Key**.
4. Cấp quyền **storage.editor** cho tài khoản dịch vụ mới của bạn.
   1. Trong cài đặt bộ chứa của bạn, đi đến **Access Bindings** và nhấp vào **Assign bindings**.
   2. Đối với tài khoản dịch vụ mới của bạn, hãy thêm vai trò **storage.editor** và nhấp vào **Save**.
5. Liên hệ với CSM AppsFlyer của bạn để bật Yandex trong Data Locker.
6. Sau khi được bật, hãy sử dụng key ID và secret key trong quá trình <Anchor target="_blank" href="/marketers/vi/docs/data-locker-for-marketers#set-up-data-locker">thiết lập Data Locker</Anchor>.

</Accordion>

<div id="note" />

<div id="data-warehouse-cloud-storage" />

## Bộ lưu trữ đám mây kho dữ liệu

<div id="bigquery" />

<Accordion title="BigQuery">

Quy trình trong phần này cần được thực hiện bởi quản trị viên BigQuery của bạn.

**Thông tin dành cho Quản trị viên BigQuery**

Data Locker là giải pháp AppsFlyer để truyền dữ liệu đến bộ lưu trữ.

**Yêu cầu**

* <span id="step-1-create-a-bigquery-dataset"></span>Tạo bộ dữ liệu BigQuery

**Để tạo bộ dữ liệu BigQuery:**

1. Trong BigQuery, hãy tạo dự án hoặc sử dụng dự án hiện có.
2. Trong dự án, nhấp vào **CREATE DATASET**.

   <Image align="center" alt="GCSCreateDataSEt_1_.png" src="https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png" />
3. Cung cấp cho bộ dữ liệu một ID phù hợp.
4. Cấp cho AppsFlyer quyền truy cập vào bộ dữ liệu. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Xem hướng dẫn Big Query</Anchor>
   * Đối với **Add principal**, sử dụng người dùng AppsFlyer sau: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * Đối với **Assign roles**, hãy chọn Trình chỉnh sửa Dữ liệu BigQuery.
5. Hoàn thành các cài đặt còn lại theo yêu cầu.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Kết nối Data Locker với tài khoản Snowflake của bạn. Bằng cách đó, dữ liệu được gửi đến Snowflake và tiếp tục khả dụng trong bộ lưu trữ đám mây mà bạn đã chọn.

**Những điều cần lưu ý dành cho các nhà phát triển BI**

* Tốc độ cập nhật dữ liệu bằng với tốc độ cập nhật dữ liệu được cung cấp trong bộ chứa.
* Cấu trúc bảng và cột của dữ liệu tương đương với cấu trúc được tìm thấy trong dữ liệu có sẵn trực tiếp từ bộ chứa Data Locker.
* Khi các hàng được thêm vào phần chia sẻ Snowflake, cột `_ingestion_time` sẽ được điền. Để đảm bảo tính duy nhất của hàng và ngăn việc nhập cùng một hàng nhiều lần:
  1. Lưu `max_ingestion_time` đối với mỗi bảng được nhập.
  2. Mỗi lần bạn chạy quy trình nhập, chỉ nhập những hàng có `_ingestion_time > max_ingestion_time`

Hoàn thành các quy trình sau để kết nối Snowflake với Data Locker.

<div id="traits-and-limitations" />

<div id="snowflake-connector-procedures" />

#### **Quy trình kết nối bộ kết nối Snowflake**

**Để nhận ID tài khoản và khu vực Snowflake của bạn**:

1. Trong Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">đăng nhập vào tài khoản Snowflake của bạn</Anchor>.
2. Trong thanh menu, chọn tên của bạn.  
   ID tài khoản của bạn và khu vực sẽ được hiển thị.  

   <Image align="center" alt="SnowflakeAccountId.png" src="https://files.readme.io/146dc699865a8a72780ba409d37ca1206767943e27221bec635b9fb49ffc7223-4412207884433.png" />

**Cách kết nối Data Locker với Snowflake**:

1. Trong AppsFlyer, đi đến **Integration** > **Data Locker**.
2. Chọn Snowflake.
3. Nhập vào **Snowflake region** và **Snowflake account ID** thông tin bạn đã nhận được trước đó từ Snowflake.
4. Nhấp vào **Save** (Lưu).

**Cách** **tạo cơ sở dữ liệu từ một chia sẻ trong Snowflake**:

1. Trong Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">đăng nhập vào tài khoản Snowflake của bạn</Anchor>.
2. Chuyển đổi vai trò sang **Accountadmin**. Xem <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share.">Tạo cơ sở dữ liệu từ một chia sẻ.</Anchor>
3. Chọn **Shares**.
4. Chọn chia sẻ AppsFlyer. Ví dụ: APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Nhấp vào **Create Database from Secure Share** và điền các thông tin chi tiết được yêu cầu. **Lưu ý**! Bạn phải tải dữ liệu từ cơ sở dữ liệu chung vào các bảng của mình vì dữ liệu trong cơ sở dữ liệu chung chỉ sẵn dùng trong một khoảng thời gian giới hạn (hiện tại là 14 ngày).
6. Trong cơ sở dữ liệu của bạn, các bảng đã nhập sẽ được hiển thị. Tên và cấu trúc bảng tương đương với tên và cấu trúc trong bộ chứa Data Locker.

</Accordion>

<div data-zendesk-anchors="bucket-cloud-storage=b%E1%BB%99-l%C6%B0u-tr%E1%BB%AF-%C4%91%C3%A1m-m%C3%A2y-c%C3%B3-b%E1%BB%99-ch%E1%BB%A9a h_01HE2SPKYZWFXA63YD5NK4KJRD=b%E1%BB%99-l%C6%B0u-tr%E1%BB%AF-%C4%91%C3%A1m-m%C3%A2y-c%C3%B3-b%E1%BB%99-ch%E1%BB%A9a h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=b%E1%BB%99-l%C6%B0u-tr%E1%BB%AF-%C4%91%C3%A1m-m%C3%A2y-kho-d%E1%BB%AF-li%E1%BB%87u h_01HE2SPKYZ77X8WP9ZNRB1D05B=b%E1%BB%99-l%C6%B0u-tr%E1%BB%AF-%C4%91%C3%A1m-m%C3%A2y-kho-d%E1%BB%AF-li%E1%BB%87u h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery step-1%E2%80%94create-a-bigquery-dataset=step-1-create-a-bigquery-dataset h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=quy-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-b%E1%BB%99-k%E1%BA%BFt-n%E1%BB%91i-snowflake h_01HE2SPKYZ11B1MJYX2HRCS07D=quy-tr%C3%ACnh-k%E1%BA%BFt-n%E1%BB%91i-b%E1%BB%99-k%E1%BA%BFt-n%E1%BB%91i-snowflake" />
