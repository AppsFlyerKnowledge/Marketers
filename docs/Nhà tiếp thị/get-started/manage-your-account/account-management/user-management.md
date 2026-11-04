---
title: Quản lý người dùng
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2023-11-16T10:30:46Z'
  id: 4409128270481
  locale: vi
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/vi/articles/4409128270481
---
> **Khái quát:** Tạo và quản lý người dùng AppsFlyer trong tài khoản của bạn, đồng thời chỉ định cho họ quyền truy cập vào các tính năng, ứng dụng và dữ liệu.

<div id="overview" />

## Thông tin cơ bản

Tài khoản AppsFlyer cho phép nhiều người dùng, mỗi người dùng lại có các quyền được quản lý riêng. Số lượng người dùng tối đa trên mỗi tài khoản được xác định theo gói đăng ký của bạn.

Mỗi quyền của người dùng được xác định theo 3 phương diện chính:

* **Vai trò** (khả năng truy cập các tính năng và thực hiện các chức năng)
* **Truy cập ứng dụng** cho các ứng dụng hiện tại và tương lai
* **Truy cập dữ liệu** theo nguồn truyền thông và địa lý
  * Quan trọng! Một số bảng điều khiển và tính năng nhất định của AppsFlyer không khả dụng đối với người dùng có quyền truy cập dữ liệu hạn chế (đối với nguồn truyền thông và địa lý). Các bảng điều khiển và tính năng này được [liệt kê ở đây](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

Quyền trong mỗi phương diện này được chỉ định độc lập. Nói cách khác, bạn có thể chỉ định cho người dùng một **vai trò** có nhiều khả năng chức năng nhưng chỉ cho phép họ thực hiện các khả năng đó trong một nhóm **ứng dụng, nguồn truyền thông và địa lý được xác định trong phạm vi hẹp.** Trường hợp ngoại lệ duy nhất là [Vai trò quản trị viên](/docs/user-management#quản-trị-viênmột-vai-trò-đặc-biệt), như được thảo luận dưới đây, vai trò này có quyền truy cập vào tất cả các khả năng, ứng dụng, nguồn truyền thông và địa lý.

Một tính năng mới, hiện đang ở giai đoạn Beta, cho phép bạn [thêm người dùng vào nhiều tài khoản](#multiple-accounts) để họ có thể dễ dàng chuyển đổi giữa các tài khoản.

<div id="manage-roles" />

## Vai trò

Mỗi người dùng tài khoản AppsFlyer của bạn phải được chỉ định một vai trò. Mỗi vai trò xác định các tính năng cụ thể của AppsFlyer mà người dùng có thể truy cập và các chức năng họ có thể thực hiện. Danh sách đầy đủ các khả năng của mỗi vai trò được cung cấp trên thẻ [Role](/docs/user-management#thẻ-roles) của trang **User management**.

Vai trò trong AppsFlyer có thể là [vai trò được xác định trước](/docs/user-management#vai-trò-được-xác-định-trước), [vai trò tùy chỉnh](/docs/user-management#vai-trò-tùy-chỉnh) hoặc [vai trò tạm thời](/docs/user-management#vai-trò-tạm-thời) (trong một số trường hợp nhất định).

<div id="predefined-roles" />

### Vai trò được xác định trước

AppsFlyer được cấu hình với nhiều vai trò được xác định trước:

* Quản trị viên
* Quản lý nhóm
* Trưởng bộ phận tiếp thị
* Tiếp thị
* Tiếp thị – hạn chế
* Người đóng góp
* Kế toán
* Bảo mật
* Đảm bảo Chất lượng

Đối với mỗi vai trò được xác định trước này, các khả năng chức năng là cố định: không cho phép "kết hợp tùy chỉnh". Tuy nhiên, bạn có thể thay đổi khả năng chức năng của người dùng bất kỳ lúc nào bằng cách chỉ định một vai trò tùy chỉnh hoặc được xác định trước khác cho họ (ngoại trừ [chủ sở hữu tài khoản](#chủ-tài-khoản), như được thảo luận bên dưới).

<div id="example-1" />

> 📄 **Ví dụ**
>
> Bạn đã giao cho Bill Bates vai trò **Quản lý nhóm.** Vai trò này mang cấp cho Bill quyền quản lý **các mẫu OneLink** nhưng không cho phép anh truy cập vào các trang **My plan** và **Payments**.
>
> **Câu hỏi:** Tôi có thể tiếp tục cho Bill giữ vai trò Quản lý nhóm đồng thời cấp cho anh ấy quyền truy cập vào trang My plan và Payments không? Tôi có thể thu hồi khả năng cho anh ấy có thể quản lý các mẫu OneLink không?
>
> **Trả lời:** Không. Trong khi Bill vẫn đang giữ vai trò là Quản lý nhóm thì bạn sẽ không thể cấp cho anh ấy quyền truy cập trang My Plan và Payments. Bạn cũng không thể tước bỏ quyền quản lý các mẫu OneLink của anh ấy. Tất nhiên, bạn có thể chỉ định Bill vào một vai trò được xác định trước khác và khả năng của anh ấy sẽ thay đổi thành những khả năng được xác định theo vai trò đó. Hoặc bạn có thể tạo vai trò tùy chỉnh cho Bill để thay đổi khả năng của anh ấy theo nhu cầu của bạn.

<div id="custom-roles" />

### Vai trò tùy chỉnh

Các vai trò được xác định trước trong AppsFlyer đã được cấu hình với các kết hợp khả năng cụ thể cần thiết trong hầu hết các tình huống. Vì lý do này, nhiều nhà quảng cáo nhận thấy rằng họ không cần tùy chỉnh thêm các vai trò. Tuy nhiên, khi cần tùy chỉnh thêm, các vai trò được xác định trước vẫn là điểm khởi đầu tuyệt vời để quản lý các khả năng của người dùng.

Tìm hiểu thêm về [quản lý vai trò tùy chỉnh](/docs/user-management#quản-lý-vai-trò-tùy-chỉnh).

<div id="temp-roles" />

### Vai trò tạm thời

Nếu tài khoản AppsFlyer của bạn tồn tại trong hệ thống quản lý người dùng trước đây của chúng tôi (khi các loại tài khoản khả dụng duy nhất là Quản trị viên và Thành viên nhóm), thì tất cả người dùng đã được đưa vào hệ thống mới với các khả năng được giữ nguyên. Do đó, hầu hết những người dùng này sẽ xuất hiện trong hệ thống hiện tại với **vai trò tạm thời**.

Tìm hiểu thêm về [quản lý vai trò tạm thời](/docs/user-management#managing-temp-roles).

<div id="admin" />

### Quản trị viên—một vai trò đặc biệt

Tài khoản AppsFlyer có thể có **một hoặc nhiều Quản trị viên**. Vai trò đặc biệt này có một số đặc điểm độc đáo:

<div id="access" />

#### Quyền truy cập

Vai trò Quản trị viên có quyền truy cập vào **tất cả** các khả năng của tài khoản, bao gồm:

* Tất cả các tính năng và chức năng
* Tất cả các ứng dụng hiện tại và tương lai
* Tất cả các nguồn truyền thông và địa lý

Đặc điểm "toàn quyền truy cập" này của vai trò Quản trị viên sẽ không thể bị thay đổi hoặc có giới hạn.

<div id="role-duplication" />

#### Sao chép vai trò

Vai trò Quản trị viên **không được trùng lặp** khi tạo [vai trò tùy chỉnh](/docs/user-management#quản-lý-vai-trò-tùy-chỉnh).

<div id="account-owner" />

#### Chủ tài khoản

Người dùng được tạo vào thời điểm tài khoản được mở (**"chủ tài khoản"**) sẽ được chỉ định vai trò Quản trị viên theo mặc định. Ban đầu, chủ tài khoản chịu trách nhiệm tạo thêm người dùng (cho đến khi tạo thêm người dùng có khả năng quản lý người dùng).

Chủ tài khoản có những đặc điểm riêng:

* Không giống như bất kỳ Quản trị viên nào ngoài chủ tài khoản, chủ tài khoản không thể bị xóa, loại khỏi vai trò Quản trị viên hoặc chỉnh sửa khỏi trang [**Quản lý người dùng**](/docs/user-management#trang-user-management) .
* Nếu bạn cần thay đổi chủ tài khoản, hãy làm theo [các bước được liệt kê dưới đây](/docs/user-management#changing-the-account-owner).
* Chỉ chủ tài khoản mới có thể:
  * Truy xuất hoặc đặt lại <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens">token API AppsFlyer</Anchor>
  * Cấu hình hoặc thay đổi <Anchor target="_blank" href="/marketers/vi/docs/push-api-streaming-raw-data">cài đặt API Push</Anchor>

<div id="user-management-page" />

## Trang User management

**Cách truy cập trang User management:**

1. Trên thanh menu, nhấp vào danh sách thả xuống địa chỉ email.
2. Chọn **User management.**

<div id="users-tab" />

### Thẻ Users

Thẻ **Users** hiển thị một bảng gồm tất cả người dùng hiện có trong tài khoản của bạn. Đây là điểm khởi đầu để tạo, quản lý và xóa người dùng.

Gợi ý để điều hướng trong thẻ Users:

* Nhấp vào tiêu đề cột **User** để sắp xếp bảng theo thứ tự bảng chữ cái (tăng dần/giảm dần).
* Sử dụng hộp tìm kiếm để tìm và hiển thị những người dùng cụ thể.
* Nhấp vào biểu tượng bộ lọc <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> trong tiêu đề cột **Role** để lọc người dùng theo vai trò của họ (bao gồm cả vai trò tạm thời).
  * Để xóa bộ lọc, chọn **None** trong danh sách thả xuống bộ lọc.
* Nhấp vào tiêu đề cột **Last login** để sắp xếp người dùng theo ngày họ đăng nhập lần cuối vào AppsFlyer.
  * **Gợi ý:** Sử dụng tính năng này để dễ dàng xác định và [xóa](/docs/user-management#deleting-users) người dùng không hoạt động, giúp giữ an toàn cho tài khoản của bạn khỏi các hoạt động đăng nhập trái phép.
* Sử dụng các hộp kiểm để chọn và [chỉnh sửa nhiều người dùng](/docs/user-management#chỉnh-sửa-nhiều-người-dùng) cùng một lúc.
* Chỉ dành cho quản trị viên: Nhấp vào biểu tượng tải xuống <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> ở góc trên bên phải của trang để tải xuống toàn bộ bảng người dùng dưới dạng tập tin CSV.
  * Tập tin đã tải xuống bao gồm các cột giống như trong bảng ở thẻ **Users**.

<div id="roles-tab" />

### Thẻ Roles

Thẻ **Roles** hiển thị danh sách tất cả các vai trò được xác định trong tài khoản của bạn, bao gồm:

* [Vai trò được xác định trước](/docs/user-management#vai-trò-được-xác-định-trước)
* [Vai trò tùy chỉnh](/docs/user-management#quản-lý-vai-trò-tùy-chỉnh) mà bạn đã tạo
* Mọi [vai trò tạm thời](/docs/user-management#vai-trò-tạm-thời) hiện được chỉ định cho người dùng

Bên cạnh mỗi vai trò, bạn có thể thấy số lượng người dùng hiện được chỉ định cho vai trò đó.

Nhấp vào tên của bất kỳ vai trò nào trong bảng bên trái để hiển thị toàn bộ chi tiết về khả năng của vai trò đó.

<div id="manage-users" />

## Quản lý người dùng

<div id="creating-users" />

<Accordion title="Tạo người dùng">

**Để tạo người dùng mới:**

1. Trên thẻ **Users**, nhấp vào nút **New user**.
2. Nhập tên người dùng (bắt buộc):
   * Có thể bao gồm các chữ cái, số, dấu cách, dấu chấm (.), dấu gạch nối (-), dấu gạch dưới (\_) và dấu nháy đơn (') hoặc dấu nháy kép (").
   * Không được phép sử dụng các ký tự đặc biệt khác.
3. Nhập địa chỉ email của người dùng (bắt buộc):
   * Có thể bao gồm các chữ cái, chữ số, dấu nháy đơn ('), dấu và (&), ký hiệu đô la ($), ký hiệu thăng (#), dấu gạch nối (-), dấu gạch dưới (\_) và dấu chấm (.)
   * Không được phép sử dụng hai dấu chấm liền nhau (..) và các ký tự đặc biệt khác.
   * Phải kết thúc bằng một miền email hợp lệ.

   <div id="important" />

   > 🚧 **Quan trọng!**
   >
   > Địa chỉ email của người dùng là thứ xác định họ trong nền tảng AppsFlyer, nghĩa là:
   >
   > * Địa chỉ không thay đổi được sau đó, chỉ có thể xóa và tạo lại người dùng.
   > * Địa chỉ phải là một địa chỉ email hợp lệ mà người dùng sử dụng để nhận email.
   > * Địa chỉ không liên kết được với người dùng khác trong bất kỳ tài khoản AppsFlyer nào, [ngoại trừ người dùng trong tài khoản beta](/docs/user-management#multiple-accounts). Nếu địa chỉ email đã được sử dụng (trong tài khoản của bạn hoặc tài khoản khác), bạn sẽ thấy thông báo *Can't create this user.* Thực hiện theo [các bước khắc phục sự cố dưới đây](/docs/user-management#troubleshooting-can-t-create-this-user) để giải quyết vấn đề này.

4. Chọn bộ phận của người dùng (tùy chọn).
5. Chọn vai trò của người dùng (bắt buộc) – vai trò được xác định trước hoặc vai trò tùy chỉnh mà bạn đã tạo.
6. Chọn các ứng dụng mà người dùng có thể truy cập:
   * Cài đặt mặc định cho phép truy cập vào tất cả các ứng dụng hiện tại và tương lai trong tài khoản. Để thay đổi cài đặt này, hãy sử dụng hộp kiểm để chọn và bỏ chọn ứng dụng.
   * Người dùng chỉ có thể được cấp quyền truy cập vào tất cả các ứng dụng trong tương lai nếu họ có quyền truy cập vào tất cả các ứng dụng hiện tại.
7. Chọn các nguồn truyền thông mà người dùng có thể truy cập. Cài đặt mặc định cho phép truy cập vào tất cả các nguồn truyền thông. Để thay đổi cài đặt này:
   1. Nhấp vào nút **All** .
   2. Từ danh sách thả xuống, hãy chọn các nguồn truyền thông cụ thể mà người dùng có thể truy cập.  

      > 📘 **Lưu ý**
      >
      > * Khi chọn các nguồn truyền thông cụ thể, người dùng sẽ chỉ có quyền truy cập vào các đối tác mà họ được tích hợp cùng
      > * Quyền truy cập vào các nguồn truyền thông sở hữu chỉ khả dụng khi chọn **Tất cả** các nguồn truyền thông.
      > * Một số [bảng và tính năng nhất định của AppsFlyer không khả dụng](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access) đối với người dùng có quyền truy cập nguồn truyền thông hạn chế

8. Chọn các khu vực địa lý mà người dùng có thể truy cập:
   * Cài đặt mặc định cho phép truy cập vào tất cả các khu vực địa lý. Để thay đổi cài đặt này:
     * Nhấp vào nút **All** .
     * Từ danh sách thả xuống, hãy chọn các khu vực địa lý cụ thể mà người dùng có thể truy cập.
   * Một số [bảng điều khiển và tính năng nhất định của AppsFlyer không khả dụng](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access) đối với người dùng có quyền truy cập địa lý hạn chế.
9. Nhấp vào **Save** để tạo người dùng.

   * <span id="activation"></span>Người dùng được gửi lời mời qua email để kích hoạt tài khoản của họ.
   * Người dùng được hiển thị trong bảng người dùng. Biểu tượng phong bì ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png) cho biết rằng lời mời đã được gửi và tài khoản đang chờ kích hoạt. Khi người dùng kích hoạt tài khoản của họ, phong bì sẽ biến mất.
   * Liên kết kích hoạt được gửi cho người dùng có hiệu lực trong 48 giờ. Nếu người dùng không nhận được lời mời hoặc nếu liên kết đã hết hạn, bạn có thể [gửi lại lời mời](/docs/user-management#resending-a-user-invitation).

</Accordion>

<div id="multiple-accounts" />

<Accordion title="Thêm người dùng vào nhiều tài khoản">

> 📘 **Lưu ý**
>
> Tính năng này hiện chỉ có trên các tài khoản tham gia phiên bản beta. Nếu bạn muốn dùng thử, hãy liên hệ với CSM của bạn hoặc [hello@appsflyer.com](mailto:hello@appsflyer.com).

Có thể thêm người dùng vào nhiều tài khoản và chỉ định cho các vai trò khác nhau trong từng tài khoản. Điều này giúp người dùng làm việc trong các tài khoản khác nhau mà không cần nhập lại thông tin đăng nhập.

<div id="supported-accounts-and-users" />

#### Tài khoản và người dùng được hỗ trợ

Các tài khoản sau hỗ trợ có cùng người dùng trong nhiều tài khoản:

* Chỉ các tài khoản nhà quảng cáo
* Các tài khoản không dùng <Anchor target="_blank" href="/marketers/vi/docs/implementing-and-using-2fa-login">2FA</Anchor> hoặc <Anchor target="_blank" href="/marketers/vi/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>

Các giới hạn sau được áp dụng khi thêm người dùng vào nhiều tài khoản:

* Chỉ người dùng có quyền quản lý Người dùng phù hợp mới sử dụng được tính năng này.
* [Chủ tài khoản](#chủ-tài-khoản) chỉ có thể tồn tại trong một tài khoản. Người dùng này không thể tồn tại trong bất kỳ tài khoản nào khác, kể cả trong vai trò khác.
* Không thể thêm người dùng chưa [kích hoạt tài khoản](#activation) vào tài khoản khác.

<div id="add-users-to-multiple-accounts" />

#### Thêm người dùng vào nhiều tài khoản

**Để thêm cùng người dùng vào nhiều tài khoản:**

1. Đăng nhập vào tài khoản mà bạn muốn thêm người dùng.
2. Từ thanh menu, nhấp vào **mục thả xuống địa chỉ email** > **User management**.
3. Từ tab **Users**, nhấp vào **New user**.
4. Nhập thông tin chi tiết bắt buộc, chọn vai trò cho người dùng trong tài khoản này và nhấp vào **Save**.
5. Lặp lại các bước 1-4 để thêm người dùng vào các tài khoản khác.

</Accordion>

<div id="editing-users" />

<Accordion title="Chỉnh sửa người dùng">

Người dùng có thể được chỉnh sửa theo cá nhân hoặc theo nhóm.

<div id="individual-editing" />

#### Chỉnh sửa theo cá nhân

**Để chỉnh sửa một người dùng cá nhân:**

1. Trên thẻ **Users**, nhấp vào nút **Actions** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> ở phía ngoài cùng bên phải hàng của người dùng.
2. Chọn **Edit** từ menu.
3. Chỉnh sửa cài đặt người dùng theo yêu cầu.
4. Tất cả các cài đặt ngoài địa chỉ email đều có thể chỉnh sửa được (bao gồm vai trò, ứng dụng, nguồn truyền thông và địa lý).
5. Nhấp vào **Save** (Lưu).

<div id="multi-user-editing" />

#### Chỉnh sửa nhiều người dùng

Chỉnh sửa nhiều người dùng là một cách hiệu quả để thay đổi quyền tài khoản của nhiều người dùng cùng một lúc. Sử dụng tính năng này kết hợp với khả năng tìm kiếm và lọc của thẻ **Users** có thể giúp tính năng này đặc biệt hữu ích cho việc quản lý số lượng lớn người dùng.

<div id="note-4" />

> 📘 **Lưu ý**
>
> Bạn không thể xóa người dùng hoặc chỉ định họ vào vai trò Quản trị viên bằng tính năng chỉnh sửa nhiều người dùng.

**Để chỉnh sửa nhiều người dùng:**

1. Trên thẻ **Users**, chọn hộp kiểm của người dùng hoặc những người dùng bạn muốn chỉnh sửa.
   * Chọn hộp kiểm trong tiêu đề cột để chọn tất cả người dùng đang được hiển thị.
   * Số lượng người dùng hiện được chọn được hiển thị ở phía bên phải của hộp tìm kiếm. Lưu ý rằng [chủ sở hữu tài khoản](#chủ-tài-khoản) không thể được chọn và không bao gồm trong số lượng người dùng được chọn.
2. Một loạt các nút hiển thị ở trên cùng bên phải của bảng: **Role, Apps, Media sources,** và **Geos.**
   * Nếu một hoặc nhiều người dùng được chọn có quyền truy cập vào các ứng dụng trong tương lai, thì nút **Apps** sẽ không khả dụng. (Xem [Hạn chế của vai trò tạm thời](/docs/user-management#hạn-chế-của-vai-trò-tạm-thời) bên dưới.)
3. Nhấp vào nút cho các quyền bạn muốn thay đổi.
4. Thực hiện các thay đổi cần thiết bằng cách sử dụng hộp thoại hoặc danh sách thả xuống được hiển thị.
   * Hãy nhớ rằng các thay đổi của bạn sẽ áp dụng cho tất cả người dùng đã chọn!
5. Người dùng đã chỉnh sửa được tô sáng trong bảng và người dùng sẽ xuất hiện như cách họ sẽ được hiển thị sau khi lưu thay đổi. Tuy nhiên, bạn vẫn có cơ hội xem lại các thay đổi của mình và xác nhận hoặc hủy chúng trong bước tiếp theo.
6. Xem lại các thay đổi của bạn. Nhấp vào **Save** để xác nhận hoặc **Cancel** để hoàn tác thay đổi.

<div id="example" />

> 📄 **Ví dụ**
>
> **Tình huống:**
>
> * Có 30 người dùng trong tài khoản của bạn. Mười trong số này có vai trò **Tiếp thị – hạn chế**.
> * Alice, Bill và Charlie vừa được thăng chức và bạn muốn thay đổi họ từ vai trò **Tiếp thị – hạn chế** sang vai trò **Tiếp thị** .
> * Alice sẽ làm việc với ứng dụng Astounding. Bill sẽ làm việc với ứng dụng Beautiful. Charlie sẽ làm việc với ứng dụng Charming.
>
> **Các bước thực hiện:**
>
> 1. Sử dụng bộ lọc Vai trò <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> để chỉ xem những người dùng có vai trò **Tiếp thị–hạn chế**.
> 2. Thay đổi Alice, Bill và Charlie thành vai trò **Tiếp thị**:
>    * Chọn các hộp kiểm cho Alice, Bill và Charlie.
>    * Nhấp vào nút **Role**.
>    * Chọn **Tiếp thị** từ danh sách thả xuống.
>    * Nhấp vào **Save** để xác nhận.
>    * Lưu ý rằng sau khi bạn xác nhận các thay đổi, bộ lọc **Vai trò** sẽ bị xóa và bảng sẽ hiển thị tất cả người dùng.
> 3. Cấp cho Alice, Bill và Charlie quyền truy cập ứng dụng thích hợp:
>    * Sử dụng hộp tìm kiếm để tìm Alice, sau đó chỉnh sửa riêng tài khoản người dùng của cô ấy để cấp cho cô ấy quyền truy cập vào ứng dụng Astounding.
>    * Lặp lại các bước này cho Bill và Charlie để cấp cho họ quyền truy cập vào Beautiful và Charming tương ứng.

</Accordion>

<div id="deleting-users" />

<Accordion title="Xóa người dùng">

**Để xóa người dùng:**

1. Trên thẻ **Users** , nhấp vào nút **Action** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> ở phía ngoài cùng bên phải hàng của người dùng.
2. Chọn **Delete** từ menu.

</Accordion>

<div id="manage-custom-roles" />

## Quản lý vai trò tùy chỉnh

<div id="creating-custom-roles" />

<Accordion title="Tạo vai trò tùy chỉnh">

Quá trình tạo vai trò tùy chỉnh liên quan đến việc sao chép vai trò **được xác định trước** và sửa đổi khả năng của vai trò đó theo yêu cầu.

> 📘 **Lưu ý**
>
> * Chỉ chủ sở hữu tài khoản hoặc người dùng có quyền truy cập Quản trị viên mới có thể tạo vai trò tùy chỉnh.
> * Không thể sao chép vai trò Quản trị viên, vai trò tùy chỉnh và vai trò tạm thời.

**Để tạo vai trò tùy chỉnh:**

1. Trên bảng bên trái của thẻ **Roles**, nhấp vào tên của vai trò **được xác định trước** với các khả năng gần giống với vai trò bạn muốn tạo nhất. Đây là điểm khởi đầu của bạn.
2. Nhấp vào nút **Duplicate** ![user_management_duplicate_button.png](https://files.readme.io/93d3427f3890b6d19470523ab8baa4435489428da62c23cd56a7cca7e8be923c-8781532671249.png) ở góc trên bên phải của màn hình.

   Màn hình của bảng bên phải sẽ thay đổi, cho phép bạn tạo vai trò tùy chỉnh mới.
3. Nhập tên cho vai trò mới mà bạn đang tạo.
   * **Lưu ý:** Khi bạn đã lưu vai trò tùy chỉnh, không thể chỉnh sửa tên của vai trò đó.
   * **Đề xuất:** Đặt tên mang tính mô tả và dễ nhận biết sau này.
4. Các cấp độ quyền của tất cả các khả năng có thể chỉnh sửa sẽ được hiển thị dưới dạng các nút. Nhấp vào các nút này để thay đổi cấp độ quyền đối với vai trò tùy chỉnh mới. (Đảm bảo cuộn xuống để xem danh sách đầy đủ các khả năng.)
   * **Lưu ý:** Hiện không thể chỉnh sửa các khả năng không xuất hiện dưới dạng nút. Để thay đổi cấp độ quyền của người dùng đối với khả năng không thể chỉnh sửa, người dùng đó phải được chỉ định một vai trò được xác định trước với cấp độ quyền cần thiết.
5. Khi bạn hài lòng với tất cả các lựa chọn của mình, hãy nhấp vào nút **Save role**.
6. Vai trò tùy chỉnh mới được hiển thị trong bảng bên trái và có thể được chỉ định khi tạo người dùng mới hoặc chỉnh sửa người dùng hiện có.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="Chỉnh sửa vai trò tùy chỉnh">

**Để chỉnh sửa vai trò tùy chỉnh:**

1. Trên bảng bên trái của thẻ **Roles**, nhấp vào tên của vai trò tùy chỉnh mà bạn muốn chỉnh sửa.
2. Nhấp vào nút **Edit** ![user_management_edit_role_button.png](https://files.readme.io/bf1ba44ddaa3483996c55c9450c42056acb6acbc9e921e339c8af5061f1c0bfb-8781493918225.png) ở góc trên bên phải của màn hình.

   Màn hình của bảng bên phải sẽ thay đổi, cho phép bạn chỉnh sửa cài đặt quyền của vai trò.

   * **Lưu ý:** Không thể chỉnh sửa tên của vai trò. Để thay đổi tên của một vai trò, hãy xóa vai trò đó và tạo lại với tên mới.
3. Các cấp độ quyền của tất cả các khả năng có thể chỉnh sửa sẽ được hiển thị dưới dạng các nút. Nhấp vào các nút này để thay đổi cấp độ quyền đối với vai trò tùy chỉnh mới. (Đảm bảo cuộn xuống để xem danh sách đầy đủ các khả năng.)
4. Khi bạn hài lòng với tất cả các lựa chọn của mình, hãy nhấp vào nút **Save role**.
5. Cấp độ quyền của vai trò áp dụng thay đổi cho tất cả người dùng mới và người dùng hiện có.

<div id="important-1" />

> 🚧 **Quan trọng!**
>
> Mọi thay đổi bạn thực hiện đối với vai trò tùy chỉnh sẽ tự động được áp dụng cho **tất cả người dùng hiện có** trong vai trò đó.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="Xóa vai trò tùy chỉnh">

**Xóa một vai trò tùy chỉnh:**

1. Trên bảng bên trái của thẻ **Roles**, nhấp vào tên của vai trò tùy chỉnh mà bạn muốn xóa.
2. Nhấp vào nút **Delete** ![user_management_delete_role_button.png](https://files.readme.io/6a9a97ce9437de6fca16ebb9ed3ac365299e7e558f5075698d20806076c0fd9c-8781434340113.png) ở góc trên bên phải của màn hình.
3. Xác nhận rằng bạn muốn xóa vai trò.
   * Vai trò tùy chỉnh chỉ có thể bị xóa khi không có người dùng nào được chỉ định cho vai trò đó. Nếu có người dùng hiện được chỉ định cho một vai trò tùy chỉnh, hãy chỉ định những người dùng này cho một vai trò khác trước khi xóa vai trò tùy chỉnh.

</Accordion>

<div id="special-situations-and-additional-procedures" />

## Các tình huống đặc biệt và quy trình bổ sung

<div id="managing-temp-roles" />

<Accordion title="Quản lý vai trò tạm thời">

Nếu tài khoản của bạn trước đây đã sử dụng hệ thống quản lý người dùng cũ của chúng tôi, [**vai trò tạm thời**](/docs/user-management#vai-trò-tạm-thời) sẽ được chỉ định cho người dùng hiện có để đảm bảo rằng họ được đưa vào hệ thống mới với các khả năng được giữ nguyên.

* Những người dùng có cùng khả năng đã được chỉ định cùng một vai trò tạm thời.
* Sử dụng các tính năng của thẻ [Roles](/docs/user-management#thẻ-roles) để xem lại khả năng của từng vai trò tạm thời và danh sách người dùng hiện đang có vai trò đó.

<div id="temp-role-limitations" />

#### Hạn chế của vai trò tạm thời

Vai trò tạm thời được thiết kế đặc biệt để cho phép chuyển đổi liền mạch từ hệ thống quản lý người dùng trước đây của chúng tôi. Do vậy, chúng chỉ có sẵn trong các tình huống hạn chế:

* Vai trò tạm thời không thể được chỉ định cho người dùng khác (dù là mới hay hiện có).
* Người dùng có vai trò tạm thời không thể được chỉ định một vai trò tạm thời khác (mặc dù bạn có thể thay đổi ứng dụng, nguồn truyền thông và địa lý mà họ có quyền truy cập).
  * Lưu ý rằng **không thể** thay đổi quyền truy cập của người dùng vào các ứng dụng trong tương lai khi người dùng đang ở vai trò tạm thời.
* Khi người dùng có vai trò tạm thời được thay đổi thành vai trò được xác định trước, họ không thể chuyển về lại vai trò tạm thời đã chỉ định trước đó (hoặc bất kỳ vai trò tạm thời nào khác).
* Nếu người dùng cuối cùng giữ vai trò tạm thời bị xóa khỏi vai trò đó, thì vai trò đó sẽ không còn xuất hiện trong tài khoản của bạn nữa.

<div id="example-2" />

> 📄 **Ví dụ**
>
> Tài khoản của bạn ngày trước đã sử dụng hệ thống quản lý người dùng trước đây của chúng tôi. Diana và Edward là những người dùng hiện có vào thời điểm tài khoản của bạn được chuyển sang hệ thống mới. Diana hiện đang có vai trò Tạm thời 1 và Edward có vai trò Tạm thời 2.
>
> * Bạn tuyển một nhân viên mới, Fiona. Bạn có thể chỉ định cho Fiona bất kỳ [vai trò được xác định trước](/docs/user-management#vai-trò-được-xác-định-trước) nào. Tuy nhiên, bạn không thể chỉ định cho Fiona vai trò Tạm thời 1 hoặc vai trò Tạm thời 2.
> * Không thể chuyển Diana từ vai trò Tạm thời 1 sang vai trò Tạm thời 2. Tuy nhiên, bạn có thể chỉ định cho cô ấy bất kỳ vai trò được xác định trước nào. Bạn cũng có thể thay đổi quyền truy cập của cô ấy vào các ứng dụng, nguồn truyền thông và địa lý nếu cần.
> * Nếu bạn chuyển Diana từ vai trò Tạm thời 1 sang vai trò Kế toán, sau này cô ấy không thể chuyển về lại vai trò Tạm thời 1.
> * Nếu Diana là người dùng cuối cùng giữ vai trò Tạm thời 1 khi bạn chuyển cô ấy sang vai trò Kế toán, thì vai trò Tạm thời 1 sẽ không còn xuất hiện trong tài khoản của bạn nữa.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="Tính khả dụng của bảng điều khiển và tính năng dành cho người dùng có quyền truy cập địa lý/nguồn truyền thông hạn chế">

Các bảng điều khiển AppsFlyer sau **không khả dụng** đối với người dùng có quyền truy cập bị giới hạn chỉ các nguồn truyền thông và khu vực địa lý cụ thể:

* Tổng quan về SKAN
* Protect360
* Giữ chân người dùng
* Phân bổ trên cơ sở người dùng
* Tính gia tăng

Ngoài ra, các tính năng sau của AppsFlyer **không khả dụng** đối với những người dùng này:

* Bảng tổng hợp
* OneLink
* Quy tắc Xác thực
* Đối tượng (không áp dụng cho người dùng bị giới hạn nguồn truyền thông; khả dụng đối với người dùng bị giới hạn địa lý)
* Thông tin SDK
* Nhập chi tiêu quảng cáo
* Chi phí ETL

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="Thay đổi chủ sở hữu tài khoản">

Vì tất cả Quản trị viên về cơ bản đều có quyền giống như chủ sở hữu tài khoản nên việc thay đổi chủ sở hữu tài khoản thường không cần thiết. Nhưng nếu bạn thấy rằng bạn phải thay đổi chủ sở hữu tài khoản, hãy làm theo các bước sau để thực hiện.

<div id="important-2" />

> 🚧 **Quan trọng!**
>
> Phải thay đổi chủ sở hữu tài khoản thủ công theo các bước dưới đây. Không thể thực hiện các thao tác này từ trang **User management**.

<div id="1assign-a-team-member-the-admin-role" />

#### #1–Gửi yêu cầu qua email

Để bắt đầu quá trình thay đổi chủ sở hữu tài khoản, hãy gửi yêu cầu email tới AppsFlyer **từ email của chủ sở hữu tài khoản hiện tại.**

* Đảm bảo rằng đây là địa chỉ email của chủ sở hữu tài khoản hiện tại được hiện giống như trong tài khoản AppsFlyer của bạn.
* Nếu chủ sở hữu tài khoản hiện tại đã rời khỏi công ty của bạn, hãy yêu cầu đội ngũ CNTT của bạn cho phép bạn gửi email từ địa chỉ của họ.

Đưa các thông tin sau vào trong yêu cầu của bạn:

| Gửi đến: | CSM AppsFlyer của bạn hoặc hello@appsflyer.com |
| --- | --- |
| CC: | Email của chủ sở hữu tài khoản mới |
| Chủ đề: | Yêu cầu thay đổi chủ sở hữu tài khoản cho `{account name}` |
| Nội dung: | Nội dung ngắn bao gồm tên và chức danh của chủ sở hữu tài khoản mới |

Sử dụng email mẫu này để tham khảo:

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

<div id="3next-steps" />

#### #2–Các bước tiếp theo

Khi thay đổi đã được xử lý, bạn sẽ nhận được thông báo qua email từ AppsFlyer.

* Nếu bạn muốn chủ sở hữu tài khoản trước đó tiếp tục sử dụng tài khoản AppsFlyer của mình, [hãy tạo người dùng mới](/docs/user-management#creating-users) cho họ và chỉ định họ vào vai trò mới.
* Các API sử dụng token v2 không bị ảnh hưởng khi thay đổi chủ sở hữu tài khoản. Tuy nhiên, nếu bạn muốn đặt lại token, hãy truy cập trang token API và <Anchor target="_blank" href="/marketers/vi/docs/managing-appsflyer-tokens#đặt-lại-mã-thông-báo-api">đặt lại mã theo cách thủ công</Anchor> sau khi thay đổi chủ sở hữu.

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="Khắc phục sự cố 'Không thể tạo người dùng này'">

Nếu bạn nhận được thông báo lỗi *Can’t create this user* khi nhập địa chỉ email của người dùng mới, điều đó thường có nghĩa là email đã được liên kết với người dùng AppsFlyer (trong tài khoản của bạn hoặc tài khoản khác). Thực hiện theo các bước phù hợp với tình huống của bạn:

Nếu người dùng có trong tài khoản của bạn:

* Kiểm tra xem người dùng đã kích hoạt tài khoản của họ chưa. Nếu không, [hãy gửi lại lời mời](/docs/user-management#resending-a-user-invitation) nếu được yêu cầu.
* Nếu người dùng đã kích hoạt tài khoản của họ, hãy yêu cầu họ thử đăng nhập lại bằng địa chỉ email liên kết với người dùng của họ. Khuyên họ làm theo các bước về **Forgot password** nếu cần thiết.

Nếu email của người dùng được sử dụng trong một tài khoản khác hoặc bạn không thể xác định tài khoản mà email của người dùng được sử dụng, hãy chọn một trong các tùy chọn sau:

* Xóa chúng khỏi tài khoản khác và thêm chúng vào tài khoản của bạn (yêu cầu bạn hoặc người dùng có các quyền cần thiết trong tài khoản kia); hoặc
* Thêm chúng vào tài khoản của bạn bằng một địa chỉ email khác. Đây phải là một địa chỉ email hợp lệ mà họ sử dụng để nhận email; hoặc
* Liên hệ với Quản lý Hỗ trợ Khách hàng (CSM) hoặc gửi email đến nhóm Thu hút Khách hàng của chúng tôi theo địa chỉ [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="Gửi lại lời mời người dùng">

Nếu người dùng mới không nhận được [lời mời kích hoạt tài khoản](#activation) của họ hoặc nếu họ không kích hoạt trong vòng 48 giờ, bạn có thể gửi lại email như sau:

1. Trên thẻ **Users** , nhấp vào nút **Action** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> ở phía ngoài cùng bên phải hàng của người dùng.
   * Lưu ý rằng người dùng vẫn có biểu tượng phong bì ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png) hiển thị, cho biết họ chưa kích hoạt tài khoản của mình.
2. Chọn **Resend email invite** từ menu.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Đặt lại xác thực hai yếu tố (2FA)">

Nếu tài khoản của bạn sử dụng 2FA, có thể đôi khi bạn cần đặt lại cài đặt 2FA của người dùng. Thực hiện như sau:

1. Trên thẻ **Users** , nhấp vào nút **Action** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> ở phía ngoài cùng bên phải hàng của người dùng.
2. Chọn **Reset 2FA** từ menu.

**Lưu ý:** Quản trị viên có thể đặt lại 2FA của bất kỳ quản trị viên nào khác ngoài 2FA của chính họ hoặc của [chủ sở hữu tài khoản](#chủ-tài-khoản). Để đặt lại 2FA của chủ sở hữu tài khoản, hãy liên hệ với nhóm Hỗ trợ AppsFlyer.

</Accordion>

<div data-zendesk-anchors="background=th%C3%B4ng-tin-c%C6%A1-b%E1%BA%A3n h_01H9Q9007QP8YMPDVZ57N4M1HD=th%C3%B4ng-tin-c%C6%A1-b%E1%BA%A3n more-about-roles=vai-tr%C3%B2 h_01H9Q9007Q8CMR2RD6E4KN26YE=vai-tr%C3%B2 predefined-roles=vai-tr%C3%B2-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9Q9007Q28D43B6JRP71NDQM=vai-tr%C3%B2-%C4%91%C6%B0%E1%BB%A3c-x%C3%A1c-%C4%91%E1%BB%8Bnh-tr%C6%B0%E1%BB%9Bc h_01H9Q9007QXSGG375PR2SCS7QS=v%C3%AD-d%E1%BB%A5 custom-roles=vai-tr%C3%B2-t%C3%B9y-ch%E1%BB%89nh h_01H9Q9007QZ7F2TX8B9D1TNYPN=vai-tr%C3%B2-t%C3%B9y-ch%E1%BB%89nh temp-roles=vai-tr%C3%B2-t%E1%BA%A1m-th%E1%BB%9Di h_01H9Q9007QE8YT1DNRPNTFQWYH=vai-tr%C3%B2-t%E1%BA%A1m-th%E1%BB%9Di admin%E2%80%94a-special-role=qu%E1%BA%A3n-tr%E1%BB%8B-vi%C3%AAnm%E1%BB%99t-vai-tr%C3%B2-%C4%91%E1%BA%B7c-bi%E1%BB%87t h_01H9Q9007Q4A6KETAAGAWEPQQ9=qu%E1%BA%A3n-tr%E1%BB%8B-vi%C3%AAnm%E1%BB%99t-vai-tr%C3%B2-%C4%91%E1%BA%B7c-bi%E1%BB%87t access=quy%E1%BB%81n-truy-c%E1%BA%ADp h_01HF8N2Z8ZP3HV06XJPMQ19DTK=quy%E1%BB%81n-truy-c%E1%BA%ADp role-duplication=sao-ch%C3%A9p-vai-tr%C3%B2 h_01HF8N6DKWYKMBE35QKKB55KEM=sao-ch%C3%A9p-vai-tr%C3%B2 account-owner=ch%E1%BB%A7-t%C3%A0i-kho%E1%BA%A3n h_01HF8N69VYE3ZJVFW1ENC0XA62=ch%E1%BB%A7-t%C3%A0i-kho%E1%BA%A3n user-management-page=trang-user-management h_01H9Q9007QW1RD3MTTV01Q8QRE=trang-user-management users-tab=th%E1%BA%BB-users h_01H9Q9007QJB7XD599VTT89MFX=th%E1%BA%BB-users roles-tab=th%E1%BA%BB-roles h_01H9Q9007Q8B4VNDWZEX3Z4WNT=th%E1%BA%BB-roles managing-users=qu%E1%BA%A3n-l%C3%BD-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01H9Q9007QYSJZYZMP0C8NA98G=qu%E1%BA%A3n-l%C3%BD-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users h_01H9Q9007Q6SK4391P8C3A147N=quan-tr%E1%BB%8Dng h_01H9Q9007R3VH0NMBFX4JZ5THK=l%C6%B0u-%C3%BD h_01HAS6Z5R0BHNXVZR7V048GGC7=multiple-accounts h_01HAS6HHHZ5SFFMR741KFYVT7A=l%C6%B0u-%C3%BD-1 supported-accounts-and-users=t%C3%A0i-kho%E1%BA%A3n-v%C3%A0-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-%C4%91%C6%B0%E1%BB%A3c-h%E1%BB%97-tr%E1%BB%A3 h_01H9Z7XXE0CKRSE191ZN017MGE=t%C3%A0i-kho%E1%BA%A3n-v%C3%A0-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-%C4%91%C6%B0%E1%BB%A3c-h%E1%BB%97-tr%E1%BB%A3 adding-users-to-multiple-accounts=th%C3%AAm-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-v%C3%A0o-nhi%E1%BB%81u-t%C3%A0i-kho%E1%BA%A3n h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=th%C3%AAm-ng%C6%B0%E1%BB%9Di-d%C3%B9ng-v%C3%A0o-nhi%E1%BB%81u-t%C3%A0i-kho%E1%BA%A3n h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=ch%E1%BB%89nh-s%E1%BB%ADa-theo-c%C3%A1-nh%C3%A2n h_01H9Q9007R3QW4AYRJBTF0X7B9=ch%E1%BB%89nh-s%E1%BB%ADa-theo-c%C3%A1-nh%C3%A2n multiuser-editing=ch%E1%BB%89nh-s%E1%BB%ADa-nhi%E1%BB%81u-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01H9Q9007R4JQPKQS2HVB251GH=ch%E1%BB%89nh-s%E1%BB%ADa-nhi%E1%BB%81u-ng%C6%B0%E1%BB%9Di-d%C3%B9ng h_01H9Q9007R9M9YDMJ2YYNZDW3D=l%C6%B0u-%C3%BD-2 h_01H9Q9007RAFXB899YK6CADD9R=v%C3%AD-d%E1%BB%A5-1 h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users managing-custom-roles=qu%E1%BA%A3n-l%C3%BD-vai-tr%C3%B2-t%C3%B9y-ch%E1%BB%89nh h_01H9Q9007RQHHNHZ3M38E88YPW=qu%E1%BA%A3n-l%C3%BD-vai-tr%C3%B2-t%C3%B9y-ch%E1%BB%89nh h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6AF9PD8D3Z9GRHSR=l%C6%B0u-%C3%BD-3 h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=quan-tr%E1%BB%8Dng-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-%C4%91%E1%BA%B7c-bi%E1%BB%87t-v%C3%A0-quy-tr%C3%ACnh-b%E1%BB%95-sung h_01H9Q9007RSWFVAZQ5DNVNN7T2=c%C3%A1c-t%C3%ACnh-hu%E1%BB%91ng-%C4%91%E1%BA%B7c-bi%E1%BB%87t-v%C3%A0-quy-tr%C3%ACnh-b%E1%BB%95-sung h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-vai-tr%C3%B2-t%E1%BA%A1m-th%E1%BB%9Di h_01H9Q9007RJ0CQRGEYNEQJ2QR5=h%E1%BA%A1n-ch%E1%BA%BF-c%E1%BB%A7a-vai-tr%C3%B2-t%E1%BA%A1m-th%E1%BB%9Di h_01H9Q9007RHBYD2B6PHQRD7TWV=v%C3%AD-d%E1%BB%A5-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=quan-tr%E1%BB%8Dng-2 1%E2%80%93send-an-email-request=1g%E1%BB%ADi-y%C3%AAu-c%E1%BA%A7u-qua-email h_01H9Q9007RSA5406WXCB1E4JRK=1g%E1%BB%ADi-y%C3%AAu-c%E1%BA%A7u-qua-email 2%E2%80%93next-steps=2c%C3%A1c-b%C6%B0%E1%BB%9Bc-ti%E1%BA%BFp-theo h_01H9Q9007RZ2X9RAY8067SZETF=2c%C3%A1c-b%C6%B0%E1%BB%9Bc-ti%E1%BA%BFp-theo troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
