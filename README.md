# E-commerce UI Improvement

Bài tập cá nhân Buổi 1 – Chương 1: Tổng quan về phát triển ứng dụng TMĐT (Phát triển ứng dụng WEB/TMĐT – UEH)

- **Sinh viên:** Đào Ngọc Hoàng Yến
- **MSSV:** 89244020117

## 1. Giới thiệu

Dự án khảo sát website nhà thuốc trực tuyến Pharmacity và thiết kế lại khu vực **thẻ sản phẩm (Product Card)** bằng HTML5/CSS3. Thẻ mới làm nổi bật giá bán, giá gốc, mức giảm (huy hiệu %, số tiền tiết kiệm) và nút "Chọn mua", đồng thời hiển thị tốt trên điện thoại.

## 2. Website tham khảo

- Tên website: Pharmacity
- URL: https://www.pharmacity.vn/
- Khu vực đã khảo sát: Trang chủ, Danh mục sản phẩm, Chi tiết sản phẩm, Tìm kiếm, Giỏ hàng (chi tiết trong thư mục [`khao-sat/`](khao-sat/))

## 3. Chức năng

- Hiển thị danh sách sản phẩm dạng lưới (8 sản phẩm mẫu).
- Hiển thị tên, quy cách, giá bán, giá gốc gạch ngang, huy hiệu % giảm và số tiền tiết kiệm.
- Thẻ không giảm giá vẫn thẳng hàng với thẻ có giảm giá.
- Tên dài được cắt gọn tối đa 2 dòng.
- Bố cục hỗ trợ nhiều kích thước màn hình: 2 cột (điện thoại), 3 cột (từ 768px), 4 cột (từ 1024px).

## 4. Công nghệ

- HTML5
- CSS3 (CSS Variables, Grid, Flexbox, media queries mobile-first)

Không dùng backend, cơ sở dữ liệu hay thư viện bên ngoài.

## 5. Cách chạy

Mở file `index.html` bằng trình duyệt.

Bản chạy trực tiếp (GitHub Pages): `https://USERNAME.github.io/ecommerce-ui-improvement/`  *(thay USERNAME bằng tên tài khoản GitHub)*

## 6. Cải tiến đã thực hiện

**Vấn đề ban đầu:** thông tin giảm giá chưa nổi bật khi lướt nhanh trên điện thoại; khó so sánh giá gốc và giá hiện tại.

**Thay đổi đã thực hiện:**

- Giá bán đặt cỡ chữ lớn nhất, đổi sang màu đỏ khi sản phẩm có khuyến mãi.
- Giá gốc gạch ngang (`<del>`) đặt cạnh giá bán; thêm dòng "Tiết kiệm ... ₫".
- Huy hiệu `-15%`, `-30%`... đặt chồng ở góc ảnh, có chữ chứ không chỉ dựa vào màu.
- Nút "Chọn mua" nằm sát đáy thẻ, cao tối thiểu 44px để dễ bấm trên điện thoại.
- Dùng Flexbox dọc để các nút luôn thẳng hàng dù tên sản phẩm dài hay ngắn.
- Sau khi kiểm tra bằng Chrome DevTools, sửa lỗi giá gốc lúc nằm cạnh lúc nằm dưới giá bán ở độ rộng 375–414px: trên điện thoại giá gốc luôn xuống dòng riêng, từ 768px nằm cạnh giá bán.

## 7. Hỗ trợ từ AI

Sử dụng Claude để phân tích website, đề xuất bố cục, hỗ trợ viết mã HTML/CSS và giải thích mã. Sinh viên đã đối chiếu kết quả với website Pharmacity thực tế, loại bỏ những đề xuất không phù hợp, chạy thử trên trình duyệt/Chrome DevTools và tự chỉnh sửa. Chi tiết trong [`AI_USAGE.md`](AI_USAGE.md).

## 8. Cấu trúc thư mục

```text
ecommerce-ui-improvement/
├── index.html
├── css/
│   └── style.css
├── images/            # hình minh họa sản phẩm (tự thiết kế)
├── khao-sat/
│   ├── phan-tich-website.md
│   ├── phan-tich-ai.md
│   └── de-xuat-cai-tien.md
├── README.md
└── AI_USAGE.md
```

> Tên sản phẩm, giá và hình ảnh là dữ liệu mẫu phục vụ học tập, không phải dữ liệu thật của Pharmacity.
