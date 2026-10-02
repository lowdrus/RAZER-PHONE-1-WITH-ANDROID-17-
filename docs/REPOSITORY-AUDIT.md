# Repository audit / reproducible MOD plan

Audit date: 2026-10-02

## Current repository state
At audit time the repository contained only `README.md`. This is not yet sufficient for another Razer Phone 1 owner to reproduce the MOD.

## What this repository should contain

### 1. Documentation (commit to Git)
- `docs/00-prerequisites.md` — supported model/codename, warnings, cable requirements, Windows/Linux prerequisites.
- `docs/01-audit-stock-device.md` — read-only inventory before modification.
- `docs/02-backup-and-recovery.md` — backup strategy and return-to-stock procedure.
- `docs/03-bootloader.md` — OEM unlocking / bootloader steps and explicit wipe warnings.
- `docs/04-android17-build.md` — exact source manifests, branches, patches and build commands.
- `docs/05-install.md` — exact flashing/install sequence.
- `docs/06-razer-experience.md` — restoration of Razer visual experience without redistributing restricted proprietary files.
- `docs/07-gaming-tuning.md` — tested performance/thermal/display settings.
- `docs/08-linux-ai.md` — ARM64 strategy for Linux-AI OS components.
- `docs/09-dex-case.md` — HDMI/hub/power/cooling/external power-button project.
- `docs/10-troubleshooting.md` — known failures and recovery.
- `docs/COMPATIBILITY.md` — camera, LTE/IMS, Wi-Fi, BT, NFC, fingerprint, audio, 120 Hz, USB, HDMI, sensors, encryption, SafetyNet/Play Integrity status.
- `docs/CHANGELOG.md`.

### 2. Device/build source (commit to Git when developed/licensed)
- `device/razer/cheryl/` — Android device tree or reproducible patches/fork references.
- `kernel/` — source/patches/config used for the final kernel, respecting upstream licensing.
- `manifests/` — pinned repo/local manifests with exact commit/branch references.
- `patches/` — Android 17/cheryl compatibility patches.
- `sepolicy/` — project SELinux policy changes if separated from device tree.
- `overlays/` — resource overlays.
- `scripts/` — audit/build/install/verify/recovery automation.
- `config/` — reproducible configuration files.

### 3. Razer Experience Layer
Commit only project-owned scripts/config/metadata and redistributable assets. Suggested layout:
- `razer-experience/manifest/` — list, package names, hashes and origin of original Razer components.
- `razer-experience/extract/` — scripts that extract permitted assets from the user's own device/factory package.
- `razer-experience/install/` — integration/install scripts.
- `razer-experience/compat/` — Android 17 compatibility shims/overlays created by this project.

Do NOT blindly commit proprietary Razer APKs, factory images, firmware, vendor blobs, boot animations, wallpapers or other copyrighted/restricted payloads. Prefer extraction scripts, hashes and official download links. The Razer factory-image page explicitly restricts redistribution/modification of device software.

### 4. Proprietary vendor blobs
For a ROM build, maintain a `proprietary-files.txt`-style manifest and extraction tooling rather than committing blobs unless redistribution rights are confirmed. Modern Lineage device workflows use a proprietary-files list plus extraction utilities.

### 5. Release artifacts
Large generated images should normally be GitHub Release assets, not ordinary Git history:
- ROM flashable package
- boot/recovery/vendor_boot images when applicable
- checksums (`SHA256SUMS`)
- signed release manifest
- installation notes
- source commit/build ID used

Never publish a dump containing personal data, unique device credentials/keys, IMEI, serial-derived secrets, DRM/Widevine keys, persist/EFS/modem calibration or account data.

### 6. CI/reproducibility
Recommended future files:
- `.github/workflows/lint.yml`
- `.github/workflows/docs.yml`
- `.github/workflows/build.yml` only after the build is reproducible and runner/storage requirements are understood.
- `.gitignore`
- `LICENSE` for project-owned code
- `CONTRIBUTING.md`
- `SECURITY.md`
- `THIRD_PARTY.md` with upstream projects/licenses/links.

## Upstream sources identified
- Official Razer Phone Developer Portal: factory images and kernel/Wi-Fi source are still published for Razer Phone 1.
- Official Razer Phone 1 global factory image Android 9 MR2: build `P-MR2-RC001-RZR-N.7083`, official SHA-256 `7F885F2A6ED297A98147CEB414C09BCC911B9E42561BC91FCBBDEB68086AAB7D`.
- Razer also publishes older 8.1/7.1.1 factory images and carrier-specific CKH images.
- LineageOS maintains `LineageOS/android_device_razer_cheryl`; during this audit its default branch was `lineage-22.2` and repository activity extended into 2026. This is an important upstream reference, not proof by itself of Android 17 support.

## Current local tooling evidence
Android Platform Tools 37.0.1 are available both globally and under the project workspace. Recorded local project-copy hashes:
- adb.exe: `B4A6B455702684652CCCF7B46258B29E653538904359A58FD4931CF3EF286B3F`
- fastboot.exe: `B2D9CBFF4CE9AE7EB448CFC831BAFC867935F50F5BE38F8F81057FD7EB3B8D86`
- AdbWinApi.dll: `C1D653030B4BDE65D3E07E4D0B0979E17BE56DF1436CDD15528630F27808050D`
- AdbWinUsbApi.dll: `0710E894D9B40F71A670C13C694079D564C92C1279DA382CFE4850983AAEBE1B`

## Immediate gating tasks
1. Authorize ADB RSA without touch loss/destructive changes.
2. Capture complete stock-device inventory.
3. Determine exact installed stock build/region and bootloader state.
4. Preserve a recovery path before unlocking/flashing.
5. Research/build Android 17 against the existing cheryl ecosystem.
6. Only after boot and hardware validation, package a reproducible public MOD.
