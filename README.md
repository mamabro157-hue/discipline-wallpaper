# 26 WEEKS OF DISCIPLINE — Android Live Wallpaper

Real `WallpaperService` live wallpaper. Everything is computed from the device clock:

- Progress ring + percentage (16 Nov 2026 → 16 May 2027, 182 days / 26 weeks)
- Completed / remaining weeks (week 1 completes on 23 Nov 2026; auto-advances weekly)
- Live Days / Hrs / Min / Sec countdown to 16 May 2027 (ticks every second while visible)
- Live clock with seconds and full date at the top (set USE_24H in the service for 24-hour time)
- 26-week grid: green = completed, blue pulsing outline = current week, grey = upcoming
- Pure black AMOLED, content kept below the system clock and above the dock

The wallpaper only redraws while visible, so battery impact is minimal.

## Build without a computer (phone only)

1. Create a GitHub repo and upload the contents of this folder (keep the `.github` folder).
2. Open the **Actions** tab → **Build APK** → run it (it also runs on every push).
3. Download the `discipline-wallpaper-apk` artifact, unzip, install `app-debug.apk`.
4. Open the app "26 Weeks of Discipline" → tap **Set wallpaper**.

## Build with Android Studio

Open this folder, let Gradle sync, Run on a device. Requires Android 8.0+ (API 26).

## Customise

All dates and the week count are constants at the top of `DisciplineEngine` in
`DisciplineWallpaperService.kt`. Vertical positions are fractions of screen height (e.g. `H * 0.455f`).
