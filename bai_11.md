Phần 1: Thiết kế kiến trúc

1.1. Module và luồng dữ liệu

&#x20;\[Gặp khái niệm khó]

&#x20;         │

&#x20;         ▼

&#x20;\[Viết Prompt 3 phần]  ◄── templates/prompt-template.md

&#x20;         │

&#x20;         ▼

&#x20;\[AI trả lời]

&#x20;         │

&#x20;         ▼

&#x20;\[Kiểm chứng: đối chiếu tài liệu chính thức / chạy thử]

&#x20;         │

&#x20;         ├── Đúng ──► ✅ Đã xác minh

&#x20;         ├── Nghi ──► ⚠️ Chưa chắc

&#x20;         └── Sai  ──► ❌ Hallucination (ghi rõ chỗ sai)

&#x20;         │

&#x20;         ▼

&#x20;\[Lưu file: notes/YYYY-MM-DD\_mon\_khai-niem.md]

&#x20;         │

&#x20;         ▼

&#x20;\[Cập nhật INDEX.md (bảng + task list) và TAGS.md]

knowledge-base/

├── INDEX.md                  ← file cổng chính

├── TAGS.md                   ← tra cứu theo tag

├── templates/

│   └── prompt-template.md    ← mẫu Prompt 3 phần

└── notes/

&#x20;   ├── 2026-10-12\_it101\_markdown-parser.md

&#x20;   ├── 2026-10-14\_ai101\_token-ai.md

&#x20;   └── 2026-10-15\_skl103\_sbi-feedback.md

Module	Vai trò

INDEX.md	Cổng vào, phân loại theo môn, theo dõi tiến độ

TAGS.md	Phân loại chéo theo chủ đề

templates/	Mẫu dùng lại, giúp các file đồng nhất

notes/	Mỗi file một khái niệm (nguyên tắc “1 file = 1 ý”)

1.2. Quy tắc đặt tên file



Format: YYYY-MM-DD\_mon-hoc\_khai-niem.md

Ví dụ: 2026-10-14\_ai101\_token-ai.md



Quy tắc	Lý do

Ngày YYYY-MM-DD đứng đầu	File tự sắp xếp theo thời gian, ôn thi dễ lọc “tuần này học gì”

Mã môn ở vị trí thứ hai, chữ thường	Lọc nhanh theo môn bằng \*it101\*

Tên khái niệm đứng cuối	Nhìn tên là biết nội dung

Chữ thường, không dấu, nối bằng -	Tránh lỗi link do khoảng trắng và tiếng Việt có dấu

\_ ngăn cách 3 phần, - nối từ trong một phần	Phân biệt rõ ranh giới ngày / môn / khái niệm

Phần 2: Sản phẩm hoàn chỉnh

2.1. File INDEX.md

markdown

\# 📚 Knowledge Base Cá nhân: Học kỳ 1, Năm nhất



Kho kiến thức cá nhân được \*\*AI giải thích\*\* và \*\*mình kiểm chứng lại\*\*, lưu hoàn toàn bằng Markdown để tra cứu nhanh và phát triển suốt 4 năm đại học.



> 💡 \*\*Quy ước:\*\* mỗi file ghi trạng thái xác minh: ✅ đã xác minh, ⚠️ chưa chắc, ❌ AI trả lời sai.



\## 🗂️ Phân loại theo môn học



| Môn | Khái niệm | File chi tiết | Trạng thái | Từ khóa |

|:---|:---|:---|:---:|:---|

| \*\*IT101\*\* | Markdown Parser | \[Markdown Parser](notes/2026-10-12\_it101\_markdown-parser.md) | ✅ | markdown, parser, cú pháp, render |

| \*\*AI101\*\* | Token trong AI | \[Token AI](notes/2026-10-14\_ai101\_token-ai.md) | ⚠️ | token, tokenizer, context window, LLM |

| \*\*SKL103\*\* | Phản hồi SBI | \[SBI Feedback](notes/2026-10-15\_skl103\_sbi-feedback.md) | ✅ | sbi, góp ý, feedback, giao tiếp |



\## 🏷️ Tra cứu theo tag



Xem toàn bộ tag tại \[TAGS.md](TAGS.md).



\## 📈 Tiến độ học



\- \[x] IT101: Markdown Parser

\- \[x] SKL103: Mô hình SBI

\- \[x] AI101: Token (đã học, \*còn chờ kiểm chứng\*)

\- \[ ] IT101: Git và GitHub Pages

\- \[ ] SKL103: Closed-loop và Họp 15 phút

\- \[ ] AI101: Prompt Engineering



\*\*Thống kê:\*\* 3 / 6 chủ đề hoàn thành.



\## 🔍 Cách tìm nhanh



1\. Dùng cột \*\*Từ khóa\*\* trong bảng trên.

2\. Mở \[TAGS.md](TAGS.md) để tìm theo tag.

3\. Tìm toàn văn trong VS Code: `Ctrl + Shift + F`.

2.2. File chi tiết: notes/2026-10-12\_it101\_markdown-parser.md

markdown

\# 🧩 Markdown Parser



\*\*Môn:\*\* IT101 | \*\*Ngày học:\*\* 2026-10-12 | \*\*Trạng thái:\*\* ✅ Đã xác minh

\*\*Tags:\*\* `#markdown` `#parser` `#it101`



\[⬅️ Về INDEX](../INDEX.md)



\## 1. Khái niệm



\*\*Markdown parser\*\* là chương trình đọc văn bản thô `.md` và chuyển thành \*HTML\* để trình duyệt hiển thị. Nó nhận diện cú pháp (`#`, `\*\*`, `-`...) rồi đổi thành thẻ tương ứng.



\## 2. Ví dụ minh họa



```markdown

\## Tiêu đề cấp 2

Đây là \*\*chữ đậm\*\* và \*chữ nghiêng\*.

\- Mục danh sách

```



Parser sẽ biến đoạn trên thành:



```html

<h2>Tiêu đề cấp 2</h2>

<p>Đây là <strong>chữ đậm</strong> và <em>chữ nghiêng</em>.</p>

<ul><li>Mục danh sách</li></ul>

```



\## 3. Các lỗi hay gặp



| Lỗi | Hậu quả |

|:---|:---|

| Thiếu dấu cách sau `#` | Không thành heading |

| Thiếu `https://` trong link | Link thành đường dẫn tương đối, lỗi 404 |

| Xóa hàng phân cách của bảng | Bảng thành đoạn văn thường |



> 🤖 \*\*Ghi chú từ AI:\*\* parser theo chuẩn CommonMark xử lý văn bản theo 2 bước: chia thành các khối (block), rồi xử lý định dạng bên trong (inline).



\## 4. Việc cần làm



\- \[x] Hiểu parser là gì

\- \[x] Nhớ 3 lỗi cú pháp thường gặp

\- \[ ] Thử viết parser mini bằng Python



\## 5. Tài liệu tham khảo



\- \[CommonMark Spec](https://spec.commonmark.org/)

\- \[GitHub Flavored Markdown](https://github.github.com/gfm/)

2.3. File tạo từ AI: notes/2026-10-14\_ai101\_token-ai.md

markdown

\# 🔤 Token trong AI



\*\*Môn:\*\* AI101 | \*\*Ngày học:\*\* 2026-10-14 | \*\*Nguồn:\*\* AI giải thích

\*\*Trạng thái:\*\* ⚠️ Chưa chắc (còn 1 điểm cần kiểm chứng)

\*\*Tags:\*\* `#token` `#llm` `#ai101` `#nguon-ai`



\[⬅️ Về INDEX](../INDEX.md)



\## 1. Prompt đã gửi (3 phần)



> \*\*Bối cảnh:\*\* Mình là sinh viên năm nhất CNTT, đang học môn AI101, chưa biết gì về mô hình ngôn ngữ lớn.

>

> \*\*Nhiệm vụ:\*\* Giải thích "token" trong AI là gì, vì sao AI tính phí và giới hạn độ dài theo token, và cho 1 ví dụ cụ thể.

>

> \*\*Định dạng:\*\* Trả lời bằng tiếng Việt, tối đa 200 từ, dùng ví dụ đời thường, có 1 bảng nhỏ minh họa.



\## 2. Câu trả lời của AI (dán nguyên văn)



> \*\*Token\*\* là đơn vị nhỏ nhất mà mô hình AI dùng để đọc và sinh văn bản. Mô hình không đọc từng chữ cái hay từng từ, mà cắt văn bản thành các mảnh gọi là token.

>

> - Một token có thể là \*\*một từ, một phần của từ, hoặc một dấu câu\*\*.

> - Với tiếng Anh, trung bình \*\*1 token ≈ 4 ký tự\*\*.

> - Với tiếng Việt, \*\*1 từ luôn bằng đúng 1 token\*\*.

>

> AI giới hạn và tính phí theo token vì \*\*chi phí tính toán tỷ lệ với số token\*\* phải xử lý. Mỗi mô hình có một "cửa sổ ngữ cảnh" (context window) tối đa, ví dụ 8.000 token.

>

> | Câu | Số token (ước lượng) |

> |:---|:---:|

> | `Hello world` | 2 |

> | `Xin chào` | 2 |



\## 3. Nhận xét và kiểm chứng của mình



| Nội dung AI nói | Kết quả | Ghi chú |

|:---|:---:|:---|

| Token là đơn vị văn bản mô hình xử lý | ✅ Đúng | Khớp tài liệu của nhà cung cấp |

| Token có thể là từ, một phần từ, dấu câu | ✅ Đúng | Đã thử trên công cụ đếm token |

| Tiếng Anh ≈ 4 ký tự/token | ✅ Đúng (ước lượng) | Chỉ là con số trung bình |

| \*\*Tiếng Việt: 1 từ luôn = 1 token\*\* | ❌ \*\*SAI (hallucination)\*\* | Tiếng Việt thường tốn nhiều token hơn, một từ có dấu có thể bị cắt thành 2-3 token. Chữ "luôn" là dấu hiệu đáng nghi |

| Tính phí theo token | ✅ Đúng | |

| `Xin chào` = 2 token | ⚠️ Chưa chắc | Tùy tokenizer, cần thử trực tiếp |



> ❌ \*\*CẢNH BÁO HALLUCINATION:\*\* AI khẳng định tuyệt đối "1 từ tiếng Việt luôn = 1 token". Điều này \*\*sai\*\*. Số token phụ thuộc vào \*\*tokenizer\*\* của từng mô hình, và tiếng Việt thường tốn nhiều token hơn tiếng Anh.



\*\*Bài học:\*\* AI hay sai ở những câu có từ tuyệt đối ("luôn", "chắc chắn", "100%") và ở \*\*con số cụ thể\*\*. Cần kiểm chứng những chỗ này trước khi lưu.



\## 4. Kiến thức đã chỉnh sửa (dùng để ôn thi)



\- Token là đơn vị văn bản mà mô hình xử lý.

\- Số token phụ thuộc \*\*tokenizer\*\* của từng mô hình.

\- Tiếng Anh ≈ 4 ký tự/token; tiếng Việt thường tốn nhiều token hơn.



\## 5. Việc cần làm



\- \[x] Hỏi AI và lưu câu trả lời

\- \[x] Phát hiện và đánh dấu lỗi

\- \[ ] Thử đếm token của 1 câu tiếng Việt bằng công cụ tokenizer

\- \[ ] Đổi trạng thái thành ✅ sau khi kiểm chứng xong

2.4. Cơ chế phát hiện hallucination

Bước	Cách làm

Phát hiện	Đối chiếu tài liệu chính thức; chạy thử code/công cụ; hỏi lại AI bằng câu khác; nghi ngờ từ tuyệt đối và con số cụ thể

Đánh dấu	Dòng Trạng thái (✅ / ⚠️ / ❌), bảng kiểm chứng từng ý, blockquote ❌ CẢNH BÁO HALLUCINATION

Theo dõi	Cột Trạng thái trong INDEX.md; tìm mọi chỗ sai bằng grep -r "HALLUCINATION" notes/

Sửa	Giữ nguyên câu trả lời gốc của AI, thêm phần “Kiến thức đã chỉnh sửa” bên dưới

2.5. File phụ TAGS.md (cơ chế phân loại)

markdown

\# 🏷️ Tra cứu theo Tag



\[⬅️ Về INDEX](INDEX.md)



| Tag | File |

|:---|:---|

| `#markdown` | \[Markdown Parser](notes/2026-10-12\_it101\_markdown-parser.md) |

| `#token` `#llm` | \[Token AI](notes/2026-10-14\_ai101\_token-ai.md) |

| `#nguon-ai` | \[Token AI](notes/2026-10-14\_ai101\_token-ai.md) |

| `#feedback` | \[SBI Feedback](notes/2026-10-15\_skl103\_sbi-feedback.md) |

2.6. File thứ 3: notes/2026-10-15\_skl103\_sbi-feedback.md

markdown

\# 🗣️ Mô hình phản hồi SBI



\*\*Môn:\*\* SKL103 | \*\*Ngày học:\*\* 2026-10-15 | \*\*Trạng thái:\*\* ✅ Đã xác minh

\*\*Tags:\*\* `#sbi` `#feedback` `#skl103`



\[⬅️ Về INDEX](../INDEX.md)



\## 1. Khái niệm



\*\*SBI\*\* gồm 3 bước: \*\*S\*\*ituation (tình huống), \*\*B\*\*ehavior (hành vi quan sát được), \*\*I\*\*mpact (tác động). Mục tiêu là góp ý \*vào việc, không vào người\*.



\## 2. Ví dụ



```text

S: Tối qua, trong bản nháp slide gửi lên nhóm,

B: các trang chủ yếu là chữ đen trên nền trắng, chưa có hình minh họa.

I: Mình lo người nghe dễ mất tập trung. Mình giúp cậu tìm ảnh nhé?

```



\## 3. So sánh



| Kiểu góp ý | Ví dụ | Kết quả |

|:---|:---|:---|

| Công kích | "Cậu cẩu thả quá!" | Người nghe phòng thủ |

| SBI | "Slide chưa có hình minh họa..." | Người nghe dễ tiếp nhận |



> 🤖 \*\*Ghi chú từ AI:\*\* hành vi trong B phải "quay phim được", tức là nhìn hoặc nghe thấy được, không phải kết luận về tính cách.



\## 4. Việc cần làm



\- \[x] Hiểu 3 bước S, B, I

\- \[ ] Thực hành góp ý SBI 1-on-1 với một bạn cùng nhóm



\## 5. Tài liệu



\- \[Center for Creative Leadership](https://www.ccl.org/)

Phần 3: Edge Case, tìm “Token AI” trong 50 file

Cơ chế	Cách làm	Ưu điểm	Nhược điểm

1\. Tìm toàn văn (VS Code Ctrl+Shift+F, hoặc grep -ril "token" notes/)	Gõ token, hiện ngay các file chứa chữ này	Nhanh, không cần chuẩn bị trước, tìm được cả khi quên tên file	Nhiều kết quả nhiễu; không bắt được từ đồng nghĩa; phải nhớ đúng từ khóa

2\. Bảng INDEX có cột Từ khóa	Mở INDEX.md, nhìn cột Từ khóa thấy “token, tokenizer...”	Duyệt bằng mắt, thấy tổng thể, bắt được từ đồng nghĩa nếu đã ghi	Phải cập nhật thủ công, dễ quên; bảng dài khi lên hàng trăm file

3\. Tag + TAGS.md	Mở TAGS.md, xem mục #token	Phân loại chéo nhiều môn	Tag dễ không nhất quán (#token / #tokens); tốn công gắn

4\. Tên file theo quy tắc	Lọc \*ai101\*	Không cần công cụ	Chỉ lọc được theo môn và ngày, không tìm theo nội dung

