# Air Mouse

Use your Android phone as a mouse, touchpad, media remote, presentation remote, or PPSSPP controller for a Windows PC.

This repository contains the latest Android APK and Windows receiver files. Download the complete package from [the latest release](https://github.com/hello-anil/air-mouse-releases/releases/latest), or download the individual files below.

| Download | Purpose |
| --- | --- |
| [Air Mouse APK](AirMouse-SpiderIcon-20261009.apk) | Android app with the spider-and-cursor launcher icon |
| [Windows receiver EXE](windows-receiver/AirMouseReceiver.exe) | Standalone receiver; Python is bundled |
| [PPSSPP control profile](windows-receiver/profiles/ppsspp-controls.ini) | Matching controller bindings |
| [SHA-256 checksums](SHA256SUMS.txt) | Verify downloaded files |

## Install and connect

Requirements: Android 8 or newer with Bluetooth; Windows 10 or 11, 64-bit, with Bluetooth Classic support.

1. Install `AirMouse-SpiderIcon-20261009.apk` on your phone. Enable installation from the browser or file manager when Android asks. To update through ADB, run `adb install --no-incremental -r AirMouse-SpiderIcon-20261009.apk`.
2. Extract `AirMouseReceiver-Windows-20261009.zip` from the release and run `AirMouseReceiver.exe`. The receiver appears in the Windows notification area.
3. Pair your phone and PC in their Bluetooth settings.
4. In Air Mouse, allow the requested Bluetooth or Nearby devices permission, select your paired PC, and connect.
5. Open the control screen and calibrate motion control, or select touchpad mode. Use the receiver's tray menu for settings, pause, and exit.

The receiver ZIP includes the EXE, PPSSPP profile, and third-party notices. The EXE also works when downloaded individually.

## PPSSPP

Open PPSSPP on Windows and use the phone's PSP keypad. Set these bindings in **Settings > Controls > Control mapping**:

| Control | Windows key |
| --- | --- |
| D-pad | Arrow keys |
| Cross / Circle / Square / Triangle | Z / X / A / S |
| L / R | Q / W |
| Start / Select | Enter / Backspace |
| Home / PS | Escape |
| Analog up / left / down / right | I / J / K / L |

Remove Backspace from **Rewind**. The provided `profiles/ppsspp-controls.ini` contains the matching mappings. Close PPSSPP and back up its existing `controls.ini` before replacing it. Check game-specific overrides too. Run PPSSPP and the receiver at the same Windows privilege level.

## PC audio

The APK's **Speaker** screen receives Windows audio over Wi-Fi or USB. Start its receiver, then open **Network speaker...** from the Windows tray menu and start the matching transport. Wi-Fi needs both devices on the same network. USB needs Android USB debugging and ADB available on the PC.

Bluetooth mouse and controller input work with this APK. Bluetooth speaker audio in the Windows receiver requires the separate Air Mouse Speaker companion, which is not included in this download.

## Release details

- Published package: October 9, 2026.
- Android app: version `1.0.0`, package `com.airmouse.app`; latest installed APK with updated launcher artwork.
- Windows receiver: latest existing build from October 3, 2026, unchanged for this package.
- Windows receiver source checks: 197 tests passed; Ruff checks passed.
- Android verification: installed through ADB, launched successfully, and launcher artwork checked on the phone.
- Third-party license notices are included in `windows-receiver/THIRD_PARTY_NOTICES/`.

Check a downloaded file in PowerShell with `Get-FileHash -Algorithm SHA256 <file>` and compare it with `SHA256SUMS.txt`.
