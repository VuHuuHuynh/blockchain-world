# BLOCKCHAIN

---

## 1. Khái niệm:

- Một loại cơ sở dữ liệu đặc biệt.
- Chỉ có thể thêm ( không thể sửa hoặc xóa).
- Mỗi khối (_block_) chứa một con trỏ chỉ về khối trước đó.

## 2. Cơ chế hoạt động:

- Ưu điểm lớn nhất: User tương tác với nhau quanh một nguồn tin cậy được chia sẻ mà không cần tin tưởng lẫn nhau.
- Để chạy, xác minh trạng thái cần cài đặt phần mềm và chạy trên máy user.
- Phần mềm tương tác với các phiên bản trên máy khác (Mục đích: upload/download thông tin).

=> Từ đó, sinh ra 1 hệ sinh thái từ hàng trăm, ngàn, chục ngàn thực thể chạy và đồng bộ hóa 1 bản sao của CSDL giống hệt nhau (node) => Mạng có công suất rất lớn và luôn có sẵn.

## 3. Thêm thông tin vào blockchain:

- Không có administrator nào tồn tại trong decentralized.
- Thông tin sai được lưu => blockchain broken.
- Trong hệ thống tiền ảo, puclic/private key đảm bảo chỉ owner mới được chi tiêu số tiền họ sở hữu - Xác nhận giao dịch cần chữ ký hợp lệ.

* Đảm bảo tính đúng đắn -> Sinh ra 2 hệ thống:

  - [Proof of Work](./PoW.md)
  - [Proof of Stake](./PoS.md)

    ### 3.1. Proof of Work:

    - Ai cũng có thể đề xuất 1 block vào trong mạng. Nhưng phải hy sinh sức mạnh tính toán để đoán ra giải pháp mà giao thức đặt ra ( **Băm dữ liệu (Hash data)** nhiều lần để tạo ra một số nhỏ hơn một giá trị cụ thể) => **Khai thác (Đào)**.
    - Hash trong blockchain (Cốt lõi của việc đào tiền ảo).
    - Miner đoán đúng được giải pháp => nhận được phần thưởng là token.
    - Băm 1 chiều - biết đầu vào dễ dàng xác minh đầu ra => xác minh miner có hợp lệ không -> không hợp lệ => không nhận được thưởng + mất hết vốn.
    - PoW đang là cơ chế được thử nghiệm nhiều nhất nhưng không phải duy nhất.

    ### 3.2. Proof of State:

    - Còn khá mới so PoW (Mô tả chi tiết hơn tại [đây](./PoS.md))

## 4. Who invented blockchain?

- Những năm 90, W.Scott Stornetta và Stuart Haber xuất bản bài báo "Làm thế nào để đóng dấu thời gian một tài liệu kỹ thuật số" - thảo luận về cách thức khiến cho các tệp không thể bị chỉnh sửa hoặc giả mạo.
  - Tiếp cận chưa hoàn hảo + cần sự tin tưởng của bên thứ 3.
- Nhờ đổi mới từ các nhà khoa học máy tính -> **Cuối 2008**, _Whitepaper Bitcoin_ ra đời, người hoặc tổ chức có biệt danh là _Satoshi Nakamoto_ được coi là cha đẻ của hệ thống mô tả bên trên, đặt bước đầu cho sự phát triển của blockchain.

## 5. Blockchain có thể làm gì?

- Bitcoin: mang đến CSDL giao dịch được chia sẻ.
- Ethereum: mang đến smartcontract.
- Ứng dụng của blockchain:
  - Tiền mã hóa
  - Thanh toán có điều kiện
  - Dữ liệu phân tán
  - Chứng khoán

## 6. Công dụng của Blockchain:

- Chuỗi cung ứng: CSDL bất biến -> mang lại sự minh bạch mới cho các ngành công nghiệp
- Game
- Chăm sóc sức khỏe
- Chuyển tiền
- Nhận dạng kỹ thuật số
- IoT
- Quản trị
- Từ thiện
