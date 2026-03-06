# VYB HR — Android App

All-in-one HR & Attendance system for small businesses.
Dark flat UI with green (#5FA26F) accent — VYB ecosystem.

## Features

- **Employee Sign In / Out** — tap a card to clock in or out; optional PIN per employee
- **Admin Panel** (PIN-protected) with 4 tabs:
  - **Employees** — add, remove, toggle active/inactive, change PINs
  - **Shifts & Leave** — set weekly shift schedules, assign/remove leave days, track leave balance
  - **Reports** — filter attendance by employee & date range, export to CSV (share via any app)
  - **Settings** — change company name, change admin PIN

## Tech Stack

- **Kotlin** + **Jetpack Compose** (Material3)
- **Navigation Compose** for screen routing
- **Gson** for JSON persistence (stored in app's internal storage)
- **ViewModel** + **StateFlow** for reactive UI

## Setup

1. Open the `VYB_HR_Android` folder in **Android Studio Hedgehog (2023.1.1)** or newer
2. Let Gradle sync automatically
3. Run on an emulator or device with Android 8.0+ (API 26+)

## Default PINs

| Role  | Default PIN |
|-------|-------------|
| Admin | `1234`      |
| Employee | `0000` (no PIN prompt) |

Change both immediately in Settings after first launch.

## Data Storage

All data is stored in the app's private internal storage (`/data/data/com.vyb.hr/files/HR_Data/`).
- `config.json` — employee list, PINs, shift schedules, leave balances
- `hr_data.json` — attendance sessions and leave assignments

## Notes

- The USB token check from the desktop version is not applicable on Android.
  Access is controlled instead by the admin PIN gate on the Settings screen.
- Photo support (employee avatars) shows initials by default.
  Custom photo support can be added by hooking into the Android photo picker.
- Excel export requires a library like Apache POI; the current export is CSV
  (shareable to any app including Google Sheets, Excel, etc.)
