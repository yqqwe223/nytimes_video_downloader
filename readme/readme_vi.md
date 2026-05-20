# 🗽 Công Cụ Phân Tích Video Từ NYTimes

> Công cụ trích xuất nội dung video từ The New York Times nhẹ, nhanh và đa năng (Phiên bản học tập & nghiên cứu)

[🌐 Dùng thử trực tuyến](https://twittervideodownloaderx.com/nytimes_downloader_vi) • [📝 Hướng dẫn sử dụng](#-hướng-dẫn-sử-dụng) • [❓ Câu hỏi thường gặp](#-câu-hỏi-thường-gặp)

---

## 📋 Giới thiệu dự án

Dự án này là công cụ phân tích video dựa trên nền web, hỗ trợ trích xuất an toàn siêu dữ liệu tài nguyên media từ các bài báo công khai trên website The New York Times, đồng thời cung cấp tùy chọn chuyển đổi và lưu trữ cục bộ dưới nhiều định dạng khác nhau. Không cần cài đặt phần mềm máy khách, không yêu cầu đăng ký tài khoản, sử dụng ngay lập tức qua trình duyệt.

> ⚠️ **Thông báo quan trọng**: Công cụ này chỉ dành cho mục đích học tập cá nhân, nghiên cứu kỹ thuật và sử dụng trong phạm vi hợp lý. Vui lòng tuân thủ [Điều khoản Dịch vụ của NYTimes](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), 《Luật Bản quyền Hoa Kỳ》và các quy định pháp luật liên quan, tôn trọng thành quả lao động của cơ quan báo chí và người sáng tạo, không sử dụng nội dung đã tải xuống cho mục đích thương mại hoặc xâm phạm quyền lợi của người khác. Công cụ này chỉ hỗ trợ nội dung video có thể truy cập công khai, không hỗ trợ truy cập nội dung có tường trả phí hoặc giới hạn đăng ký.

---

## ✨ Tính năng nổi bật

- 🔗 **Phân tích liên kết**: Hỗ trợ liên kết bài báo/trang video chuẩn của NYTimes, tự động nhận diện tài nguyên video công khai
- 📥 **Xuất nhiều định dạng**:
  - Luồng video công khai (hỗ trợ tùy chọn độ phân giải công khai mà nền tảng cung cấp)
  - Trích xuất âm thanh → Định dạng MP3 (tiện lợi cho việc nghe tin tức/podcast offline)
  - Đoạn video ngắn → Chuyển đổi thành ảnh động GIF (phù hợp làm tài liệu giảng dạy/tóm tắt nội dung)
- 🌍 **Giao diện đa ngôn ngữ**: Hỗ trợ tiếng Việt, tiếng Anh, tiếng Trung, tiếng Nhật và nhiều ngôn ngữ khác
- 📱 **Tương thích đa nền tảng**: Hoạt động tốt trên Chrome / Firefox / Safari / Edge, trải nghiệm mượt mà trên điện thoại và máy tính bảng
- 🔒 **Ưu tiên quyền riêng tư**: Không cần đăng nhập tài khoản NYTimes, không thu thập thông tin người dùng, quy trình phân tích hoàn toàn ẩn danh
- ⚡ **Xử lý tốc độ cao**: Hoàn thành phân tích trung bình trong vòng 5-10 giây, hỗ trợ yêu cầu song song

---

## 🚀 Bắt đầu nhanh

### Sử dụng trực tuyến (khuyến nghị)
1. Truy cập [https://twittervideodownloaderx.com/nytimes_downloader_vi](https://twittervideodownloaderx.com/nytimes_downloader_vi)
2. Sao chép liên kết trang video mục tiêu (ví dụ: `https://www.nytimes.com//01/01/world/example-video.html`)
3. Dán liên kết vào ô nhập liệu → Nhấp nút 「Phân tích」
4. Chọn độ phân giải và định dạng mong muốn → Lưu tệp theo hướng dẫn của trình duyệt

### Triển khai cục bộ (dành cho nhà phát triển)
```bash
# Clone repository
git clone https://github.com/your-repo/nytimes-video-parser.git

# Cài đặt dependencies
cd nytimes-video-parser && npm install

# Cấu hình biến môi trường (tùy chọn)
cp .env.example .env

# Khởi động server phát triển
npm run dev
```

> 💡 Lưu ý: Dự án sử dụng kiến trúc Node.js + Express. Vui lòng tham khảo tài liệu triển khai chi tiết tại `/docs/DEPLOY.md`

---

## 🛠 Công nghệ sử dụng

| Module | Công nghệ áp dụng |
|--------|------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Xử lý video | ffmpeg.wasm (chuyển đổi nhẹ trên frontend) |
| Proxy chuyển tiếp | Cloudflare Workers / Middleware tự xây dựng |
| Quốc tế hóa | vue-i18n + Gói ngôn ngữ JSON |

---

## 📚 Hướng dẫn sử dụng

### Quy trình thao tác cơ bản
```
1. Lấy liên kết video
   └─ Mở bài báo/trang video mục tiêu trên website NYTimes → Sao chép URL từ thanh địa chỉ trình duyệt

2. Gửi yêu cầu phân tích
   └─ Dán liên kết vào ô nhập của công cụ → Nhấp 「Bắt đầu phân tích」

3. Chọn cấu hình đầu ra
   ├─ 🎬 Tải video: Chọn độ phân giải khả dụng (chỉ áp dụng cho nội dung công khai)
   ├─ 🎵 Trích xuất âm thanh: Tạo tệp MP3 (phù hợp nghe tin tức/podcast offline)
   └─ 🎞 Tạo GIF: Cắt khoảng thời gian chỉ định để tạo ảnh động (khuyến nghị: ≤15 giây)

4. Lưu tệp
   └─ Tài nguyên mở trong tab mới → Nhấp chuột phải/menu → 「Lưu thành」
```

### Mẹo sử dụng trên điện thoại thông minh
- iOS Safari: Nút Chia sẻ → 「Lưu vào Tệp」
- Android Chrome: Nhấn giữ xem trước video → 「Tải video」
- Trường hợp video tự động phát: Nhấp `⋮` góc trên bên phải trình phát → Chọn 「Tải xuống」

---

## ❓ Câu hỏi thường gặp

**Hỏi: Tệp đã tải về được lưu ở đâu?**  
Đáp: Tệp sẽ được lưu vào thư mục tải xuống đã cài đặt trong trình duyệt. Bạn có thể kiểm tra hoặc thay đổi đường dẫn lưu trong phần cài đặt của trình duyệt.

**Hỏi: Có thể phân tích nội dung yêu cầu đăng ký trả phí hoặc dành riêng cho thành viên không?**  
Đáp: Không. Công cụ này chỉ hỗ trợ các video được cài đặt ở chế độ công khai và tôn trọng cài đặt quyền truy cập của nội dung gốc. Nội dung có tường trả phí, giới hạn đăng ký hoặc yêu cầu đăng nhập không nằm trong phạm vi hỗ trợ.

**Hỏi: Chất lượng hình ảnh/âm thanh sau khi chuyển đổi có bị giảm không?**  
Đáp: Tải video sẽ giữ nguyên bitrate gốc của độ phân giải đã chọn. Định dạng MP3 sử dụng mã hóa tiêu chuẩn 128kbps. Định dạng GIF sẽ tối ưu hóa tốc độ khung hình theo thời lượng phát để cân bằng giữa kích thước tệp và độ mượt.

**Hỏi: Lịch sử tải xuống hoặc bộ nhớ đệm có được lưu trữ không?**  
Đáp: Không. Tất cả tài nguyên đều được truyền trực tiếp đến thiết bị người dùng qua proxy tạm thời, máy chủ không lưu trữ bất kỳ nội dung yêu cầu hoặc tệp media nào.

**Hỏi: Nếu phân tích thất bại thì phải làm sao?**  
Đáp: Vui lòng kiểm tra: ① Liên kết trang video công khai có hợp lệ không ② Môi trường mạng có ổn định không ③ Thử đổi trình duyệt khác và thử lại. Nếu vấn đề vẫn tiếp diễn, vui lòng báo cáo qua Issue bất cứ lúc nào.

---

## ⚖️ Tuân thủ quy định và Tuyên bố miễn trừ

- Công cụ này **không xâm nhập hoặc bypass bất kỳ biện pháp bảo vệ kỹ thuật nào** của nền tảng, chỉ thu thập siêu dữ liệu thông qua giao diện công khai
- Người dùng vui lòng tự xác nhận hành vi sử dụng của mình có phù hợp với quy định pháp luật địa phương và điều khoản sử dụng của nền tảng hay không
- Các trường hợp sử dụng được khuyến nghị: Lưu trữ học tập cá nhân, nghiên cứu tin tức, tài liệu tham khảo sản xuất nội dung... trong phạm vi sử dụng hợp lý (Fair Use)
- Nếu phát hiện nội dung có nghi ngờ xâm phạm quyền lợi, hoặc có thắc mắc về bản quyền, vui lòng liên hệ kênh chính thức của [NYTimes qua liên kết này](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html)
- Công cụ này không có bất kỳ mối quan hệ liên kết hoặc ủy quyền nào với The New York Times Company, tất cả nhãn hiệu và bản quyền nội dung đều thuộc về chủ sở hữu quyền gốc

---

## 🤝 Hướng dẫn đóng góp

Chúng tôi hoan nghênh việc gửi Pull Request và báo cáo Issue! Trước khi đóng góp, vui lòng đọc kỹ các tài liệu sau:
- [Quy chuẩn mã nguồn](/CONTRIBUTING.md)
- [Hướng dẫn dịch đa ngôn ngữ](/locales/README.md)
- [Yêu cầu bảo mật và tuân thủ](/SECURITY.md)

---

## 📄 Giấy phép

Dự án này được phát hành dưới [Giấy phép MIT](/LICENSE), có thể sử dụng miễn phí cho mục đích học tập và nghiên cứu. Trường hợp sử dụng thương mại, vui lòng rà soát kỹ các yêu cầu tuân thủ pháp luật.

---

> 🌟 Nếu công cụ này hữu ích với bạn, vui lòng ✨nhấn Star để ủng hộ! Sự ủng hộ của mọi người chính là động lực lớn nhất để chúng tôi duy trì và phát triển dự án~

*Cập nhật lần cuối: Tháng 5 năm  | Phiên bản: v1.0.0*