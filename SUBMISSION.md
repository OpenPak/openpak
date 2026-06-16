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

- Place the manifest at the **repo root** as `<app-id>.{yaml,yml,json}`, on a branch
  named after the app id.
- `<app-id>` is your reverse-DNS application id (e.g. `io.github.you.App`).
- Ship valid AppStream `metainfo` (name, summary, description, license, screenshots)
  and a `.desktop` file + icon — these power the store listing.
- Pin sources (tag **and** commit, or a checksum) — no moving refs.
- Request only the permissions the app needs.

## What CI does

- **On your PR** (`test-build.yml`): builds the root manifest with `flatpak-builder`,
  runs `flatpak-builder-lint`, and uploads an installable test bundle. Must pass to be
  merge-eligible.
- **On merge to `new-pr`** (`onboard.yml`): creates `OpenPak/<app-id>`, seeds it with
  your manifest + a build workflow, and propagates publishing secrets. That repo then
  builds your app, **signs** the repo summary with the Openpak repo-signing key, and
  syncs to `dl.openpak.org`. The private signing key lives only in CI secrets — never
  committed and never on the download host.
- **Future updates:** PR/push to `OpenPak/<app-id>` — it rebuilds and republishes.
