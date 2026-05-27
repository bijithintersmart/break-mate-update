# BreakMate Update Repository

> [!IMPORTANT]
> This is a **distribution and update management repository** for BreakMate. It functions as the primary update server using the Sparkle framework, providing an alternative to traditional CDN-based hosting.

## 🚀 Purpose

This repository is the source of truth for BreakMate's update lifecycle. It hosts the version metadata (Appcast) and binary installers required for the application's auto-update mechanism.

### Key Artifacts:
- **`appcast.xml`**: The Sparkle feed defining version availability and download signatures.
- **`release_dmg/`**: Contains the compiled and signed macOS installer packages.
- **`release_notes.md`**: Detailed changelogs and installation guidance for the latest versions.

## 🛠 Infrastructure Setup

Unlike a standard source code repository, this environment is optimized for binary distribution:
- **CDN-less Updates**: Leveraging GitHub's raw content delivery for high-speed metadata access.
- **Sparkle Integration**: Optimized for the macOS `Sparkle` framework to ensure secure, signed updates.
- **Issue Tracking**: This repository is the designated location for reporting deployment-related bugs or update failures.

## 📦 How Updates Work

The BreakMate application is configured to monitor the following feed URL:
`https://raw.githubusercontent.com/bijithintersmart/break-mate-update/main/appcast.xml`

When a new item is added to the XML with a higher version number, Sparkle automatically triggers the update dialog in the client app, pulls the `.dmg` from this repo's `release_dmg/` folder, and manages the installation.

## 🐞 Raising Issues

If you encounter issues during the update process or installation, please **[open an issue here](https://github.com/bijithintersmart/break-mate-update/issues)**. 

Areas of focus include:
- Auto-update failures or "Update Not Found" errors.
- macOS security/permission blocks.
- Corrupted installer downloads.

---
*Developed and maintained by Bijith P N.*
