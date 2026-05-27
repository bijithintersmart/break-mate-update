## BreakMate v1.1.3 — Stability, Dev Isolation & Version Alignment

This update introduces critical fixes to resolve a startup crash and optimizes the developer experience by isolating telemetry in development environments.

### What's Changed

- **Startup Crash Fix:** Resolved a critical runtime exception (`Tried to use Provider with a subtype of Listenable/Stream`) by shifting the injection of `StatsService` inside `MultiProvider` to `ChangeNotifierProvider.value`. Subscribed widgets can now dynamically listen to background metrics calculations safely.
- **Sentry Dev Mode Isolation:** Bypassed Sentry telemetry initialization in debug/profile builds using the `kReleaseMode` check. This completely silences verbose connection warnings and native SDK exceptions when developing locally.
- **Sparkle Version Alignment:** Aligned all build metadata to version `1.1.3+28` to ensure that macOS users receive updates correctly without redundant update dialog prompts.

### Installation Note (macOS)

Since BreakMate is not notarized by Apple, macOS may show a security warning on first launch.

1. Double-click the `BreakMate-Installer.dmg` and drag BreakMate to your Applications folder.
2. Right-click (or Control-click) the BreakMate app and select Open.
3. If it still blocks, go to **System Settings > Privacy & Security** and click **Allow Anyway** next to BreakMate.
