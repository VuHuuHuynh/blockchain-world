# PROOF OF WORK

---

- Là một cơ chế ngăn chặn chi tiêu kép.
- Đa số tiền mã hóa hiện tại sử dụng nó như là "_thuật toán đồng thuận_" - một phương pháp để bảo mật sổ cái.
- PoW là thuật toán đồng thuận đầu tiên xuất hiện và hiện vẫn đang thống trị.
- Xuất hiện trong white paper Bitcoin (2008) bởi Satoshi Nakamoto. Nhưng bản chất công nghệ đã xuất hiện rất lâu trước đó (Ví dụ: HashCash của Adam Back).

## 1. Chi tiêu kép?

- Xảy ra khi: cùng 1 khoản tiền được chi tiêu nhiều lần (Một khoản tiền dược chi cho 2 người nhận cùng một lúc).
- Tiền kỹ thuật số sẽ xảy ra vấn đề này một cách nghiệm trọng vì bản chất nó chỉ là file và có thể sao chép, gửi đi nhiều nơi nhiều người cùng lúc -> Cần ngăn chặn.

## 2. PoW cần thiết, tại sao?

- Người dùng phát các giao dịch lên mạng. Nhưng giao dịch chỉ được coi là hợp lệ nếu chúng được thêm vào blockchain.
- Blockchain cho phép mọi người nhìn thấy dữ liệu => kiểm tra tiền đã được sử dụng trước đó chưa.

=> PoW ra đời để đảm bảo user không tiêu khoản tiền mà họ không có quyền chi tiêu.Thuật toán PoW cho phép mọi người cập nhật blockchain theo các quy tắc của hệ thống.

## 3. Cách thức hoạt động:

- Blockchain đóng vai trờ là một cuốn sổ cái.
- Chúng ta không thêm các giao dịch "_từng cái một_" - thay vào đó là "_gộp nhiều giao dịch thành các khối_".
- Chúng ta thông báo các giao dịch với mạng -> Người dùng tạo ra một khối - "_Khối ứng viên_".
- Giao dịch hợp lệ: Block ứng viên ---> Block hợp lệ (Được thêm vào blockchain).

  ### 3.1 Thêm block vào blockchain thông qua PoW:

  - Chi phí thêm block không rẻ.
  - PoW yêu cầu **Miner** (người tạo khối) sử dụng một số "_tài nguyên_" của chính họ để được hưởng đặc quyền.
  - Tài nguyên đó là sức mạnh tính toán --> "_Hash_" (băm) dữ liệu block đến khi tìm thấy lời giải cho câu đố.

  ### 3.2 Hash data block:

  - Băm dữ liệu block: Chuyển nó qua một hàm băm nhằm tạo 1 block hash.
  - Block hash: hoạt động như "_dấu vân tay_" - là nhận dạng cho dữ liệu đầu vào và là duy nhất với mỗi khối.
  - Gần như là không thể đảo ngược 1 block hash để lấy dữ liệu đầu vào. Tuy nhiên khi biết 1 đầu vào thì dễ dàng xác nhận hash có chính xác hay không.

  ### 3.3 Phần thưởng?

  - Muốn nhận thưởng thì phải cung cấp dữ liệu có hash khớp với các điều kiện nhất định.
    --> Nếu muốn tạo ra một block, bạn đang chơi một trò chơi đoán.
  - Lấy thông tin về tất cả giao dịch muốn thêm và một số dữ liệu quan trọng khác -> Băm tất cả lại.
  - Vấn đề phát sinh: Dữ liệu đầu vào không đổi -> Hash không đổi -> Thêm 1 phần tử biến thiên: "Nonce"

        * Nonce: Một số thay đổi sau mỗi lần thử -> Hash khác nhau
        * Nonce là một số giả ngẫu nhiên được sử dụng làm bộ đếm trong quá trình khai thác

    **==> Đào (Mined)**

  ### 3.4 Summary:

  - **Mined = Hash(Blockchain data + Nonce)** -> Hash thỏa mãn điều kiện giao thức -> Thêm block vào mạng.
  - Khi 1 block mới được thêm, tất cả node sẽ cập nhật blockchain để cập nhật block mới vào danh sách.
  - Hiện tại, các đồng tiền mã hóa lớn có các điều kiện rất khó để thỏa mãn. Tỉ lệ hash càng cao trên mạng => càng khó tìm hash mới hợp lệ -> Đảm bảo block mới không được tìm ra quá nhanh.
  - Nhận thưởng khi tạo ra được một khối hợp lệ.
  - Biết đầu vào, có thể dễ dàng kiểm tra hash của mình - Những người không phải miner, có thể xác minh khối có hợp lệ hay không mà không tốn nhiều tài nguyên tính toán.

## 4. Gian lận? Ngăn chặn nó:

- Để ngăn chặn: Mật mã khóa công khai (**PKC**- _Public Key Cryptography_) ra đời.
- Sử dụng một số thuật toán mã hóa rành mạch cho phép bất kỳ user nào xác minh liệu ai đó có quyền chuyển tiền mà họ đang cố gắng thực hiện giao dịch chi tiêu hay không.
- Khi tạo 1 giao dịch, cần thực hiện ký giao dịch đó
- Bất kỳ ai trên mạng đều có thể so sánh "_chữ ký_" của bạn với "_PKC_" -> kiểm tra khớp không + có quyền chi tiêu không + tiền vào có lớn hơn đầu ra không.

  -> Bất kỳ block nào có 1 giao dịch không hợp lệ -> Reject -> Tốn kém, lãng hí tài nguyên + không nhận được thưởng.

  => **Trong việc xử lý gian lận, PoW thể hiện ưu điểm:** "Khiến cho việc gian lận trở nên tốn kém, nhưng lại có lợi khi hành động một cách trùng thực" (Tất cả Miner đều tìm kiềm **ROI**(_Return on Investment_) -> Kỳ vọng hành động theo cách đảm bảo doanh thu).

---

### Kết luận:

- PoW là giải pháp ban đầu cho việc "_Chi tiêu kép_", đã chứng minh là tin cậy và an toàn.
- Bitcoin chứng minh rằng: không cần các thực thể tập trung để ngăn việc chi tiêu kép.
- Việc sử dụng **_mật mã hóa_** + **_hàm băm_** + **_lý thuyết trò chơi_** => người tham gia vào một môi trường decentralized có thể đạt đưuọc đồng thuận về trạng thái của một CSDL tài chính.
