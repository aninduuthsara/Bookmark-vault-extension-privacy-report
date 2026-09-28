# Privacy Policy for Bookmark Vault

**Effective Date:** September 2026  
**Developer:** Anindu Uthsara (AVORTX)  
**Contact:** aninduuthsara2008@gmail.com  

---

## 1. Core Philosophy: "Your Data, Your Custody"
*Bookmark Vault* is built from the ground up as a **local-first, zero-knowledge, and privacy-respecting** browser extension for Chromium and Firefox browsers. We believe that your digital footprint, saved bookmarks, and private workflows belong exclusively to you.

**We do not collect, track, store, transmit, or sell any personal data.** There are zero developer-owned intermediate databases, zero tracking analytics, and zero commercial telemetry scripts embedded in this software.

---

## 2. Information Collection and Storage
All data managed by Bookmark Vault is stored strictly within sandboxed local browser storage (`chrome.storage.local`) on your personal machine and, optionally, your personal Google Drive account.

- **Bookmarks & Quick URLs:** Stored locally on your device.
- **Incognito Vault (Zero-Knowledge):** Private URLs are encrypted on the client side using authenticated **AES-256-GCM** encryption. Cryptographic keys are derived in volatile memory via **PBKDF2** (100,000 SHA-256 rounds). Your Master PIN is never written to disk or transmitted across any network.
- **User Analytics & Tracking:** None. Bookmark Vault does not monitor the websites you visit or the links you click.

---

## 3. Google Drive Synchronization (`drive.file`)
When you explicitly connect your Google Account for cloud backups:

1. **Direct Communication:** Transmission occurs directly and securely between your browser and official Google Drive REST API endpoints via OAuth2 (`launchWebAuthFlow`).
2. **Restricted Scope:** The extension requests the minimum required permission: `https://www.googleapis.com/auth/drive.file`. This restricted scope strictly permits the extension to access only the files and folders it creates itself (`Bookmark Vault/`). It cannot view, read, or modify your personal Google Docs, photos, or other drive files.
3. **No Intermediary Servers:** No authentication tokens or data payloads ever route through any developer servers.

---

## 4. Permissions Justification
Bookmark Vault requests the minimum set of permissions necessary to deliver its core features:

| Permission | Purpose & Justification |
| :--- | :--- |
| `storage` & `unlimitedStorage` | Required to store encrypted vaults, color categories, and cached favicons locally offline. |
| `identity` | Required to authenticate with the user's personal Google Drive via OAuth2. |
| `bookmarks` | Required to allow the user to import their existing browser bookmarks into the vault. |
| `tabs` & `activeTab` | Required to capture the current active webpage's URL, title, and favicon when saving a bookmark or using "Save All Open Tabs". |
| `alarms` | Required to schedule periodic background synchronization checks with Google Drive. |
| `contextMenus` | Allows users to right-click on any webpage to save links directly into their vaults. |
| `host_permissions` (`<all_urls>`) | Exclusively used by the headless **Link Doctor** to send non-intrusive HEAD requests to detect 404 broken links, and to fetch high-resolution website favicons. |

---

## 5. Third-Party Services
The extension does not embed any advertising networks or third-party trackers. Optional voluntary sponsorships are handled externally via **Buy Me a Coffee**, operating under their respective privacy policies.

---

## 6. Children's Privacy & Regulatory Compliance
Bookmark Vault does not knowingly collect or solicit personal information from anyone under the age of 13. Because no personal data is collected or stored on remote servers, the extension is compliant with GDPR, CCPA, and COPPA by architectural design.

---

## 7. Contact Information
If you have any questions or architectural suggestions regarding this Privacy Policy, please contact:

**Developer:** Anindu Uthsara (AVORTX)  
**Email:** aninduuthsara2008@gmail.com  
**GitHub:** [https://github.com/aninduuthsara](https://github.com/aninduuthsara)
