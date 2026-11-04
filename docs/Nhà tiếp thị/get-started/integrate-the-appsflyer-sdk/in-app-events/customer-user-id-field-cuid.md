---
title: Trường Customer User ID (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2023-11-19T08:40:03Z'
  id: 207032016
  locale: vi
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/vi/articles/207032016
---
> **Khái quát:** CUID cho phép bạn nhóm các sự kiện của cùng một người dùng trên các thiết bị, nguồn truyền thông hoặc kênh khác nhau.

<div id="what-is-cuid" />

## **CUID là gì?**

Customer User ID (CUID) là mã định danh người dùng duy nhất. Thường được chủ sở hữu ứng dụng tạo và thiết lập tại thời điểm đăng ký người dùng. CUID cho phép chủ sở hữu ứng dụng theo dõi hành trình của người dùng trên các thiết bị khác nhau.

<div id="example" />

> 📄 **Ví dụ**
>
> Người dùng có hai thiết bị trở lên có cùng CUID trong một ứng dụng. Mỗi lần người dùng thực hiện một sự kiện trên thiết bị di động hoặc máy tính để bàn, sự kiện được thu lại cùng với CUID. Điều này cho phép nhà quảng cáo kết hợp dữ liệu của các thiết bị vào một chế độ xem người dùng tổng thể.
>
> Một số trường hợp sử dụng:
>
> * Các giao dịch mua trong ứng dụng được thực hiện bởi cùng một người dùng trong cùng một ứng dụng nhưng trên nhiều thiết bị (điện thoại, máy tính bảng, TV, máy tính để bàn) có thể được kết hợp trong một chế độ xem.
> * Hiệu suất của người dùng trong trò chơi được cài đặt trên nhiều nền tảng (máy tính để bàn, thiết bị di động, TV) có thể được chia sẻ trên các nền tảng này để đạt được trải nghiệm người dùng toàn diện.

<div id="setting-the-cuid" />

## **Cài đặt CUID**

Bạn nên đặt CUID càng sớm càng tốt trong quy trình khởi tạo SDK để số lượng sự kiện nhận được liên kết CUID nhiều nhất có thể.

<Tabs>
<Tab title="Android native">

Sau khi nhận được, bạn có thể thiết đặt CUID bằng cách gọi ra lệnh `setCustomerUserID`. CUID chỉ có thể được liên kết với các sự kiện trong ứng dụng xảy ra sau thời điểm thiết đặt. Do đó, sự kiện cài đặt sẽ không được liên kết với CUID khi gọi lệnh `start` trước lệnh `setCustomerUserID`.

<div id="associate-the-cuid-with-the-install-event" />

### **Liên kết CUID với sự kiện cài đặt**

Nếu việc liên kết sự kiện cài đặt với CUID là quan trọng đối với bạn, hãy thiết đặt CUID trước khi gọi lệnh `start`.

**Quan trọng:** Hãy nhớ rằng việc thiết đặt CUID trước khi gọi lệnh  `start` có thể ngăn chặn SDK gửi sự kiện cài đặt và do đó ngăn quá trình phân bổ diễn ra. Ví dụ: quá trình phân bổ có thể xảy ra khi người dùng khởi chạy ứng dụng lần đầu tiên, rồi sau đó thoát ứng dụng trước khi SDK có thể thiết đặt CUID.

Trong Android, phương thức `start` và thiết lập CUID có thể được thực thi từ lớp `Application` chung hoặc lớp `Activity`, tùy thuộc vào cách triển khai ứng dụng. Để biết thêm thông tin, hãy tham khảo <Anchor target="_blank" href="/marketers/vi/docs/basic-sdk-integration-guide#select-in-what-class-to-start-the-sdk">Chọn bắt đầu SDK trong lớp nào</Anchor>.

<div id="if-the-sdk-starts-in-the-application-class" />

#### Nếu SDK bắt đầu trong lớp Application

Nếu bạn muốn liên kết CUID với sự kiện cài đặt  khi bắt đầu từ lớp `Application`chung, hãy đảm bảo trì hoãn việc gửi sự kiện cài đặt bằng phương thức `waitForCustomerUserId` . Phương thức này đặt SDK ở chế độ chờ cho đến khi CUID được thiết đặt xong.

Lưu ý: Nếu vì lý do nào đó mà không cài đặt được CUID, thì SDK sẽ ở chế độ chờ và không gửi bất kỳ sự kiện nào.

<div id="if-the-sdk-starts-in-an-activity-class" />

#### Khi SDK bắt đầu trong một lớp Activity

Nếu muốn liên kết CUID với sự kiện cài đặt khi bắt đầu từ một lớp `Activity`, bạn không cần trì hoãn việc gửi sự kiện cài đặt. Chỉ cần gọi ra lệnh `setCustomerUserId` trước khi gọi lệnh `start`.

<div id="developer-instructions" />

#### HƯỚNG DẪN DÀNH CHO NHÀ PHÁT TRIỂN

Thông báo nhà phát triển về những điều sau:

* Sử dụng lệnh `waitForCustomerUserId` nếu SDK bắt đầu trong lớp `Application` chung
* Liên kết cho nhà phát triển:
  * Nếu bạn muốn liên kết CUID với sự kiện cài đặt, hãy xem [tại đây](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event).

</Tab>

<Tab title="iOS native">

Sử dụng phương thức `customerUserId` để đặt CUID. Vị trí của `customerUserId` tương quan với phương thức `start` xác định sự kiện nào có thể được liên kết với CUID.

* Nếu gọi `customerUserId` trước khi gọi `start`, CUID được liên kết với lượt cài đặt và các sự kiện trong ứng dụng sau
* Nếu gọi sau phương thức `start`, CUID chỉ được liên kết với các sự kiện được ghi nhận sau khi đặt CUID.

#### HƯỚNG DẪN DÀNH CHO NHÀ PHÁT TRIỂN

Hãy giới thiệu nhà phát triển của bạn tới phần [Thiết lập Customer User ID](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id) trong Trung tâm Nhà phát triển.

</Tab>

<Tab title="Unity">

#### HƯỚNG DẪN DÀNH CHO NHÀ PHÁT TRIỂN

Hãy giới thiệu nhà phát triển của bạn tới phần [Thiết lập Customer User ID](https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id) trong Trung tâm Nhà phát triển.

</Tab>
</Tabs>

<div id="cuid-and-privacy" />

## **CUID và quyền riêng tư**

AppsFlyer coi trọng và tôn trọng quyền riêng tư của người dùng và [không cho phép thu thập hoặc chuyển dữ liệu cá nhân nhạy cảm sang nền tảng AppsFlyer.](https://www.appsflyer.com/services-privacy-policy/#engagementinformation)

Để đảm bảo quyền riêng tư của người dùng, không được thiết kế CUID bằng thông tin định danh trực tiếp người dùng. Các thông tin này bao gồm số an sinh xã hội hoặc số nhận dạng quốc gia.

Ngoài ra, nếu CUID đã đặt chứa địa chỉ email hoặc số điện thoại của người dùng,  thông tin đó phải luôn ở dạng đã băm khi gửi tới AppsFlyer. Nghiêm cấm gửi CUID chưa băm có chứa dữ liệu cá nhân tới AppsFlyer.

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/raw-data-reporting-overview#báo-cáo-hành-trình-của-người-dùng">Báo cáo hành trình của người dùng</Anchor> (để biết thêm về CUID trong báo cáo dữ liệu thô)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Các phương pháp tốt nhất của Google để tránh gửi PII</Anchor>

<div data-zendesk-anchors="what-is-cuid=cuid-l%C3%A0-g%C3%AC h_01HAJ00DVHRSDBS4FFKM16JFER=cuid-l%C3%A0-g%C3%AC h_01HAJ00DVHZ8V8MRAXN2W3T8DS=v%C3%AD-d%E1%BB%A5 setting-the-cuid=c%C3%A0i-%C4%91%E1%BA%B7t-cuid h_01HAJ00DVHDGM133A72HD5JXER=c%C3%A0i-%C4%91%E1%BA%B7t-cuid associate-the-cuid-with-the-install-event=li%C3%AAn-k%E1%BA%BFt-cuid-v%E1%BB%9Bi-s%E1%BB%B1-ki%E1%BB%87n-c%C3%A0i-%C4%91%E1%BA%B7t h_01HAJ00DVHDE9V2MT6JQF8SAH3=li%C3%AAn-k%E1%BA%BFt-cuid-v%E1%BB%9Bi-s%E1%BB%B1-ki%E1%BB%87n-c%C3%A0i-%C4%91%E1%BA%B7t if-the-sdk-starts-in-the-application-class=n%E1%BA%BFu-sdk-b%E1%BA%AFt-%C4%91%E1%BA%A7u-trong-l%E1%BB%9Bp-application h_01HAJ00DVH746B6YJVF70PMZJ8=n%E1%BA%BFu-sdk-b%E1%BA%AFt-%C4%91%E1%BA%A7u-trong-l%E1%BB%9Bp-application if-the-sdk-starts-in-an-activity-class=khi-sdk-b%E1%BA%AFt-%C4%91%E1%BA%A7u-trong-m%E1%BB%99t-l%E1%BB%9Bp-activity h_01HAJ00DVHYZBER40RJH0GM8KF=khi-sdk-b%E1%BA%AFt-%C4%91%E1%BA%A7u-trong-m%E1%BB%99t-l%E1%BB%9Bp-activity developer-instructions-android=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n h_01HAJ00DVHZBZCRA1VGYJY44VY=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n developer-instructions::31dbab4b=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n h_01HAJ00DVH2RV902D6G224A4QY=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n developer-instructions-unity=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=h%C6%B0%E1%BB%9Bng-d%E1%BA%ABn-d%C3%A0nh-cho-nh%C3%A0-ph%C3%A1t-tri%E1%BB%83n cuid-and-privacy=cuid-v%C3%A0-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 h_01HAJ00DVH4987JGZZVDA1NB29=cuid-v%C3%A0-quy%E1%BB%81n-ri%C3%AAng-t%C6%B0 h_01HE7RXTEPQAWV03276TDEPG0V=xem-th%C3%AAm" />
