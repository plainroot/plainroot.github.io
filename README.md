# plainroot.github.io

The pages served at <https://plainroot.github.io>.

- [Landing](index.html)
- [Privacy policy](privacy.html) — Uzak
- [Support](support.html) — Uzak

All static HTML with no scripts, no trackers and no external requests.

## Serving it

GitHub Pages publishes the default branch root; there is no build step and no
workflow file. Pages must be enabled on a **public** repository — Pages from a
private repository needs a paid plan, and this path is meant to stay free.

The privacy and support URLs are quoted verbatim in the Uzak app
(`screen-time-ios`, `ScreenTime/Model/Legal.swift`) and go into App Store
Connect. Renaming or moving either file breaks a shipped build.

## Checking it is up

    curl -sI https://plainroot.github.io/
    curl -sI https://plainroot.github.io/privacy.html
    curl -sI https://plainroot.github.io/support.html

All three must answer `HTTP/2 200`. GitHub serves a generic "no site here"
page with `etag: "6aac0af2-239b"` and `content-length: 9115` for every path
when Pages is off or the repository is gone, so a 404 with that etag means
the site is not published rather than one file being missing.

The build state behind it:

    gh api /repos/plainroot/plainroot.github.io/pages

Expect `status: built`, `source.branch: main`, `source.path: /`. A push takes
about a minute to appear.

Written with AI assistance.
