---
title: 'Bản tin: TikTok for Business—SRN nâng cao'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-26T12:27:56Z'
  edited_at: '2023-11-17T02:24:05Z'
  id: 7925111265041
  locale: vi
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/vi/articles/7925111265041
---
<div id="note" />

> 📘 **Lưu ý**
>
> Vào ngày 30 tháng 1 năm 2023, tích hợp mới **TikTok for Business—SRN nâng cao** `tiktokglobal_int` đã được thêm vào, trong khi tích hợp trên nền tảng **TikTok for Business** **Cũ** `bytedanceglobal_int` đang giảm dần hoạt động và sẽ ngừng hẳn kể từ tháng 3 năm 2024. TikTok đảm nhiệm việc xử lý quá trình chuyển đổi này và sẽ thông báo cho tất cả các khách hàng về thời điểm xóa tích hợp cũ của họ. **Để tránh mất dữ liệu, hãy đảm bảo duy trì cả hai tích hợp ở trạng thái hoạt động trong giai đoạn chuyển đổi**.

| **Tiêu đề** | AppsFlyer hiện hỗ trợ TikTok For Business dưới dạng Mạng Tự Báo cáo (SRN) nâng cao |
| --- | --- |
| **Ngày có hiệu lực** | Ngày 30 tháng 1 năm 2023 |
| **Thay đổi đang diễn ra ở đâu** | Trang tích hợp TikTok For Business trong Active Integrations. |
| **Hành động yêu cầu** | <ul><li><Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup">Thiết lập tích hợp mới</Anchor>. PID mới dành cho TikTok For Business là `tiktokglobal_int`.</li><li>Nếu bạn hiện đang tích hợp với TikTok For Business cũ `bytedanceglobal_int`, để tránh mất dữ liệu, không xóa tích hợp này cho đến **ngày chuyển đổi** của mình (xem hàng bên dưới).</li></ul> |
| **Ngày chuyển đổi** | Sau khi bạn kích hoạt tích hợp mới và TikTok For Business đã xác nhận đảm bảo tiện ích này hoạt động như mong đợi, họ sẽ liên hệ với bạn để thông báo cho bạn về ngày chính xác bạn chuyển từ tích hợp `byteanceglobal_int` cũ sang tích hợp mới. Quá trình này **có thể mất tới 45 ngày**, trong thời gian đó bảng điều khiển và báo cáo tiếp tục hiển thị dữ liệu từ tích hợp cũ.<br /><br />Sau ngày chuyển đổi, bảng điều khiển và báo cáo hiển thị dữ liệu từ tích hợp `byteanceglobal_int` mới.<br /><br />**Lưu ý:** Đối với các tích hợp mới không chuyển đổi từ tích hợp cũ, dữ liệu sẽ được hiển thị ngay trên bảng điều khiển và báo cáo. |
| **Tích hợp mới này có ý nghĩa gì?** | <ul><li>**Bảng điều khiển và báo cáo**<ul><li>Sau ngày chuyển đổi, tất cả chuyển đổi mới của TikTok For Business sẽ được phân bổ cho PID mới `tiktokglobal_int`.</li><li>Lượt nhấp và lượt hiển thị đã được ghi lại trước khi kích hoạt tích hợp mới sẽ được phân bổ cho `bytedanceglobal_int`.</li></ul></li><li>**Lượt nhấp và lượt hiển thị hợp nhất**<br />Sau ngày chuyển đổi, lượt nhấp và lượt hiển thị sẽ không còn sẵn có qua báo cáo cấp độ thô; chúng sẽ sẵn có trong các báo cáo chứa dữ liệu hợp nhất sau khi <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">kích hoạt kết nối API với TikTok</Anchor>.<br />**Lưu ý:**<ul><li>Đảm bảo bạn kích hoạt kết nối API trong quá trình thiết lập tích hợp.</li><li>Quá trình chuyển đổi yêu cầu một biến chuyển đáng kể trong báo cáo đo lường AppsFlyer, vì vậy dữ liệu lượt nhấp và lượt hiển thị sẽ không sẵn có ngay lập tức cho tích hợp mới.</li></ul></li><li>**Dữ liệu chi phí**<ul><li>**Dữ liệu chi phí trùng lặp:** Nếu cả tích hợp chi phí <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">`tiktokglobal_int`</Anchor> mới và `bytedanceglobal_int` <Anchor target="_blank" href="/marketers/vi/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">cũ được</Anchor> bật đồng thời, **dữ liệu chi phí có thể xuất hiện hai lần**. Bạn có thể tránh được điều này bằng cách đảm bảo chỉ **bật một Tích hợp chi phí**.<br />Tuy nhiên, khi bật tính năng tích hợp chi phí mới, dữ liệu chi phí từ 5 ngày trước ngày chuyển đổi sẽ tự động được thu thập. Điều này có nghĩa là hoạt động tích hợp mới dự kiến sẽ hiển thị dữ liệu chi phí trùng lặp trong 5 ngày đó. **Ví dụ**: nếu tính năng tích hợp chi phí cũ bị tắt vào ngày 15 tháng 1 và tính năng tích hợp chi phí mới được bật vào cùng ngày thì dữ liệu chi phí trùng lặp sẽ được hiển thị trong tính năng tích hợp chi phí mới từ ngày 10 đến ngày 14 tháng 1, mặc dù tính năng này chỉ được bật vào ngày 15 tháng 1 .</li><li>**Để đảm bảo chỉ bật một tính năng tích hợp Chi phí:**<ol><li>Vào **ngày chuyển đổi**, hãy chuyển đến tab **Cost** của **tích hợp cũ** và **tắt** nút chuyển đổi.</li><li>Chuyển đến tab **Cost** của **tích hợp mới** và **bật** nút chuyển đổi.</li></ol></li><li>Sau ngày bạn chuyển đổi, dữ liệu chi phí sẽ được liên kết với PID mới. Để xem dữ liệu chi phí cũ hơn, hãy thêm PID cũ vào bất kỳ tùy chọn lọc nào trên bảng điều khiển.</li><li>Trong giai đoạn chuyển đổi, số lượt cài đặt có thể bị phân chia giữa hai tích hợp trong một vài ngày, trong khi đó dữ liệu chi phí sẽ hiển thị tất cả. Lưu ý rằng trong khoảng thời gian này, KPI dựa trên dữ liệu này (như eCPI và ROI) có thể sẽ không chính xác.<br /><Image alt="cost integration on.png" src="https://files.readme.io/802e43a872253691d15cdf68feeaf59b7d21f348380819a38742be5e70987b51-18535286024337.png" width="283px" /></li></ul></li></ul><ul><li>**Các bài đăng lại SKAN**<br />Sau ngày chuyển đổi, tất cả các bài đăng lại SKAN sẽ được liên kết với tích hợp mới `tiktokglobal_int`.</li><li>**Chiến dịch nhắm mục tiêu lại**<br />Khi di chuyển sang tích hợp mới, nút chuyển đổi **Re-engagement** bị **tắt theo mặc định**, bất kể trạng thái trong tích hợp kế thừa. Đối với <Anchor target="_blank" href="/marketers/vi/docs/retargeting-attribution-guide">các chiến dịch nhắm mục tiêu lại</Anchor>, **để đảm bảo tính liên tục, hãy đảm bảo** **bật** nút chuyển đổi **Re-engagement** trong tích hợp mới.</li></ul> |
| **Ví dụ minh họa quy trình** | <ul><li>**Ngày 1 (ngày kích hoạt):** Bật tích hợp TikTok mới chỉ từ tab tích hợp. Duy trì trạng thái tắt cho tích hợp Chi phí. Mặc dù cả hai tích hợp đều bật, tích hợp mới chưa hoạt động và chưa có phân bổ nào cho nó.</li><li>**Ngày 2 tháng 10 (Giai đoạn đánh giá TikTok. Có thể mất tối đa 45 ngày):** TikTok đang thử nghiệm tích hợp mới. Sau khi phê duyệt dữ liệu, họ sẽ thông báo cho bạn về ngày chuyển đổi. Trong ví dụ này, ngày chuyển đổi sẽ là ngày 11.<br />Trong khi chờ đợi, bảng điều khiển và báo cáo chỉ hiển thị phân bổ cho tích hợp cũ. Nếu Chi phí được bật trong cả hai tích hợp, cả hai sẽ hiển thị dữ liệu chi phí đôi. Để tránh điều này, tốt nhất là tắt Chi phí đối với tích hợp mới.</li><li>**Ngày 11 (ngày chuyển đổi):** TikTok thực hiện chuyển đổi và bắt đầu phân bổ đến tích hợp mới. Trong khoảng một tuần kể từ ngày chuyển đổi (cho đến khi mọi lượt nhấp cũ hết hạn), dữ liệu phân bổ cài đặt được tách giữa cả hai tích hợp:<ul><li>Đối với tích hợp mới, TikTok gửi dữ liệu dưới dạng SRN.</li><li>Đối với tích hợp cũ, AppsFlyer có thể vẫn phân bổ các lượt nhấp cũ từ trước ngày chuyển đổi.</li></ul></li><li>**Ngày 18 (giai đoạn sau chuyển đổi)**: Sẽ không phân bổ lượt cài đặt cho tích hợp cũ mà chỉ cho tích hợp mới.<br />Trong 60 ngày tiếp theo, phân bổ cho các sự kiện trong ứng dụng có thể tiếp tục áp dụng cho tích hợp cũ. Do đó, để cho phép AppsFlyer tiếp tục gửi đăng lại cho các sự kiện này, bạn nên giữ bật tính năng tích hợp cũ (từ tab tích hợp).<br />Nếu tích hợp Chi phí tắt đối với tích hợp mới, giờ bạn có thể bật lên. Để tránh nhìn thấy dữ liệu chi phí kép, hãy tắt Chi phí từ tích hợp cũ.</li><li>**Ngày 78 (chuyển đổi cuối):** Tắt tích hợp cũ. TikTok giờ đóng vai trò là SRN và không cần đăng lại sự kiện trong ứng dụng.<br />Mặc dù tích hợp cũ đã tắt, nếu bạn chưa tắt tích hợp Chi phí cũ, bạn sẽ tiếp tục thấy chi phí dữ liệu trùng lặp trong tích hợp mới.</li></ul> |

<div id="see-also" />

> 📄 **Xem thêm**
>
> * <Anchor target="_blank" href="https://appsflyer.showpad.com/share/XB6r4QA1TN0wN63kqmslA">Chuyển đổi thành công sang tích hợp SRN Nâng cao mới với TikTok</Anchor>
> * Có gì mới trong AppsFlyer

<div data-zendesk-anchors="01H8JZVADPFQ4NTHMCB8PSCV6P=l%C6%B0u-%C3%BD h_01HDPFFJ6129APQF5DV3TV0SM2=xem-th%C3%AAm" />
