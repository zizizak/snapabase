# Snapabase — Installation & Setup Guide (Windows/macOS)

Snapabase is a local management tool for Supabase projects, allowing you to back up and restore your database and source code with ease.

> [!NOTE]
> End-users **do not need to install Node.js** to run Snapabase. You only need to install the auxiliary tools (CLI) listed below.

---

## 1. System Prerequisites

Snapabase relies on official PostgreSQL and Supabase command-line tools (CLI) to perform its tasks. You must install these before using the application.

### For Windows:
1.  **PostgreSQL (psql & pg_dump):**
    *   Download: [PostgreSQL Windows Installer](https://www.postgresql.org/download/windows/)
    *   **Tip:** During installation, remember the `bin` folder path (e.g., `C:\Program Files\PostgreSQL\16\bin`). You will need this in the app settings.
2.  **Supabase CLI:**
    *   **Option A (Scoop):** `scoop install supabase`
    *   **Option B (Chocolatey):** `choco install supabase-cli`
    *   **Option C (Direct):** Download from [Supabase CLI Releases](https://github.com/supabase/cli/releases).

3.  **Installing Scoop (Recommended):**
    *   Open PowerShell and run:
        ```powershell
        Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
        Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
        ```

### For macOS:
1.  **PostgreSQL:** `brew install postgresql`
2.  **Supabase CLI:** `brew install supabase/tap/supabase`

---

## 2. Installing Snapabase

1.  **Download:** Get the latest `.exe` (Windows) or `.dmg` (macOS) from the [official releases](https://github.com/quocvinhdo/snapabase/releases).
2.  **Run Installer:**
    *   **Windows:** Run the `.exe` and follow the setup wizard.
    *   **macOS:** Open `.dmg`, drag Snapabase to *Applications*.
3.  **Permissions (macOS):** If you see "App cannot be opened because it is from an unidentified developer", go to `System Settings > Privacy & Security` and click **"Open Anyway"**.

---

## 3. Initial Configuration

1.  **Open Snapabase** and navigate to **Settings**.
2.  **Set CLI Paths:** Click **Select File** for each tool:
    *   `psql`: Usually in `C:\Program Files\PostgreSQL\...\bin\psql.exe`
    *   `pg_dump`: Usually in the same `bin` folder as `psql`.
    *   `supabase`: If installed via Scoop, it's in `~/scoop/shims/supabase.exe`.
3.  **Storage:** Choose a folder where your SQL backups will be saved.
4.  **Test:** Click **Verify Tools** to ensure everything is connected.

---

## 4. License Activation

Snapabase offers a lifetime license for professional features.

1.  Purchase your key at [Lemon Squeezy](https://snapabase.lemonsqueezy.com/checkout).
2.  In the app, go to **Settings > License**.
3.  Paste your key and click **Activate**.

---

## 5. Troubleshooting & FAQ

### Common Issues:
*   **"psql is not recognized":** Ensure you have selected the correct path to `psql.exe` in the Settings tab.
*   **Connection Timeout:** Check if your Supabase project is "Paused". If so, resume it in the Supabase Dashboard.
*   **Permission Denied (Restore):** Snapabase automatically handles trigger/role issues, but ensure your Database User has sufficient permissions (usually the `postgres` user).

### FAQ:
*   **Is my data safe?** Yes. Snapabase is "Local-First". Your database credentials and backups never leave your machine.
*   **Do I need Docker?** No. Snapabase uses native binaries for maximum performance and security.
*   **Can I restore to an existing database?** We recommend restoring to a **new/empty** project to avoid data conflicts.

---

## 6. Support
*   **Email:** quocvinhdo@gmail.com
*   **Website:** [snapabase.vercel.app](https://snapabase.vercel.app/)
*   **Github:** [Report an Issue](https://github.com/quocvinhdo/snapabase/issues)
