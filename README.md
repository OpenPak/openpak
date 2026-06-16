# openpak

Submission intake for the **Openpak** Flatpak app store — *judge the work, not the workflow.*

This is where app manifests live and where new apps are submitted, mirroring
Flathub's `flathub/flathub` model.

## How submission works

1. **Fork** this repo.
2. **Branch** named after your app id (e.g. `io.github.you.App`).
3. Add your manifest at the **repo root** as `<app-id>.{yaml,yml,json}` (plus any
   local sources it references).
4. Open a **pull request against the `new-pr` branch**.
5. CI **test-builds** your PR (the review gate) — it must build clean, pass
   `flatpak-builder-lint`, and produces an installable test bundle artifact.
6. A reviewer checks it against the [submission policy](SUBMISSION.md).
7. On **merge into `new-pr`**, the onboarding bot creates your app's repo
   `OpenPak/<app-id>`, which **builds, signs, and publishes** to
   `https://dl.openpak.org/repo/`. Future updates are PRs/pushes to that repo.

Install any published app:

```sh
flatpak remote-add --if-not-exists openpak https://dl.openpak.org/repo/openpak.flatpakrepo
flatpak install openpak <app-id>
```

## Policy in one line

**AI-assisted and AI-generated contributions are welcome.** We gate on quality,
maintenance, distinctness, clean licensing, and respect for users — never on how
the work was made. See [SUBMISSION.md](SUBMISSION.md).
