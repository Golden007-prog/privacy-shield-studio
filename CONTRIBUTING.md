# Contributing to PrivacyShield Studio

Thanks for wanting to help! 🎉 Every contribution is welcome: bug reports, ideas, docs, translations and code.

By taking part you agree to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Ways to help

- ⭐ **Star the repo.** It genuinely helps other people find it.
- 🐛 **Report a bug** with the [bug report form](https://github.com/reseachrandomv/privacy-shield-studio/issues/new?template=bug_report.yml).
- 💡 **Suggest a feature** with the [feature request form](https://github.com/reseachrandomv/privacy-shield-studio/issues/new?template=feature_request.yml), or start a thread in [Discussions](https://github.com/reseachrandomv/privacy-shield-studio/discussions).
- 🧑‍💻 **Pick up an issue.** Look for [`good first issue`](https://github.com/reseachrandomv/privacy-shield-studio/labels/good%20first%20issue) and [`help wanted`](https://github.com/reseachrandomv/privacy-shield-studio/labels/help%20wanted).

Comment on an issue before you start so nobody duplicates work.

## Project principles

- Keep it **three static files** with **no build step** and **no npm dependencies**.
- **No network calls.** The CSP sets `connect-src 'none'`; anything that needs `fetch`, analytics or a server will not be merged.
- Never commit real secrets. New detection patterns must use obviously fake samples, assembled at runtime the way `buildSampleLeak()` in `app.js` does, so secret scanners do not flag the repo.
- User input, images and generated secrets must never be written to `localStorage`, only UI settings.

## Project layout

The app is `index.html` (layout), `styles.css` (Glass UI styles) and `app.js` (all logic). There is no framework, bundler or package manager.

| Area | Where to look |
|---|---|
| New secret pattern | `RULES` array in `app.js` (Module 1). Add the regex to the right rule group, give a positive and a negative example in the PR, and update the README "Secret scrubber rules" table. |
| New tracking parameter | `TRACKING_PARAMS` / `TRACKING_PREFIXES` in `app.js` (Module 3) and the README list. |
| Metadata formats | `inspectJpeg()`, `inspectPng()`, `inspectWebp()`, `parseTiff()` in `app.js` (Module 2). |
| Generator | `randomInt()`, `genPassword()`, `genPassphrase()`, `genKey()`, `strengthLevel()` in `app.js` (Module 4). Randomness must come from `crypto.getRandomValues()` only. |

## Local development

```bash
git clone https://github.com/reseachrandomv/privacy-shield-studio.git
cd privacy-shield-studio
python3 -m http.server 8080   # or any static server, then open http://localhost:8080
```

You can also open `index.html` directly, but a local server gives you the modern Clipboard API.

## Pull request checklist

1. Fork the repo and create a branch: `git checkout -b feat/short-description`.
2. Keep PRs small and focused on one change.
3. Test in at least two browsers (e.g. Chrome and Firefox), at desktop and phone widths.
4. Open DevTools and confirm there are **no console errors** and **no new network requests**.
5. Check keyboard access: every new control must be reachable with <kbd>Tab</kbd> and have a visible focus ring.
6. Update `README.md` if you change behaviour, shortcuts, patterns or templates.
7. Fill in the pull request template.

## Commit messages

Short, imperative messages are great: `Add Stripe restricted key pattern`, `Fix focus ring on mode switcher`. Prefixes like `feat:`, `fix:` and `docs:` are welcome but not required.

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
