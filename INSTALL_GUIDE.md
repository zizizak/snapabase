# Snapabase — Hướng Dẫn Cài Đặt & Sử Dụng (Windows/macOS)

Snapabase là công cụ quản lý Backup & Restore cục bộ cho dự án Supabase, giúp bạn bảo vệ dữ liệu và mã nguồn một cách an toàn nhất.

> [!NOTE]
> Người dùng cuối (End-user) **không cần cài đặt Node.js** để chạy Snapabase. Bạn chỉ cần cài đặt các công cụ bổ trợ (CLI) được liệt kê bên dưới.

---

## 1. Yêu cầu hệ thống (Prerequisites)

Snapabase sử dụng các công cụ dòng lệnh (CLI) chính thức của PostgreSQL và Supabase để thực hiện các tác vụ. Bạn cần cài đặt chúng trước khi sử dụng ứng dụng.

### Cho Windows:
1.  **PostgreSQL (psql & pg_dump):**
    *   Tải bản cài đặt: [PostgreSQL Windows Installer](https://www.postgresql.org/download/windows/)
    *   **Mẹo:** Trong quá trình cài đặt, hãy ghi nhớ đường dẫn thư mục `bin` (ví dụ: `C:\Program Files\PostgreSQL\16\bin`). Bạn sẽ cần trỏ đường dẫn này trong phần cài đặt ứng dụng.
2.  **Supabase CLI:**
    *   **Cách A (Dùng Scoop):** `scoop install supabase`
    *   **Cách B (Dùng Chocolatey):** `choco install supabase-cli`
    *   **Cách C (Tải trực tiếp):** Tải file thực thi từ [Supabase CLI Releases](https://github.com/supabase/cli/releases).

3.  **Cài đặt Scoop (Khuyên dùng):**
    *   Mở PowerShell và chạy lệnh sau:
        ```powershell
        Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
        Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
        ```

### Cho macOS:
1.  **PostgreSQL:** `brew install postgresql`
2.  **Supabase CLI:** `brew install supabase/tap/supabase`

---

## 2. Cài đặt Snapabase

1.  **Tải ứng dụng:** Lấy bản cài đặt `.exe` (Windows) hoặc `.dmg` (macOS) mới nhất từ [trang phát hành chính thức](https://github.com/quocvinhdo/snapabase/releases).
2.  **Chạy bộ cài:**
    *   **Windows:** Chạy file `.exe` và làm theo hướng dẫn.
    *   **macOS:** Mở file `.dmg`, kéo biểu tượng Snapabase vào thư mục *Applications*.
3.  **Cấp quyền (macOS):** Nếu bạn thấy thông báo "App cannot be opened because it is from an unidentified developer", hãy vào `System Settings > Privacy & Security` và nhấn **"Open Anyway"**.

---

## 3. Cấu hình ban đầu

1.  **Mở Snapabase** và truy cập vào mục **Settings**.
2.  **Thiết lập đường dẫn CLI:** Nhấn **Select File** cho từng công cụ:
    *   `psql`: Thường nằm ở `C:\Program Files\PostgreSQL\...\bin\psql.exe`
    *   `pg_dump`: Thường nằm cùng thư mục `bin` với `psql`.
    *   `supabase`: Nếu cài qua Scoop, nó nằm ở `~/scoop/shims/supabase.exe`.
3.  **Lưu trữ (Storage):** Chọn một thư mục trên máy tính để lưu các bản backup SQL.
4.  **Kiểm tra:** Nhấn **Verify Tools** để đảm bảo mọi thứ đã sẵn sàng.

---

## 4. Kích hoạt bản quyền

Snapabase cung cấp giấy phép trọn đời để sử dụng các tính năng chuyên nghiệp.

1.  Mua mã kích hoạt tại [Lemon Squeezy](https://snapabase.lemonsqueezy.com/checkout).
2.  Trong ứng dụng, vào mục **Settings > License**.
3.  Dán mã của bạn và nhấn **Activate**.

---

## 5. Xử lý sự cố & FAQ

### Các lỗi thường gặp:
*   **"psql is not recognized":** Đảm bảo bạn đã chọn đúng đường dẫn đến file `psql.exe` trong tab Settings.
*   **Hết thời gian kết nối (Timeout):** Kiểm tra xem dự án Supabase của bạn có đang bị "Paused" (Tạm dừng) không. Nếu có, hãy Resume nó trên Dashboard của Supabase.
*   **Bị từ chối quyền (khi Restore):** Snapabase tự động xử lý các vấn đề về trigger/role, nhưng hãy đảm bảo User Database của bạn có đủ quyền (thường là user `postgres`).

### Câu hỏi thường gặp:
*   **Dữ liệu của tôi có an toàn không?** Có. Snapabase hoạt động theo cơ chế "Local-First". Thông tin đăng nhập và bản backup của bạn không bao giờ rời khỏi máy tính cá nhân.
*   **Tôi có cần Docker không?** Không. Snapabase sử dụng các tệp thực thi native để đạt hiệu suất và bảo mật tối đa.
*   **Tôi có thể restore vào database đang có dữ liệu không?** Chúng tôi khuyên bạn nên restore vào một dự án **mới/trống** để tránh xung đột dữ liệu.

---

## 6. Hỗ trợ
*   **Email:** quocvinhdo@gmail.com
*   **Website:** [snapabase.vercel.app](https://snapabase.vercel.app/)
*   **Github:** [Báo lỗi / Góp ý](https://github.com/quocvinhdo/snapabase/issues)
