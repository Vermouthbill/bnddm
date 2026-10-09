BND DM Vault — iPhone PWA Beta 0.1
SIMULATED CONTENT ONLY

This is the first integrated iPhone test build. It does not connect to Weverse and should not be used with real Weverse DM content yet.

How to deploy:
1. Upload ALL files in this folder to the same HTTPS static site folder.
2. Open index.html through that HTTPS address in iPhone Safari.
3. Safari -> Share -> Add to Home Screen.
4. Open the new Home Screen icon and follow the first-run checklist.

Integrated features:
- Six member chat archives with a WeChat-like chronological view.
- Date calendar navigation and local full-text search.
- IndexedDB local storage.
- Fictional Korean demo messages with manually authored natural-chat Chinese translations.
- JSON backup/restore for messages and OCR review metadata.
- Local mock-video storage, frame extraction and keyframe scanning.
- Persistent OCR review queue and links back to the source video second.
- Reconstruction hints: probable duplicate, near-duplicate and suspicious time-gap flags.
- Beta diagnostics page for iPhone Safari capability testing.
- First-run testing guide.

Important limitations:
- Browser TextDetector is capability-detected and may be unavailable on iPhone Safari.
- No Korean OCR model is bundled yet.
- No online AI translation or translation API is called.
- Video blobs are NOT included in JSON backups; keep source videos separately.
- Browser storage must not be treated as the only backup.
- Use only self-made simulated chat videos until permission for real Weverse DM processing is confirmed.

No analytics are included. The app makes no content-processing network requests. Network access is only needed to load the static PWA files from the site hosting them.
