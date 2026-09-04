# picklestack.github.io

The PickleStack site. It exists for one technical reason beyond the landing page: iOS reads
`/.well-known/apple-app-site-association` **only from a domain root**, and on GitHub Pages
only an org or user site serves a root — project sites live under a path and cannot host it.

- `.nojekyll` — **load-bearing.** Pages runs Jekyll by default and Jekyll silently drops any
  path beginning with a dot, so without this `.well-known` is never published. The site looks
  healthy and the universal link just never validates.
- `.well-known/apple-app-site-association` — association for `M7975H254R.com.theguch.PickleStack`,
  covering `/link*` (invite links) and `/add*` (connect codes).
- `link/` — where an invite link lands when the app is not installed: App Store badge plus the
  "tap the link again after installing" step, which iOS requires because it cannot hand a link
  to an app that was not installed at tap time.
