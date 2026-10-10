**English** | [Tiếng Việt](README.vi.md)

# CMT Copy

A file copy / move tool for large jobs on Windows 10/11 (64-bit), developed by
**BKRECOVER — Bach Khoa Data Recovery Center** (Vietnam Computer Solutions JSC).
Website: https://recoverdata.com.vn

> This repository holds **installers and documentation only**. CMT Copy is free software for research and study,
> non-commercial, and **not open source**; the source code is not published. See [LICENSE.txt](LICENSE.txt).

## Download

Go to **[Releases](../../releases)** — latest version **2.3.2**:

| File | Use |
|---|---|
| `CMTCopy-2.3.2-x64.msi` | Installer: Start Menu, Desktop, and a "Paste with CMT Copy" item in Explorer's right-click menu. Upgrades 1.x / 2.x. |
| `CMTCopy-2.3.2-portable.zip` | Runs without installing: `CMT Copy.exe` with the terms of use and third-party notices. |
| `SHA256SUMS.txt` | SHA-256 checksums to confirm the downloads were not altered. |

No .NET or other runtime needed. Silent install: `msiexec /i CMTCopy-2.3.2-x64.msi /qn`.

Check a download (PowerShell):

```powershell
Get-FileHash .\CMTCopy-2.3.2-x64.msi -Algorithm SHA256
```

## Main features (2.3.2)

- Paste with CMT Copy from Explorer (Ctrl+C / Ctrl+X, then right-click the destination folder), drag and drop,
  several jobs in parallel or queued one after another.
- Paths longer than 260 characters, Unicode names; duplicate files: ask / overwrite / skip / keep both.
- **Safe write**: a crash or power cut never leaves a broken file under its real name.
- **Saved jobs**: after closing the app, a power cut or a restart, jobs continue and skip files already copied.
- Lost network drive / NAS: waits and resumes by itself. Full destination: pauses and waits, or **continue at another
  destination** (files already at the old one are skipped).
- Error list with reasons and "retry failed files"; the log also records user actions.
- English and Vietnamese interface (Options → Language).

## Windows Defender / SmartScreen

CMT Copy is **not code-signed yet**. On first run Windows SmartScreen may warn ("Windows protected your PC") — choose
*More info → Run anyway* if you downloaded it from this Releases page and the SHA-256 matches.

When copying millions of files, Windows Defender may **falsely flag** CMT Copy by its behavior
(seen: `Behavior:Win32/Filecoder.DD`) and stop it mid-job. No data is damaged (safe write), and the job continues when
the app is opened again. To avoid it, add an exclusion: *Windows Security → Virus & threat protection → Manage
settings → Exclusions → Add an exclusion → Process* → `CMT Copy.exe`.

**Reported to Microsoft as a false positive** on 2026-10-10 through Microsoft Security Intelligence, submission ID
`c335abff-816f-49a6-8f73-6cc4e9cb6035` (`CMT Copy.exe` 2.3.2, SHA-256
`2229d17b1fec13759f044e15be54abfffed6b03bb3451dac67bd097efdfa528e`). Status: **awaiting Microsoft's analysis** — this
section will be updated with the result.

## Privacy

CMT Copy collects nothing and sends nothing anywhere. Its log stays on your computer:
`%LOCALAPPDATA%\CMT Copy\cmtcopy.log`.

## Copyright and compliance

- **CMT Copy** © 2026 Vietnam Computer Solutions JSC — BKRECOVER. All rights reserved. Provided free of charge for
  research and study, non-commercial, under [LICENSE.txt](LICENSE.txt) (the same terms users accept in the
  installer). Selling, modifying, reverse engineering or distributing modified copies requires written permission.
- **Third-party components**: the program statically links libstdc++ / libgcc (GPL-3.0 with the GCC Runtime Library
  Exception 3.1), the mingw-w64 runtime (ZPL-2.1) and winpthreads (MIT); the installer uses the WixUI dialogs of the
  WiX Toolset (MS-RL). These components keep their own licenses; the full license texts and copyright notices are in
  [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) and inside the portable zip. We comply with all conditions of
  those licenses.
- This repository contains no customer data and no personal data.
- Users are responsible for copying only data they are legally entitled to (section 6 of the terms).

Copyright questions / infringement reports: https://recoverdata.com.vn
