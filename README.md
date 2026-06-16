# openpak

Submission intake for the **Openpak** Flatpak app store — *judge the work, not the workflow.*

This is where app manifests live and where new apps are submitted, mirroring
Flathub's `flathub/flathub` model.

## How submission works

1. **Fork** this repo.
2. **Branch** named after your app id (e.g. `io.github.you.App`).
3. Add your manifest under `apps/<app-id>/` (the manifest + any local sources).
4. Open a **pull request against the `new-pr` branch**.
5. CI **test-builds** your PR (the review gate) — it must build clean and pass
   `flatpak-builder-lint`.
6. A reviewer checks it against the [submission policy](SUBMISSION.md).
7. On **merge into `new-pr`**, CI **builds, signs, and publishes** the app to
   `https://dl.openpak.org/repo/`.

Install any published app:

```sh
flatpak remote-add --if-not-exists openpak https://dl.openpak.org/repo/openpak.flatpakrepo
flatpak install openpak <app-id>
```

## Policy in one line

**AI-assisted and AI-generated contributions are welcome.** We gate on quality,
maintenance, distinctness, clean licensing, and respect for users — never on how
the work was made. See [SUBMISSION.md](SUBMISSION.md).
