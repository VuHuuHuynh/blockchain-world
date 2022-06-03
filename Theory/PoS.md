# PROOF OF STAKE

---

- **PoS**(_Proof of Stake_) là một cơ chế đồng thuận phổ biến, dần thay thế PoW.
- Thay việc sử dụng sức mạnh tính toán để xác thực giao dịch, người xác thực phải stake tiền mã hóa.

## 1. PoS ?

- **Năm 2011**, PoS được giới thiệu trên diễn đàn BitcoinTalk, được đề xuất như một giải pháp cho các vấn đề của PoW.
- Cả PoW và PoS đều chung mục tiêu là đạt được "sự đồng thuận" trong block nhưng quá trình thực hiện lại hoàn toàn khác.
  - **PoW**: Cung cấp bằng chứng tính toán chuyên sâu.
  - **PoS**: Chứng minh là đã stake tiền mã hóa.

## 2. PoS hoạt động như thế nào?

- Thuật toán PoS sử dụng "_quy trình bầu cử giả ngẫu nhiên_" để chọn trình xác thực từ một nhóm các node.
- Hệ thống sử dụng kết hợp các yếu tố: tuổi stake, ngẫu nhiên, mức độ giàu có của node.
- Trong PoS, các block được "**forged**" (_rèn_) thay vì "**mined**" (_đào_).
- Hầu hết các loại tiền mã hóa PoS đều ra mắt với nguồn cung tiền ở dạng "_pre-forged_", cho phép các node hoạt động ngay lập tức.

  ### 2.1 Forged (Rèn):

  - Tham gia vào quá trình rèn: Phải khóa một số tiền nhất định vào mạng làm khoản cổ phần (_Stake_) của họ.
  - **Stake** càng lớn thì cơ hội node được chọn để làm trình xác thực rèn khối tiếp theo càng lớn.
  - Tránh việc chỉ ưu tiên node giàu nhất trong mạng -> 2 phương pháp được thêm vào quá trình lựa chọn:

    - **Lựa chọn khối ngẫu nhiên** (_Randomized Block Selection_): Các trình xác thực được chọn bằng cách tìm kiếm các node có sự kết hợp của "**giá trị băm thấp nhất**" + "**số tiền stake cao nhất**" -> Size stake công khai => **Forger** (_Thợ rèn_) tiếp theo có thể được dự đoán bởi các node khác.

    - **Lựa chọn tuổi của đồng tiền** (_Coin Age Selection_):
      - Lựa chọ dựa trên thời gian stake token.
      - `Coin age = Stake time * Amonut coin staked` (_Thời gian tiền dùng làm stake_ x _Số lượng coin đã stake_)
      - Node đã rèn được block -> Coin age = 0 --> Ngăn chặn việc các node có stake lớn thống trị blockchain.

  ### 2.2 Xác thực giao dịch:

  - Mỗi loại tiền mã hóa sử dụng thuật toán PoS và bộ quy tắc, phương pháp riêng mà được coi là sự kết hợp tốt nhất giữa họ và người dùng.
  - Khi được chọn để tạo khối tiếp theo => node sẽ kiểm tra các giao dịch hợp lệ hay không --> **Ký** --> Thêm vào blockchain.
  - Phần thưởng: Node nhận được phí giao dịch từ block và có thể là coin.
  - Từ bỏ làm **forger**, _stake + reward_ sẽ được giải phóng sau một thời gian nhất định (Để mạng lưới có một khoảng thời gian để xác thực rằng node đó không thêm block fake vào mạng).

## 3 Blockchain sử dụng PoS:

- BNB Chain
- BNB Smart Chain
- Solang
- Avalanche
- Polkadot

## 4. Ưu điểm:

- **Khả năng thích ứng:** Như cầu sử dụng blockchain thay đổi, PoS cũng vậy -> Nhiều phiên bản của PoS được ra đời -> linh hoạt, phù hợp với hầu hết các trường hợp sử dụng blockchain.
- **Tính phi tập trung:** Mỗi người dùng có thể chạy node để tạo ra block. Dù đã có những Staking pool (Giải thích rõ hơn ở Staking Pool).
- **Hiệu suất năng lượng:** Tiết kiệm năng lượng hơn so với PoW. Chi phí stake < Chi phi điện toán giải đố.
- **Khả năng mở rộng:** PoS không dựa vào "_trâu_" để tạo ra sự đồng thuận => có khả năng mở rộng hơn. Không cần "_trại trâu_" + nguồn cung năng lượng lớn --> Thêm validator vào mạng với chi phí rẻ, đơn giản, dễ tiếp cận hơn.
- **Mức độ bảo mật:** Nếu mạng phát hiện 1 giao dịch gian lận, node forger sẽ mất một phần tiền stake và không được làm forger trong một thời gian --> `Tiền stake > Reward` --> Gian lận sẽ mất nhiều hơn được.

## 5. Nhược điểm:

- **Phân nhánh:**
  - PoS không có cơ chế ngừng khuyến khích việc khai thác 2 nhánh blockchain sau một đợt **fork** (_phân nhánh_).
  - Nếu PoW, việc mined cả 2 nhánh sẽ lãng phí năng lượng, còn PoS, chi phí phát sinh ít hơn nhiều, mọi người có thể "_stake_" vào cả 2 nhánh của blockchain.
- **Khả năng tiếp cận:**
  - Để stake, cần nguồn cung token gốc của blockchain -> mua token -> cần đầu tư đáng kể để bắt đầu stake hiệu quả.
  - Với PoW, có thể mua thiết bị đào rẻ hoặc thuê -> tham gia hội miner và bắt đầu khai thác kiếm tiền.
- **Tấn công 51%:** Nếu giá token giảm hoặc blockchain có vốn hóa thấp -> Có thể dễ dàng mua lại > 50% và kiểm soát mạng lưới.

## 6. So sánh PoW và PoS:

|                      |         PoW          |               PoS                |
| :------------------- | :------------------: | :------------------------------: |
| Thiết bị cần thiết   |     Thiết bị đào     | Số tiền tối thiểu hoặc không cần |
| Tiêu thụ năng lượng  |         Cao          |               Thấp               |
| Xu hướng             |    Tập trung hóa     |        Tính phi tập trung        |
| Phương pháp xác thực | Bằng chứng tính toán |        Stake tiền mã hóa         |

- Còn nhều cơ chế PoS khác nhau trên các blockchain. Mỗi cơ chế có thêm các đặc điểm riêng.

## 7. Biến thể của PoS:

- PoS có khả năng tùy chỉnh cao.Các nhà phát triển có thẻ thay đổi cơ chế để phù hợp với từng trường hợp sử dụng cụ thể của blockchain.
  ### 7.1. Delegated Proof of Stake (DPoS) - Bằng chứng cố phần được ủy quyền:
  - DPoS cho phép stake không cần trở thành validator.
  - Người dùng có thể stake cho "validator", ủy quyền cho nó và chia sẻ reward
    - Càng nhiều người ủy quyền -> Validator có cơ hội được lựa chọn càng cao.
  ### 7.2. Nominated Proof of Stake (NPoS) - Bằng chứng cổ phần được đề cử:
  - NPoS là mô hình đồng thuận được phát triển bới **Polkadot**.
  - Gần tương đồng với **DPoS**.
  - Người dùng stake vào 1 validator độc hại -> mất hết cổ phần của họ => Trong NPoS, người được stake có thể chọn **tối đa 16 validator** -> mạng phân phối đồng đều số lượng stake cho các validator đã chọn.
  ### 7.3. Proof of Stake Authority (PoSA):
  - Cơ chế kết hợp giữa `Proof of Authority(PoA) + Proof of Stake(PoS)`
  - Cho phép các _validator_ thay nhau _forged_
  - **BNB Smart Chain** sử dụng **PoSA** để tạo ra sự đồng thuận.
  - Một nhóm gồm **21 validator** đang hoạt động đủ điều kiên tham gia, được lựa chọn theo số lượng BNB mà chúng stake hoặc được ủy quyền cho chúng. Tập hợp này được xác định hàng ngày và BNB Chain lưu trữ việc lựa chọn.

---

### Kết luận:

- Hiện tại, không còn phải dựa vào sức mạnh tính toán để tạo ra sự đồng thuận tiền mã hóa.
- PoS có nhiều ưu điểm và cho tới hiện tại PoS đang hoạt động khá hiệu quả.
- Bitcoin đang dần trở thành số ít các mạng PoW còn tồn tại và PoS đang ngày càng chiếm ưu thế.
