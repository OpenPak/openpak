# Openpak submission policy

Deliberately strict — about the *right things*.

## On AI
AI-assisted and AI-generated contributions are welcome. We will never ask whether
a tool was used, and never reject a submission *because* one was. Disclosing heavy
AI involvement is encouraged (for reviewer/user context) but not required.

## What we gate on (quality)
1. **It works.** Builds reproducibly, launches, does what it claims. Reviewers test it.
2. **It's maintained.** Credible sign of ongoing ownership — responsive maintainer,
   real changelog, an answered issue tracker. One-shot abandonware is rejected.
3. **It's distinct.** Not the fortieth identical to-do app or bare web-wrapper.
4. **It's licensed cleanly.** No copyrighted, license-incompatible, or plagiarised code.
5. **It respects users.** Correct metadata, honest permissions, no dark patterns,
   no undisclosed telemetry.

## Conduct
Reviewers are volunteers. Hostility, entitlement, or badgering is grounds for
rejection and, if repeated, a ban.

---

## Manifest requirements

- Place the manifest at `apps/<app-id>/<app-id>.yaml` (or `.yml`/`.json`).
- `<app-id>` is your reverse-DNS application id (e.g. `io.github.you.App`).
- Ship valid AppStream `metainfo` (name, summary, description, license, screenshots)
  and a `.desktop` file + icon — these power the store listing.
- Request only the permissions the app needs.

## What CI does

- **On your PR** (`test-build.yml`): builds the changed manifest with
  `flatpak-builder` and runs `flatpak-builder-lint`. Must pass to be merge-eligible.
- **On merge to `new-pr`** (`publish.yml`): pulls the current signed repo, builds your
  app into it, regenerates and **signs** the summary with the Openpak key, and syncs
  it to `dl.openpak.org`. The private signing key lives only in CI secrets — never in
  this repo and never on the download host.
