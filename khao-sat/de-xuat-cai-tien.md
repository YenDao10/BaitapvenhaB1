# Nhiệm vụ 3 – Đề xuất cải tiến giao diện (Product Card)

## Bước 1. Xác định vấn đề

Khu vực hiển thị sản phẩm hiện tại đã cung cấp hình ảnh, tên sản phẩm và giá bán. Tuy nhiên, thông tin giảm giá và các điểm nổi bật của sản phẩm chưa thực sự nổi bật khi người dùng lướt nhanh trên điện thoại. Một số sản phẩm khuyến mãi cũng chưa giúp khách hàng dễ so sánh giá gốc và giá bán hiện tại.

Vì vậy, chọn cải tiến **giao diện thẻ sản phẩm (Product Card)** nhằm:

- Làm nổi bật giá khuyến mãi.
- Hiển thị rõ phần trăm giảm giá.
- Tăng khả năng nhận biết sản phẩm nổi bật.
- Cải thiện trải nghiệm trên thiết bị di động.
- Giúp khách hàng đưa ra quyết định mua hàng nhanh hơn.

## Bước 2. Phương án thiết kế (AI đề xuất, sinh viên thống nhất)

### Prompt đã dùng

```text
Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử
bằng HTML5 và CSS3.

Tôi muốn cải tiến khu vực: thẻ sản phẩm (hiển thị giá bán, giá gốc, tỷ lệ giảm giá).

Đối tượng sử dụng: khách hàng mua sắm trực tuyến tại Việt Nam.

Hãy đề xuất:
1. Bố cục giao diện.
2. Các thành phần HTML cần sử dụng.
3. Cách tổ chức CSS.
4. Cách hiển thị trên máy tính và điện thoại.
5. Những điểm cần kiểm tra về khả năng sử dụng.

Trước tiên, hãy giải thích phương án thiết kế.
Chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu.
```

### 1. Bố cục giao diện

Thẻ xếp **dọc**, từ trên xuống:

| Vùng | Nội dung |
| --- | --- |
| Ảnh | Ảnh sản phẩm tỷ lệ vuông, huy hiệu giảm giá đặt chồng ở góc trên |
| Thông tin | Tên (tối đa 2 dòng), quy cách/đơn vị (ví dụ "Hộp 60 viên") |
| Giá | Giá bán lớn, giá gốc gạch ngang bên cạnh, mức giảm |
| Hành động | Nút "Chọn mua" nằm sát đáy thẻ |

Cả trang gồm tiêu đề, rồi một lưới các thẻ (tối thiểu 4 sản phẩm mẫu theo đề bài).

### 2. Thành phần HTML

```text
<header>            tiêu đề trang
<main>
  <section>         khu vực sản phẩm (có <h2>)
    <ul>            danh sách sản phẩm
      <li>
        <article>   một thẻ sản phẩm
          <figure> + <img>      ảnh (có alt, width/height)
          <span>                huy hiệu giảm giá
          <h3>                  tên sản phẩm
          <p>                   quy cách/đơn vị
          <div> giá: <del> giá gốc + <strong> giá bán
          <button type="button"> Chọn mua
```

### 3. Cách tổ chức CSS

Một file `css/style.css` (đề bài yêu cầu tách riêng), chia theo thứ tự:

- **Biến màu/cỡ chữ** ở `:root` (CSS variables): đổi một chỗ là đổi cả trang.
- **Reset/base** nhẹ: `box-sizing`, font, margin.
- **Layout lưới**: dùng CSS Grid cho danh sách.
- **Thẻ và thành phần**: đặt tên theo kiểu BEM (`.product-card`, `.product-card__price`, `.product-card--sale`...).
- **Trạng thái**: `:hover`, `:focus-visible` cho nút và thẻ.
- **Media queries** ở cuối (mobile-first).

Kỹ thuật chính để các nút thẳng hàng: thẻ dùng Flexbox dọc, phần thông tin chiếm hết chỗ trống để đẩy nút xuống đáy.

### 4. Hiển thị máy tính và điện thoại

| Màn hình | Số cột | Ghi chú |
| --- | --- | --- |
| Điện thoại (dưới ~600px) | 2 cột | Nút rộng hết thẻ, dễ bấm bằng ngón cái |
| Máy tính bảng (~768px) | 3 cột | |
| Máy tính (từ ~1024px) | 4 cột | Giới hạn chiều rộng nội dung ở giữa trang |

Số cột trên điện thoại là lựa chọn thiết kế, không phải kết luận từ khảo sát; cần đối chiếu với Pharmacity trên điện thoại.

### 5. Điểm cần kiểm tra về khả năng sử dụng

- **Phân cấp thông tin:** nhìn thoáng qua có thấy giá bán đầu tiên không?
- **Tên dài:** cắt gọn 2 dòng thì thẻ có còn đều chiều cao không?
- **Thẻ không giảm giá:** bố cục có bị lệch so với thẻ có giảm giá không?
- **Độ tương phản chữ/nền** đủ đọc; mức giảm có chữ chứ không chỉ dựa vào màu.
- **Vùng bấm** của nút đủ lớn trên điện thoại (khoảng 44px cao).
- **Phím Tab:** đi qua được các nút và thấy rõ viền focus.
- **Chrome DevTools** ở các độ rộng 320, 375, 768, 1024, 1440px: có tràn chữ hay vỡ lưới không?
- **Định dạng giá** kiểu Việt Nam ("841.500 ₫") và ảnh có thuộc tính `alt`.

## Bước 3. Tạo mã nguồn

Mã nguồn hoàn chỉnh nằm ở `index.html` và `css/style.css`. Trang có 8 sản phẩm mẫu, trong đó có thẻ không giảm giá (sản phẩm 5, 8) và thẻ có tên rất dài (sản phẩm 7) để kiểm tra các tình huống ở mục 5.
