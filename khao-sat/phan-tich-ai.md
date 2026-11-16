# Nhiệm vụ 2 – Sử dụng AI hỗ trợ phân tích

- **Công cụ AI:** Claude (Anthropic)
- **Website phân tích:** Pharmacity – https://www.pharmacity.vn/

## Prompt 1 – Phân tích website

```text
Bạn là chuyên gia phân tích nghiệp vụ và thiết kế trải nghiệm người dùng
cho website thương mại điện tử.

Tôi đang khảo sát website: Pharmacity (https://www.pharmacity.vn/).

Hãy giúp tôi lập bảng phân tích các khu vực:
1. Trang chủ.
2. Danh mục sản phẩm.
3. Chi tiết sản phẩm.
4. Tìm kiếm.
5. Giỏ hàng.

Với mỗi khu vực, hãy nêu:
- Mục đích của chức năng.
- Thành phần giao diện cần có.
- Điểm thuận tiện đối với khách hàng.
- Một vấn đề có thể phát sinh.
- Một đề xuất cải tiến.

Không khẳng định những tính năng chưa được kiểm chứng.
Phân biệt rõ nhận xét dựa trên quan sát và đề xuất của AI.
```

## Bảng phân tích của AI (đã đối chiếu với website thực tế)

| Khu vực | Mục đích chức năng | Thành phần giao diện quan sát được | Điểm thuận tiện cho khách hàng | Vấn đề có thể phát sinh | Đề xuất cải tiến (AI) |
| --- | --- | --- | --- | --- | --- |
| 1. Trang chủ | Giới thiệu thương hiệu, điều hướng người dùng đến sản phẩm và dịch vụ chăm sóc sức khỏe | Thanh menu, ô tìm kiếm, danh mục sản phẩm, chương trình khuyến mãi, sản phẩm nổi bật, liên hệ dược sĩ, tìm nhà thuốc, tra cứu đơn hàng. | Người dùng có thể tiếp cận nhiều chức năng quan trọng ngay từ trang đầu. | Lượng thông tin và khuyến mãi hiển thị nhiều có thể khiến người dùng mới khó tập trung vào nội dung chính. | Gom các khối nội dung theo nhóm ưu tiên và tăng khoảng trắng giữa các khu vực để dễ quan sát hơn. |
| 2. Danh mục sản phẩm | Giúp người dùng duyệt sản phẩm theo nhu cầu sức khỏe hoặc nhóm điều trị | Danh mục như Thuốc, Vitamin & Khoáng chất, Tiêu hóa, Tim mạch, Tiểu đường, Mẹ và bé... Các nhóm được chia theo nhu cầu sử dụng; khi vào từng mục mới chia theo thông tin chi tiết hơn. | Cách phân loại gần với nhu cầu thực tế của người dùng ngành y tế. | Số lượng danh mục nhiều có thể gây khó khăn cho người dùng lần đầu truy cập. | Bổ sung icon minh họa và cho phép lọc nhanh theo nhu cầu sức khỏe phổ biến. |
| 3. Chi tiết sản phẩm | Cung cấp thông tin giúp khách hàng đánh giá sản phẩm trước khi quyết định mua hoặc tư vấn | Tên sản phẩm, giá bán, hình ảnh sản phẩm; một số sản phẩm hiển thị nút "Chọn mua", một số hiển thị "Cần tư vấn dược sĩ". | Người dùng nhận biết được sản phẩm nào có thể mua trực tiếp và sản phẩm nào cần được tư vấn trước. | Thông tin chuyên môn dược phẩm có thể khó hiểu đối với người không có kiến thức y tế. | Thêm phần "Tóm tắt nhanh" gồm công dụng chính, đối tượng sử dụng và lưu ý quan trọng. |
| 4. Tìm kiếm | Giúp người dùng tìm sản phẩm hoặc nhóm sản phẩm mong muốn nhanh chóng | Ô tìm kiếm nổi bật ở đầu trang; xuất hiện các từ khóa gợi ý như chống nắng, cảm cúm, đường huyết... | Người dùng không cần duyệt nhiều menu vẫn có thể tiếp cận sản phẩm mong muốn. | Từ khóa y khoa hoặc tên thuốc có thể làm người dùng nhập sai chính tả. | Bổ sung gợi ý từ khóa gần đúng (auto-correct) và nhóm kết quả theo danh mục. |
| 5. Giỏ hàng | Hỗ trợ quá trình thu thập sản phẩm trước khi thanh toán | Trong phạm vi khảo sát công khai, có thể quan sát được nút "Chọn mua" trên nhiều sản phẩm. | Nút hành động mua hàng được hiển thị khá rõ trên danh sách sản phẩm. | Chưa kiểm chứng được toàn bộ luồng giỏ hàng và thanh toán trong quá trình khảo sát. | Nếu triển khai cải tiến, nên hiển thị thông tin tiết kiệm chi phí, thời gian giao hàng dự kiến và tổng tiền tạm tính rõ hơn. |

## Đối chiếu và hiệu chỉnh của sinh viên

Sau khi mở website Pharmacity để kiểm tra, sinh viên loại bỏ hoặc điều chỉnh các đề xuất của AI không phù hợp:

| Khu vực | Đề xuất của AI | Kết quả đối chiếu của sinh viên |
| --- | --- | --- |
| Chi tiết sản phẩm | Thêm phần "Tóm tắt nhanh" | **Không dùng.** Website đã tóm tắt đầy đủ thông tin; với thuốc, nội dung là thông tin đặc trưng bắt buộc nên không cần thêm phần tóm tắt. |
| Giỏ hàng | Hiển thị tiết kiệm chi phí, thời gian giao hàng dự kiến, tổng tiền tạm tính | **Không dùng.** Website đã có các thông tin này. |
| Danh mục sản phẩm | Mô tả cách chia nhóm | **Bổ sung:** danh mục chia theo nhu cầu sử dụng; khi vào từng mục mới chia theo thông tin chi tiết hơn. |

## Phân biệt rõ giữa Quan sát và Đề xuất

### Nội dung quan sát được từ website

- Có thanh tìm kiếm ở đầu trang.
- Có danh mục sản phẩm theo nhóm bệnh lý và nhu cầu sức khỏe.
- Có chức năng liên hệ dược sĩ.
- Có chức năng tra cứu đơn hàng.
- Có sản phẩm hiển thị nút "Chọn mua".
- Có sản phẩm hiển thị trạng thái "Cần tư vấn dược sĩ".

### Nội dung là đề xuất của AI

- Tăng khoảng trắng trong giao diện.
- Bổ sung icon cho danh mục.
- Thêm phần tóm tắt công dụng sản phẩm.
- Hỗ trợ sửa lỗi chính tả trong tìm kiếm.
- Cải thiện hiển thị thông tin tại giỏ hàng.

Các đề xuất trên là ý kiến phân tích UX/UI, không phải khẳng định website hiện đang có hoặc đang thiếu các chức năng này.

## Kết luận

Từ góc độ phát triển ứng dụng Web/Thương mại điện tử, Pharmacity là một website phù hợp để khảo sát vì có đầy đủ các khu vực cốt lõi của một hệ thống TMĐT như trang chủ, danh mục sản phẩm, tìm kiếm và khu vực mua hàng. Trong phạm vi khảo sát, khu vực **thẻ sản phẩm (Product Card)** là đối tượng phù hợp nhất để cải tiến bằng HTML/CSS vì xuất hiện tại nhiều màn hình và ảnh hưởng trực tiếp đến trải nghiệm mua sắm của người dùng.
