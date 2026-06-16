<!--
Thanks for submitting an app to Openpak!

Open this pull request against the `new-pr` branch.
Add your manifest at the repo ROOT as `<app-id>.{yaml,yml,json}`, on a branch named
after your app id (e.g. `io.github.you.App`).

Submission guide:  ./SUBMISSION.md
Openpak judges the work, not the workflow — AI-assisted and AI-generated
contributions are welcome. We gate on quality, maintenance, and good faith.
-->

#### Submission checklist

- [ ] The PR targets the `new-pr` branch.
- [ ] The branch is named after the app id, and the manifest lives at
      the repo ROOT as `<app-id>.{yaml,yml,json}`.
- [ ] The app id is a valid reverse-DNS id I control (or that matches the project's
      domain / hosting), e.g. `io.github.you.App`.
- [ ] The app is free/open-source software, **or** I am the developer (or am
      authorized) to publish this proprietary app.
- [ ] The Flatpak **builds and runs locally** (`flatpak-builder` + install + launch).
- [ ] The manifest requests **only the permissions the app needs**
      (`finish-args`) — no broad filesystem or unnecessary device/socket access.
- [ ] The app ships valid **AppStream `metainfo`** (name, summary, description,
      license, screenshots) and a `.desktop` file + icon.
- [ ] Sources are pinned (tag **and** commit, or a checksum) — no moving refs.
- [ ] Licensing is clean: no copyrighted, license-incompatible, or plagiarised code.
- [ ] I have read the [submission policy](../SUBMISSION.md) and will engage with
      reviewers respectfully.

#### App

- **App id:**
- **Upstream / homepage:**
- **Summary (one line):**

#### Notes for reviewers

<!-- Anything reviewers should know. Optionally: disclose heavy AI involvement
     (encouraged for context, never required and never grounds for rejection). -->
