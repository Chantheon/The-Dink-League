Dink League V3 - Auto-Update PWA Build

This build includes an update-safe service worker:
- Versioned cache name changes whenever the app build changes.
- Old Dink League caches are removed during service-worker activation.
- Navigation/HTML requests use network-first with cache fallback, so published fixes are picked up automatically.
- Service-worker registration uses updateViaCache: "none" and explicitly checks for updates.
- New service workers activate immediately and take control without requiring Safari/PWA data to be cleared.
- The app reloads once after a new service worker takes control.

For future releases, change CACHE_VERSION in sw.js (for example, increment the date/build suffix). This is the safest way to guarantee a new service-worker build is installed.
