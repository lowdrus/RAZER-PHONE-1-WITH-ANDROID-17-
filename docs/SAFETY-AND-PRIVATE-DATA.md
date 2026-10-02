# Safety and private-device-data policy

Before publishing any artifact captured from a physical phone, verify it does not contain:

- IMEI/MEID or other cellular identifiers
- account tokens, passwords or cookies
- ADB private keys
- Wi-Fi credentials
- Bluetooth pairing secrets
- DRM/Widevine/device attestation keys
- persist/EFS/modem calibration data
- user photos/files/databases
- unique encryption keys
- serial-derived secrets

Stock backups belong outside Git. Public releases should be reproducible from documented upstream sources plus extraction/build scripts whenever licensing permits.

Bootloader unlocking and factory-image flashing can erase user data. The public guide must clearly mark destructive steps and provide recovery/rollback instructions before them.
