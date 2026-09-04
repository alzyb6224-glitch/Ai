# NexCode AI V11

A developer-first autonomous AI workspace for Android.

## What V7 can do

**Understand → Plan → Search project → Web/Deep Research → Impact analysis → Implement → Review → Test → Repair → Retest → Deliver**

The app provides one intelligent chat and a project workspace for files, code intelligence, terminal/sandbox verification, Git, visual debugging, research, quality and memory.

## Backend

1. Copy `backend/.env.example` to `backend/.env`.
2. Put the server-side AI key in `OPENAI_API_KEY`.
3. Keep `EXECUTION_MODE=safe_static` until Docker isolation is configured and tested.
4. Run with Docker Compose or Uvicorn.

## Android

The Android platform is generated with Flutter tooling. Use:

```bash
cd app
flutter pub get
flutter run --dart-define=NEXCODE_API_URL=https://YOUR-DOMAIN/api
```

For Play Store distribution use an AAB:

```bash
flutter build appbundle --release --dart-define=NEXCODE_API_URL=https://YOUR-DOMAIN/api
```

The GitHub Actions workflow builds both APK and AAB.

## Verification performed for this package
- Python syntax compilation across the backend.
- V6 regression suite: **6/6 passed**.
- V7 benchmark: **120/120 fixture checks passed (100%)**.
- Safety checks cover path traversal, protected files, command allowlisting, import relationships and impact propagation.
- ZIP integrity checked after packaging.

Flutter/Dart SDK is not installed in the current build environment, so an Android APK/AAB was not claimed as locally built or device-tested.

## Important production note
V6 contains production-oriented building blocks, not a claim that all external infrastructure is already provisioned. Real GitHub PRs, web research and model calls require their server-side credentials/network access.

See `docs/V7_STATUS.md`, `docs/AUTONOMOUS_DEVELOPER.md`, `docs/SECURITY.md`, and `docs/PRODUCTION_BUSINESS.md`.


## V9
V9 foundation (historical) adds Computer Agent, MCP, Memory 2.0, Workspace 2.0, Deep Research 2.0, Data Analysis, Voice Developer, Background Agents, Collaboration, Multimodal intelligence and Observability. See `docs/V9_STATUS.md`.


## V9 engineering foundation
V9 also adds a production-oriented Model Router, browser/computer execution boundaries, MCP registry (stdio/HTTP), multi-agent research orchestration, Codebase Graph V3, bounded autonomous verify/repair loops, a real SWE harness, enterprise RBAC/audit/redaction, IDE/artifact primitives, realtime collaboration protocol, memory learning loop, mobile/voice adapters, background jobs, code review, dependency analysis, security audit, and approval-gated deployment.

The V9 benchmark is a contract-level benchmark; the SWE harness can execute real test commands against a prepared worktree. Live provider/browser/deployment integrations still require their external credentials/runtime dependencies.


## V11 Authentication

Email/password plus configurable OAuth for Google, Apple, GitHub, Microsoft and Discord. See `docs/AUTH_V11.md`. OAuth providers are enabled only when their credentials are configured; secrets are never hard-coded into the app.


## V11: Central Agent Core
NexCode now exposes `/api/v11/*` for central orchestration, agent-team delegation, long-running tasks, observability, feedback learning, release gates and V11 benchmarking. Project chat uses the V11 Agent Core whenever a project is active in the Flutter client.

## Android without Android Studio
Use `.github/workflows/android.yml` from a GitHub repository. The workflow generates the Flutter Android platform, configures the NexCode OAuth deep link, and produces APK/AAB artifacts. See `docs/ANDROID_FROM_PHONE.md`.
