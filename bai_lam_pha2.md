# BÀI LÀM PHA 2 

- **Họ tên:** VĂN HỮU LUÂN
- **Lớp:**CNTT1
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé ra JSON

**KET QUA AI**

```text
[
{
"ma_goi": "SVT",
"ngay_su_kien": "2026-12-20",
"nguoi_lon": 2,
"tre_em": 1,
"loai_ve": "thuong",
"ghi_chu": null
},
{
"ma_goi": "FZ",
"ngay_su_kien": "2027-01-05",
"nguoi_lon": 3,
"tre_em": 0,
"loai_ve": null,
"ghi_chu": "hỗ trợ xe lăn"
},
{
"ma_goi": "VIP",
"ngay_su_kien": null,
"nguoi_lon": 4,
"tre_em": 0,
"loai_ve": "vip",
"ghi_chu": "hỗ trợ tìm chỗ cho người khiếm thị"
}
]
```

**Link trò chuyện:**https://share.gemini.google/jDjeEQ7OsEUw

## 4.3. Báo giá vé bằng Chain-of-Thought

**KET QUA AI**

```text
**Tóm tắt thông tin từ yêu cầu của khách hàng:**

* **Gói vé:** SVT – Sân Vận Động ($1.200.000\text{ đồng/người lớn}$)
* **Số lượng khách:**
* Người lớn: $5\text{ người}$ (trong đó có $1\text{ người}$ chọn khu ghế ưu tiên).
* Trẻ em: $2\text{ bé}$ ($8\text{ tuổi}$ và $10\text{ tuổi}$) và $1\text{ bé}$ ($3\text{ tuổi}$).



---

**Chi tiết tính tiền theo từng bước:**

**Bước 1: Tiền người lớn**

* **Kiến thức áp dụng:** Phép nhân số lượng với đơn giá ($T_{\text{người lớn}} = N_{\text{người lớn}} \times \text{Đơn giá SVT}$).
* **Tính toán:**

$$5 \times 1.200.000 = 6.000.000\text{ (đồng)}$$



**Bước 2: Tiền trẻ em**

* **Kiến thức áp dụng:** Quy tắc tính phần trăm ($a\% = \frac{a}{100}$) và quy tắc làm tròn độ tuổi theo quy định của Ban tổ chức:
* Trẻ từ 5 đến 11 tuổi: tính $70\%$ giá vé người lớn. Nhóm có 2 bé (8 tuổi và 10 tuổi) thuộc diện này.
* Trẻ dưới 5 tuổi: miễn phí ($0\text{ đồng}$). Nhóm có 1 bé 3 tuổi thuộc diện này.


* **Tính toán:**
* Giá vé 1 trẻ em (từ 5–11 tuổi):

$$1.200.000 \times 70\% = 1.200.000 \times \frac{70}{100} = 840.000\text{ (đồng)}$$


* Tổng tiền vé cho 2 trẻ em (8 tuổi, 10 tuổi) và 1 bé (3 tuổi):

$$(2 \times 840.000) + (1 \times 0) = 1.680.000\text{ (đồng)}$$





**Bước 3: Tiền vé (chưa giảm giá)**

* **Kiến thức áp dụng:** Phép cộng tổng hợp ($T_{\text{vé}} = T_{\text{người lớn}} + T_{\text{trẻ em}}$).
* **Tính toán:**

$$6.000.000 + 1.680.000 = 7.680.000\text{ (đồng)}$$



**Bước 4: Giảm giá nhóm**

* **Kiến thức áp dụng:** Điều kiện áp dụng chiết khấu nhóm (nhóm có từ 5 người lớn trở lên được giảm $5\%$ trên tổng tiền vé) và phép tính phần trăm.
* **Tính toán:**
* Vì nhóm có đủ $5\text{ người lớn}$ nên được giảm $5\%$ tiền vé:

$$7.680.000 \times 5\% = 7.680.000 \times \frac{5}{100} = 384.000\text{ (đồng)}$$


* Tiền vé sau khi đã trừ giảm giá:

$$7.680.000 - 384.000 = 7.296.000\text{ (đồng)}$$





**Bước 5: Phụ thu**

* **Kiến thức áp dụng:** Phép nhân chi phí phát sinh cố định ($T_{\text{phụ thu}} = N_{\text{ghế ưu tiên}} \times \text{Đơn giá phụ thu}$). Lưu ý phụ thu không được áp dụng giảm giá.
* **Tính toán:**

$$1 \times 300.000 = 300.000\text{ (đồng)}$$



**Bước 6: Tổng tiền**

* **Kiến thức áp dụng:** Công thức tổng thanh toán ($\text{Tổng tiền} = \text{Tiền vé sau giảm} + \text{Phụ thu}$).
* **Tính toán:**

$$7.296.000 + 300.000 = 7.596.000\text{ (đồng)}$$



---

**Bảng tổng hợp hóa đơn:**

| Hạng mục | Số lượng | Thành tiền (đồng) |
| --- | --- | --- |
| Vé người lớn (SVT) | 5 | 6.000.000 |
| Vé trẻ em (5 – 11 tuổi) | 2 | 1.680.000 |
| Vé trẻ em (dưới 5 tuổi) | 1 | 0 |
| **Tạm tính tiền vé** |  | **7.680.000** |
| Giảm giá nhóm (5%) |  | -384.000 |
| Phụ thu ghế ưu tiên | 1 | 300.000 |
| **Tổng thanh toán** |  | **7.596.000** |

[RESULT: 7.596.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/iOIspU1RpNDx

### b) Kiểm tra kết quả AI
**Bước 1:** $6.000.000\text{ đồng}$

**Bước 2:** $1.680.000\text{ đồng}$

**Bước 3:** $7.680.000\text{ đồng}$

**Bước 4:** $384.000\text{ đồng}$

**Bước 5:** $300.000\text{ đồng}$

**Bước 6:** $7.596.000\text{ đồng}$

[RESULT: 7.596.000 đồng]

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
"loai_su_co": "sai_khu_vuc",
"so_khach": 2,
"so_hiep_bi_anh_huong": 2,
"tom_tat": "Khán giả mua vé có mái che nhưng bị xếp sang khu không mái trong 2 hiệp đầu khiến ghế ướt."
}
```

**Link trò chuyện:**https://share.gemini.google/KjlEBYk05gqa

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **1. Đúng thông tin** *(Tối đa 5.0đ)* | **0.0/5.0** | - **Trích nguyên văn:** *"Vé Sân Vận Động bên em giá 1.000.000đ/người"* và *"Anh huỷ trước 3 ngày thì được hoàn tiền đầy đủ nha anh."*<br>

<br>- **Lý do sai:** Sai hoàn toàn cả 2 thông tin chuẩn (giá chuẩn là 1.200.000 đồng/người lớn; huỷ trước từ 3 đến 6 ngày chỉ hoàn 50%, tức là mất 50% tiền vé). | - **Câu sửa đề xuất:** *"Hiện tại, giá vé gói Sân Vận Động (SVT) là 1.200.000 đồng/người lớn. Về chính sách hoàn huỷ, nếu anh huỷ vé trước sự kiện từ 3 đến 6 ngày, Ban tổ chức sẽ hoàn lại 50% giá trị vé (tức phí huỷ vé là 50%)."* |
| **2. Đầy đủ** *(Tối đa 3.0đ)* | **2.0/3.0** | - **Trích nguyên văn:** *"Anh cần gì cứ nhắn em nhé!"*<br>

<br>- **Lý do thiếu sót:** Đã trả lời đủ 2 ý hỏi của khán giả nhưng kết thúc chung chung, thiếu phần chủ động mời khán giả cung cấp ngày trận đấu và số lượng vé để hỗ trợ đặt vé. | - **Câu sửa đề xuất:** *"Anh vui lòng cho em biết ngày diễn ra trận đấu và số lượng vé anh dự định đặt để em hỗ trợ kiểm tra và giữ chỗ cho mình nhé!"* |
| **3. Giọng điệu** *(Tối đa 2.0đ)* | **1.0/2.0** | - **Trích nguyên văn:** *"...xem rất đã luôn ạ."* và *"...nha anh."*<br>

<br>- **Lý do sai:** Sử dụng từ ngữ mang tính suồng sã, văn nói thân mật quá mức (*"rất đã"*, *"nha"*), chưa đảm bảo tính chuẩn mực, chuyên nghiệp của Ban tổ chức giải đấu. | - **Câu sửa đề xuất:** Thay *"xem rất đã luôn ạ"* bằng *"với vị trí quan sát toàn cảnh sân đấu rất tốt ạ"*; thay *"nha anh"* bằng *"ạ"*. |

**Tổng điểm: 3.0/10**
```

**Link trò chuyện:**https://share.gemini.google/9hQPhWT0c9X8
