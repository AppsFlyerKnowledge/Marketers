---
title: Cấu hình chiến dịch Amazon DSP
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-09-09T13:03:19Z'
  id: 11904659502737
  locale: vi
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/vi/articles/11904659502737
---
> **Khái quát:** Amazon DSP (amazondsp\_int), đối tác tích hợp của AppsFlyer, cho phép chủ sở hữu ứng dụng đo lường phân bổ dựa trên lượt nhấp chuột và lượt xem bằng AppsFlyer dành cho TV, máy tính bảng và thiết bị di động.

![mceclip0.png](https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png)

<div id="complete-the-setup-in-amazon-ads" />

<div id="activate-partner" />

## Kích hoạt đối tác

**Điều kiện tiên quyết:** Trước khi thiết lập tích hợp, hãy nhớ <Anchor target="_blank" href="/marketers/vi/docs/partner-integrations#liên-hệ-với-đối-tác">liên hệ với đối tác</Anchor> và mở tài khoản với họ.

Quá trình thiết lập được thực hiện trên trang **Active Integrations**, nhưng để tìm đối tác mới, trước tiên bạn phải truy cập Marketplace theo mô tả bên dưới.

**Để kích hoạt chức năng tích hợp đối tác:**

1. Trong AppsFlyer, đi đến **Configuration** > **Partner Marketplace**.
2. Tìm kiếm và chọn tích hợp đối tác mới.
3. Nhấp vào **Set up integration**. Bạn được chuyển đến trang thiết lập **Active Integrations**.
4. Trong tab **Integration**, bật tùy chọn **Activate partner**.  
   **Lưu ý:** Nút bật/tắt phải luôn ở trạng thái bật (<Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">được kích hoạt</Anchor>) trong thời gian bạn làm việc với đối tác.
5. Hoàn thành cấu hình bằng cách sử dụng các thẻ có liên quan, như được mô tả ở phần tiếp theo.

<div id="setting-up-amazon-ads" />

## Thiết lập tích hợp Amazon DSP

Việc tích hợp với Amazon DSP hỗ trợ phân bổ lượt nhấp chuột và lượt hiển thị. Cửa sổ cấu hình bao gồm các thẻ sau: Integration, Attribution link, Cost, Ad revenue và Permissions. Amazon DSP sử dụng thẻ Integration và Permissions.

<div id="note" />

> 📘 **Lưu ý**
>
> * Một số tùy chọn cài đặt sẽ khác nhau giữa các thiết bị iOS và Android
> * Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner">cách thiết lập tích hợp đối tác</Anchor>

<div id="integration-tab" />

<Accordion title="Thẻ Integration">

Thẻ **Integration** bao gồm một số phần, như được mô tả bên dưới.

<div id="activate-partner-1" />

#### Kích hoạt đối tác

Để cấu hình tích hợp, trước tiên bạn phải [bật](/docs/amazon-ads-campaign-configuration#kích-hoạt-đối-tác) nút bật/tắt **Activate partner**. Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation#activating-a-partner">kích hoạt và hủy kích hoạt tích hợp đối tác</Anchor>. 

#### Quyền riêng tư Nâng cao

Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào trạng thái chuyển đổi **Quyền riêng tư Nâng cao (dành cho iOS 14.5+ trở lên)**:

| Quyền riêng tư Nâng cao: Bật | Quyền riêng tư Nâng cao: Tắt |
| --- | --- |
| Chỉ gửi các bài đăng lại về những sự kiện được phân bổ cho đối tác | Gửi các bài đăng lại theo cấu hình của bạn:<ul><li>**Tất cả các nguồn truyền thông, bao gồm nguồn tự nhiên**</li><li>**Chỉ đối tác này**</li></ul> |
| Gửi các bài đăng lại theo <Anchor target="_blank" href="/partners/vi/docs/advanced-privacy-guide-postback-macros-for-ad-networks">biểu mẫu Quyền riêng tư Nâng cao</Anchor> |  |
| <Anchor target="_blank" href="/marketers/vi/docs/apply-aggregated-advanced-privacy-framework">Dữ liệu hợp nhất và ẩn danh</Anchor> được chia sẻ với đối tác, đồng nghĩa với việc không chia sẻ dữ liệu ở cấp người dùng (ID thiết bị). |  |

<div id="general-settings" />

#### Cài đặt chung

**ID sản phẩm Amazon**

Đây là một mã khóa độc nhất do Người quản lý tài khoản Amazon tạo ra và được cấp cho nhà quảng cáo đối với các ứng dụng Amazon DSP. Cần có ID sản phẩm Amazon để hoàn tất quá trình tích hợp và cho phép phân bổ đến Amazon DSP.

#### Các bài đăng lại mặc định

Cấu hình cách thức gửi bài đăng lại cho lượt cài đặt:  

* **Chỉ đối tác này**: Chỉ gửi các bài đăng lại khi sự kiện được phân bổ cho đối tác này—nghĩa là người dùng thực hiện sự kiện đến từ đối tác này.
* **Tất cả các nguồn truyền thông bao gồm nguồn tự nhiên**: Gửi các bài đăng lại về những sự kiện được phân bổ cho bất kỳ đối tác nào và những sự kiện tự nhiên—nghĩa là khi người dùng thực hiện sự kiện đến từ bất cứ nguồn truyền thông nào.

> 📘 **Lưu ý**
>
> * Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào **trạng thái của nút chuyển đổi** <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#quyền-riêng-tư-nâng-cao">Quyền riêng tư nâng cao (dành cho iOS 14.5+ trở lên)</Anchor>.
> * Các bài đăng lại được chia sẻ qua Data Locker trong báo cáo hàng giờ chứ không phải theo thời gian thực.

<div id="note-1" />

<div id="ignore-active-users-for-retargeting" />

<div id="re-engagement-attribution" />

<div id="install-attribution" />

#### Phân bổ lượt cài đặt

Đặt khung thời gian phân bổ lượt nhấp qua và lượt xem hết cho lượt cài đặt (lần khởi chạy đầu tiên). Lưu ý rằng chỉ có thể phân bổ lượt cài đặt trong khung thời gian xem lại đến Amazon DSP.

1. Đặt **Install click-through lookback window** thành 1-23 giờ hoặc 1-30 ngày.  
   **Lưu ý:** Amazon DSP khuyên bạn nên đặt khung thời gian xem lại lượt nhấp qua thành 14 ngày để phù hợp với khung thời gian phân bổ của họ.
2. [Tùy chọn] Bật **Install view-through attribution** và đặt **Install view-through attribution window** thành 1-24 giờ.

<div id="in-app-event-postbacks" />

#### Đăng lại sự kiện trong ứng dụng

Cấu hình ánh xạ các sự kiện trong ứng dụng với các sự kiện của Amazon DSP, được gửi qua các bài đăng lại.

<div id="note-2" />

> 📘 **Lưu ý**
>
> Các bài đăng lại được chia sẻ qua Data Locker trong báo cáo hàng giờ chứ không phải theo thời gian thực.

**Để cấu hình đăng lại sự kiện trong ứng dụng:**

1. Bật tùy chọn **In-app event postbacks**.
2. Nhấp vào **Add event** để thêm một SDK hoặc sự kiện máy chủ đến máy chủ vào danh sách. Bảng sau đây mô tả các trường cần hoàn thành:  

| Tên thông số | Mô tả |
| --- | --- |
| **Sự kiện AppsFlyer** | Tên của sự kiện mà AppsFlyer nhận được từ SDK sẽ được tích hợp vào ứng dụng của bạn hoặc từ các sự kiện máy chủ đến máy chủ.<br />**Mẹo**: Bạn không thấy sự kiện đang tìm kiếm?<ul><li>Hãy đảm bảo kích hoạt sự kiện trên thiết bị có lượt cài đặt không tự nhiên và kiểm tra lại.</li><li>Nhập vào **AppsFlyer event**, sau đó nhấp vào **Create custom**. Đọc thêm về <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#sự-kiện-tùy-chỉnh">ánh xạ sự kiện tùy chỉnh.</Anchor></li></ul> |
| **mapped to partner event** | Tên hoặc ID duy nhất của từng sự kiện được xác định ở phía đối tác. Các cấu hình ánh xạ có thể có là:<ul><li>**Text field:** Nhận ID sự kiện tương ứng từ đối tác.</li><li>**Drop-down box:** Chọn sự kiện AppsFlyer được xác định trước phù hợp nhất.</li><li>**As is**: Gửi các sự kiện như vốn có mà không ánh xạ tên.</li></ul> |
| **for users from** | Chọn tùy chọn gửi cho sự kiện:<ul><li>**This partner only**: chỉ gửi các bài đăng lại khi sự kiện này được phân bổ cho đối tác này.</li><li>**All media sources including organic**: Gửi các bài đăng lại cho các sự kiện được phân bổ cho bất cứ đối tác cũng như các sự kiện tự nhiên.</li></ul> |
| **bao gồm** | <ul><li>**No data (default)**: Chỉ gửi sự kiện mà không gửi bất kỳ giá trị sự kiện nào.</li><li>**Values and revenue**: Gửi tất cả các thông số sự kiện, **bao gồm** cả giá trị doanh thu (nếu có trong sự kiện).</li><li>**Values without revenue**: Gửi tất cả các thông số **ngoại trừ** giá trị doanh thu.</li></ul> |

3. [Tùy chọn] Nhấp vào biểu tượng **Add condition**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e3b4e42933325fc5e93d4cc9e892a1b28388648078fddb965a31c8ec8c04b25f-17912947736465.png" width="30px" />để <Anchor target="_blank" href="/marketers/vi/docs/in-app-event-postback-configuration#đăng-lại-sự-kiện-trong-ứng-dụng-có-điều-kiện">đặt điều kiện</Anchor> cho một sự kiện.
4. Nhấp vào **Save integration**.
5. [Tùy chọn] Sau khi lưu tích hợp, trong khi vẫn còn ở trang cấu hình, bạn có thể tích hợp thêm ứng dụng của mình với đối tác:
   1. Từ góc trên cùng bên trái, dưới tên đối tác, hãy nhấp vào tên ứng dụng để mở danh sách ứng dụng.
   2. Chọn một ứng dụng khác từ danh sách thả xuống.
   3. Lặp lại [các bước tích hợp](/docs/amazon-ads-campaign-configuration#integration-tab) đối với ứng dụng đã chọn.

> 📘 **Lưu ý**
>
> Chỉ dành cho ứng dụng iOS: Quyền kiểm soát dữ liệu của bạn được chia sẻ với đối tác thông qua các bài đăng lại và <Anchor target="_blank" href="/marketers/vi/docs/about-raw-data-identifier-restrictions">báo cáo</Anchor> tùy thuộc vào **trạng thái của nút chuyển đổi** <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#quyền-riêng-tư-nâng-cao">Quyền riêng tư nâng cao (dành cho iOS 14.5+ trở lên)</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Thẻ Attribution link">

Đường dẫn phân bổ không dành cho Amazon DSP. Thực hiện phân bổ bằng cách kết hợp dữ liệu tương tác từ Amazon DSP với dữ liệu từ AppsFlyer, sử dụng khung thời gian xem lại lượt nhấp qua và lượt xem hết được cấu hình trong thẻ [Integration](/docs/amazon-ads-campaign-configuration#integration-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Thẻ Cost">

Dữ liệu chi phí không có sẵn đối với Amazon DSP.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Thẻ Ad revenue">

Doanh thu quảng cáo không có sẵn đối với Amazon DSP.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Thẻ Permission">

Chọn các quyền cho phép Amazon DSP có thể truy cập dữ liệu của bạn và thực hiện các hành động khác nhau.

<div id="note-3" />

> 📘 **Lưu ý**
>
> * Nếu tích hợp bị <Anchor target="_blank" href="/marketers/vi/docs/partner-activation-deactivation">hủy kích hoạt</Anchor> trong khi vẫn bật nút Permissions, thì các quyền vẫn được cấp.
> * Tìm hiểu thêm về <Anchor target="_blank" href="/marketers/vi/docs/set-up-an-integrated-partner#permissions-tab">cấp quyền</Anchor>.

</Accordion>

<div id="traits-and-limitations" />

<div id="see-also-1" />

<div id="note-5" />

<div id="dma-consent-methods" />

<div id="note-4" />

<div id="support-amazon-eu-consent-policy" />

<div id="ctv-to-mobile-attribution" />

<div id="raw-data-restrictions" />

<div id="deferred-deep-linking" />

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="/marketers/vi/docs/setting-up-amazon-fire-tv-ad-attribution">Thiết lập thuộc tính quảng cáo Amazon Fire TV</Anchor>

<div data-zendesk-anchors="activate-partner=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c 01H88VAJH3B5ESK12D3ATMMVZ8=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c setting-up-amazon-dsp-integration=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-amazon-dsp 01H88VAJH3VENKYVRQY5RXN63P=thi%E1%BA%BFt-l%E1%BA%ADp-t%C3%ADch-h%E1%BB%A3p-amazon-dsp 01H88VAJH3BYZSXQGGZZJQ9N0C=l%C6%B0u-%C3%BD 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c-1 01H88VAJH34GP7FK1KTJGRDPM7=k%C3%ADch-ho%E1%BA%A1t-%C4%91%E1%BB%91i-t%C3%A1c-1 advanced-privacy=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao 01H88VAJH3G5FAR7RRNDEPNGME=quy%E1%BB%81n-ri%C3%AAng-t%C6%B0-n%C3%A2ng-cao general-settings=c%C3%A0i-%C4%91%E1%BA%B7t-chung 01H88VAJH3F2FJK5YP3M2V7RWD=c%C3%A0i-%C4%91%E1%BA%B7t-chung default-postbacks=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh 01H88VAJH3WE9Z0971WMBRBJRS=c%C3%A1c-b%C3%A0i-%C4%91%C4%83ng-l%E1%BA%A1i-m%E1%BA%B7c-%C4%91%E1%BB%8Bnh 01H88VAJH3AETJZGYMY1YK7FJ6=l%C6%B0u-%C3%BD-3 install-attribution=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t 01H88VAJH3SSG6ZNV7XQ46W5CX=ph%C3%A2n-b%E1%BB%95-l%C6%B0%E1%BB%A3t-c%C3%A0i-%C4%91%E1%BA%B7t inapp-event-postbacks=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng 01H88VAJH3AS37MVF75GANWX4B=%C4%91%C4%83ng-l%E1%BA%A1i-s%E1%BB%B1-ki%E1%BB%87n-trong-%E1%BB%A9ng-d%E1%BB%A5ng h_01HCW04WHZ8HGHBHV4733CS615=l%C6%B0u-%C3%BD-2 01H88VAJH36MYZ9W1YPWA92Z1Z=l%C6%B0u-%C3%BD-3 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=l%C6%B0u-%C3%BD-4 h_01HDNZ59NQEDFC3D8JYGENR1NR=xem-th%C3%AAm" />
