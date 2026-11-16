# AI Usage Log

## 1. Công cụ AI

Tên công cụ: Claude (Anthropic)

## 2. Mục đích sử dụng

- Phân tích cấu trúc và giao diện website Pharmacity theo 5 khu vực.
- Đề xuất bố cục, thành phần HTML và cách tổ chức CSS cho thẻ sản phẩm.
- Hỗ trợ viết mã HTML/CSS và giải thích mã nguồn.

## 3. Prompt đã sử dụng

**Prompt 1 – Phân tích website** (đầy đủ trong [`khao-sat/phan-tich-ai.md`](khao-sat/phan-tich-ai.md))

> Bạn là chuyên gia phân tích nghiệp vụ và thiết kế trải nghiệm người dùng cho website thương mại điện tử. Tôi đang khảo sát website Pharmacity (https://www.pharmacity.vn/). Hãy lập bảng phân tích 5 khu vực (Trang chủ, Danh mục sản phẩm, Chi tiết sản phẩm, Tìm kiếm, Giỏ hàng): mục đích, thành phần giao diện, điểm thuận tiện, một vấn đề có thể phát sinh, một đề xuất cải tiến. Không khẳng định tính năng chưa kiểm chứng; phân biệt rõ nhận xét dựa trên quan sát và đề xuất của AI.

**Prompt 2 – Đề xuất giao diện** (đầy đủ trong [`khao-sat/de-xuat-cai-tien.md`](khao-sat/de-xuat-cai-tien.md))

> Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử bằng HTML5 và CSS3. Tôi muốn cải tiến khu vực thẻ sản phẩm. Đối tượng: khách hàng mua sắm trực tuyến tại Việt Nam. Hãy đề xuất bố cục, thành phần HTML, cách tổ chức CSS, cách hiển thị trên máy tính và điện thoại, điểm cần kiểm tra về khả năng sử dụng. Trước tiên hãy giải thích phương án; chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu.

**Prompt 3 – Tạo mã nguồn**

> Dựa trên phương án đã thống nhất, hãy tạo một trang giao diện thương mại điện tử bằng HTML5 và CSS3. Yêu cầu: có tiêu đề và khu vực sản phẩm; tối thiểu 4 sản phẩm mẫu; mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác; bố cục phù hợp máy tính và điện thoại; HTML cấu trúc rõ ràng; CSS tách file riêng; không backend/cơ sở dữ liệu; không đưa thư viện không cần thiết. Giải thích cách chạy trang web và những phần cần kiểm tra.

## 4. Kết quả AI đề xuất

- **Phân tích website:** bảng 5 khu vực với mục đích, thành phần giao diện, điểm thuận tiện, vấn đề và đề xuất cải tiến.
- **Phương án thiết kế:** thẻ sản phẩm xếp dọc (ảnh + huy hiệu giảm giá, tên/quy cách, giá, nút mua); HTML ngữ nghĩa (`header`, `main`, `section`, `ul/li`, `article`, `figure`, `del`, `button`); CSS tách file, dùng biến, Grid, Flexbox, BEM, mobile-first; 2/3/4 cột theo màn hình.
- **Mã nguồn:** `index.html` và `css/style.css` với 8 sản phẩm mẫu (có thẻ không giảm giá và thẻ tên rất dài để kiểm thử), cùng hình minh họa trong `images/`.

## 5. Kiểm tra và điều chỉnh

**Đã kiểm tra:**

- Đối chiếu bảng phân tích của AI với website Pharmacity thực tế.
- Mở `index.html` trên trình duyệt; dùng Chrome DevTools xem ở các độ rộng 320, 375, 768, 1024, 1440px.
- Kiểm tra ảnh, nội dung, bố cục; thẻ không giảm giá và thẻ tên dài; phím Tab và viền focus.

**Không sử dụng / điều chỉnh đề xuất của AI:**

- Không dùng đề xuất "Tóm tắt nhanh" ở chi tiết sản phẩm: website đã tóm tắt đầy đủ, và thông tin thuốc là thông tin đặc trưng bắt buộc.
- Không dùng đề xuất bổ sung thông tin tiết kiệm/thời gian giao/tổng tiền ở giỏ hàng: website đã có.
- Bổ sung nhận xét của bản thân về cách chia danh mục (theo nhu cầu sử dụng, vào từng mục mới chia chi tiết).
- Số cột trên điện thoại (2 cột) là lựa chọn thiết kế của AI, được kiểm tra lại bằng DevTools.

**Điểm tự phát hiện và sửa:**

- **Phát hiện:** khi mở Chrome DevTools ở độ rộng 375px và 414px (điện thoại phổ biến), vị trí giá gốc không nhất quán: ở thẻ này giá gốc nằm cạnh giá bán (Siro: `59.500 ₫  85.000 ₫`), ở thẻ khác lại rớt xuống dòng dưới (Vitamin C, Máy đo huyết áp). Nguyên nhân: `.product-card__price` dùng `flex-wrap: wrap`, nên giá gốc chỉ xuống dòng khi giá bán dài và không đủ chỗ. Khách hàng lướt nhanh khó so sánh giá gốc – giá bán giữa các thẻ. Ở 320–360px luôn xuống dòng, từ 768px trở lên luôn nằm cạnh; lỗi chỉ xuất hiện ở khoảng 375–414px.
- **Sửa (`css/style.css`):**
  - Thêm `flex-basis: 100%` cho `.product-card__price-old`: trên điện thoại giá gốc luôn nằm một dòng riêng ngay dưới giá bán.
  - Trong `@media (min-width: 768px)` đặt lại `flex-basis: auto`: màn hình rộng đủ chỗ nên giá gốc nằm cạnh giá bán.
- **Kết quả:** đo lại ở 320, 360, 375, 414, 768, 1024, 1440px, tất cả thẻ giảm giá đều có bố cục giá giống nhau trong cùng một độ rộng; các nút vẫn thẳng hàng, không tràn ngang.
- **Vai trò của phần đã sửa:** `flex-wrap` cho phép phần tử xuống dòng khi hết chỗ; `flex-basis: 100%` buộc phần tử chiếm trọn một dòng của vùng flex (nên luôn bị đẩy xuống dòng mới); media query `min-width: 768px` ghi đè lại giá trị đó cho màn hình rộng (cách viết mobile-first).

## 6. Phần tôi hiểu và có thể giải thích

- **`:root` và CSS variables** (`--color-sale`, `--color-primary`, `--gap`...): lưu màu và khoảng cách một chỗ; đổi một giá trị là đổi cả trang.
- **`.product-grid`** dùng CSS Grid: `repeat(2, minmax(0, 1fr))` cho điện thoại, mở rộng thành 3 và 4 cột bằng `@media (min-width: 768px / 1024px)` (mobile-first). `minmax(0, 1fr)` giúp cột không bị tràn khi chữ dài.
- **`.product-card`** dùng Flexbox dọc với `height: 100%`: các thẻ cùng hàng cao bằng nhau; `.product-card__body { flex: 1 }` đẩy nút xuống sát đáy nên mọi nút thẳng hàng.
- **`.product-card__title`** dùng `-webkit-line-clamp: 2` và `min-height`: tên dài bị cắt ở 2 dòng, tên ngắn vẫn chiếm đủ 2 dòng để giá thẳng hàng.
- **`.product-card__media`** là `position: relative`, huy hiệu `.product-card__badge` là `position: absolute` để đè lên góc ảnh; ảnh dùng `aspect-ratio: 1 / 1` và `object-fit: cover`.
- **Giá:** `<strong>` cho giá bán, `<del>` cho giá gốc gạch ngang, kèm `visually-hidden` "Giá gốc" để trình đọc màn hình hiểu ngữ cảnh; `.product-card--sale` đổi giá bán sang màu đỏ chỉ khi có khuyến mãi.
- **Nút:** `<button type="button">` cao tối thiểu 44px; `:hover` đổi màu, `:focus-visible` hiện viền khi dùng phím Tab; `aria-label` nêu rõ sản phẩm.
- **HTML ngữ nghĩa:** `header`, `main`, `section` (có `h2` ẩn bằng `.visually-hidden`), `ul/li`, `article`, `figure`; ảnh có `alt`, `width`/`height` để tránh nhảy bố cục, `loading="lazy"`.
- **`prefers-reduced-motion`:** tắt hiệu ứng chuyển động cho người dùng đã tắt animation trong hệ điều hành.
