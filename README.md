# Bambu Studio account switcher for macOS

A shareable, local-only utility for switching among separate Bambu Studio profiles on one Mac. It creates a guided **Bambu Setup.app** and searchable profile launchers.

The release does not include any account, cookie, password, profile, or session data. Each person creates and signs into their own local profiles on their own Mac.

## Install

1. Download [`bambu-account-switcher-1.2-shareable.zip`](releases/bambu-account-switcher-1.2-shareable.zip).
2. Verify the checksum against [`SHA256SUMS`](releases/SHA256SUMS).
3. Unzip without changing the package contents.
4. Confirm Bambu Studio is installed at `/Applications/BambuStudio.app`.
5. Open **Bambu Setup.app**. If macOS asks, use Finder's right-click **Open** once; this is an ad-hoc-signed, non-notarized utility.
6. Name the current account, add local profiles, and use the generated launchers in `~/Applications`.

Each new profile starts logged out. Sign in once in Bambu Studio; later switches restore only that Mac's saved local session.

## Safety and limits

- The switcher requests a normal Bambu Studio quit and aborts if it cannot close within 30 seconds.
- It stages profile and session changes and restores the previous link if a replacement fails.
- Profile names are restricted to simple names and cannot form paths.
- Do not copy profile folders or hidden session backups between people.
- The app is ad-hoc signed, not Developer ID signed or notarized. Do not bypass macOS security settings or run shell commands from untrusted copies.

## Requirements

- macOS
- Bambu Studio installed in `/Applications` (or set `BAMBU_STUDIO_APP` to another `.app` path)

To verify the extracted app before opening it:

```sh
codesign --verify --deep --strict --verbose "Bambu Setup.app"
```

