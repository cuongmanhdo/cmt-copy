# CMT Copy

Công cụ sao chép / di chuyển tệp dung lượng lớn cho Windows 10/11 (64-bit), phát triển bởi
**BKRECOVER — Trung tâm Khôi phục Dữ liệu Bách Khoa** (Công ty Cổ phần Giải pháp Máy tính Việt Nam).
Website: https://recoverdata.com.vn

*A file copy / move tool for large jobs on Windows 10/11 (64-bit), by BKRECOVER — Vietnam Computer Solutions JSC.
English summary below.*

> Repo này chỉ chứa **bộ cài và tài liệu**. CMT Copy là phần mềm miễn phí cho mục đích nghiên cứu và học tập,
> phi thương mại, **không phải phần mềm mã nguồn mở**; mã nguồn không được công bố. Xem [LICENSE.txt](LICENSE.txt).

## Tải về

Vào mục **[Releases](../../releases)**, bản mới nhất **2.3.2**:

| Tệp | Dùng cho |
|---|---|
| `CMTCopy-2.3.2-x64.msi` | Bộ cài: Start Menu, Desktop, menu chuột phải "Dán bằng CMT Copy" trong Explorer. Nâng cấp được từ các bản 1.x / 2.x. |
| `CMTCopy-2.3.2-portable.zip` | Bản chạy ngay: `CMT Copy.exe` cùng điều khoản và thông báo bên thứ ba. |
| `SHA256SUMS.txt` | Mã SHA-256 để kiểm tra tệp tải về không bị thay đổi. |

Không cần cài .NET hay runtime nào khác. Cài im lặng: `msiexec /i CMTCopy-2.3.2-x64.msi /qn`.

Kiểm tra tệp tải về (PowerShell):

```powershell
Get-FileHash .\CMTCopy-2.3.2-x64.msi -Algorithm SHA256
```

## Tính năng chính (2.3.2)

- Dán bằng CMT Copy từ Explorer (Ctrl+C / Ctrl+X rồi chuột phải thư mục đích), kéo thả, nhiều tác vụ song song hoặc
  xếp hàng chờ nhau.
- Đường dẫn dài trên 260 ký tự, tên tiếng Việt; khi gặp tệp trùng: hỏi / ghi đè / bỏ qua / giữ cả hai.
- **Ghi an toàn**: tắt ngang hoặc mất điện không để lại tệp hỏng dưới tên thật.
- **Lưu tiến trình**: đóng phần mềm, mất điện hay khởi động lại máy vẫn chạy tiếp được, bỏ qua tệp đã chép.
- Mất kết nối ổ mạng / NAS: tự chờ và chép tiếp. Ổ đích đầy: tạm dừng chờ, hoặc **chạy tiếp sang đích khác** (bỏ qua
  tệp đã có ở đích cũ).
- Danh sách lỗi có lý do, thử lại tệp lỗi; nhật ký ghi cả thao tác của người dùng.

## Lưu ý về Windows Defender / SmartScreen

CMT Copy **chưa được ký số**. Khi chạy lần đầu, Windows SmartScreen có thể cảnh báo ("Windows protected your PC") —
chọn *More info → Run anyway* nếu bạn tải từ trang Releases này và mã SHA-256 khớp.

Khi chép hàng triệu tệp, Windows Defender có thể **nhận nhầm** CMT Copy là mã độc theo hành vi
(đã gặp: `Behavior:Win32/Filecoder.DD`) và dừng phần mềm giữa chừng. Dữ liệu không bị hỏng (ghi an toàn), tác vụ chạy
tiếp được khi mở lại. Để tránh, thêm loại trừ: *Windows Security → Virus & threat protection → Manage settings →
Exclusions → Add an exclusion → Process* → `CMT Copy.exe`.

**Đã báo nhận nhầm cho Microsoft** ngày 10/10/2026 qua Microsoft Security Intelligence, mã hồ sơ
`c335abff-816f-49a6-8f73-6cc4e9cb6035` (tệp `CMT Copy.exe` 2.3.2, SHA-256
`2229d17b1fec13759f044e15be54abfffed6b03bb3451dac67bd097efdfa528e`). Trạng thái: **đang chờ Microsoft phân tích** —
mục này sẽ được cập nhật khi có kết quả.

## Quyền riêng tư

CMT Copy không thu thập và không gửi ra ngoài bất kỳ dữ liệu nào. Nhật ký chỉ lưu trên máy:
`%LOCALAPPDATA%\CMT Copy\cmtcopy.log`.

## Bản quyền và tuân thủ

- **CMT Copy** © 2026 Công ty Cổ phần Giải pháp Máy tính Việt Nam — BKRECOVER. Bảo lưu mọi quyền. Được cung cấp miễn
  phí cho mục đích nghiên cứu và học tập, phi thương mại, theo [LICENSE.txt](LICENSE.txt) (cũng là điều khoản người
  dùng đồng ý trong bộ cài). Không được bán, sửa đổi, dịch ngược hay phân phối bản đã chỉnh sửa khi chưa có chấp
  thuận bằng văn bản.
- **Thành phần của bên thứ ba**: tệp chương trình liên kết tĩnh libstdc++ / libgcc (GPL-3.0 kèm GCC Runtime Library
  Exception 3.1), mingw-w64 runtime (ZPL-2.1) và winpthreads (MIT); bộ cài dùng giao diện WixUI của WiX Toolset
  (MS-RL). Các thành phần này giữ nguyên giấy phép của chúng; toàn văn giấy phép và thông báo bản quyền có trong
  [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) và được kèm trong bản portable. Chúng tôi tuân thủ đầy đủ các điều
  kiện của những giấy phép đó.
- Repo không chứa dữ liệu của khách hàng hay bất kỳ dữ liệu cá nhân nào.
- Người dùng tự chịu trách nhiệm chỉ sao chép dữ liệu mà mình có quyền hợp pháp (điều 6 của điều khoản).

Liên hệ về bản quyền / báo vi phạm: https://recoverdata.com.vn

---

## English

**CMT Copy** copies and moves large amounts of files on Windows 10/11 x64: paste from Explorer, parallel or queued
jobs, long paths, duplicate handling, crash-safe writes, jobs saved across restarts, waits for lost network drives and
full destinations, and can continue a job at another destination. No runtime needed.

- **Download**: see [Releases](../../releases) — `CMTCopy-2.3.2-x64.msi` (installer) or `CMTCopy-2.3.2-portable.zip`,
  with `SHA256SUMS.txt`.
- **Not code-signed yet**: SmartScreen may warn on first run. Windows Defender may falsely flag it
  (`Behavior:Win32/Filecoder.DD`) during very large jobs; add a process exclusion for `CMT Copy.exe` if that happens.
  Reported to Microsoft as a false positive on 2026-10-10, submission ID `c335abff-816f-49a6-8f73-6cc4e9cb6035`
  (CMT Copy.exe 2.3.2, SHA-256 `2229d17b1fec13759f044e15be54abfffed6b03bb3451dac67bd097efdfa528e`) — awaiting
  Microsoft's analysis.
- **Privacy**: nothing is collected or sent anywhere; the log stays at `%LOCALAPPDATA%\CMT Copy\cmtcopy.log`.
- **License**: proprietary freeware for research and study, non-commercial — © 2026 Vietnam Computer Solutions JSC —
  BKRECOVER, all rights reserved. See [LICENSE.txt](LICENSE.txt). This repository holds binaries and documentation
  only; the source code is not published.
- **Third-party components** (libstdc++/libgcc under GPL-3.0 with the GCC Runtime Library Exception, mingw-w64 runtime
  under ZPL-2.1, winpthreads under MIT, WiX WixUI under MS-RL) keep their own licenses; full texts and copyright
  notices are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and inside the portable zip.
