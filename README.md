# haqaliz/homebrew-vocca

Homebrew tap for [**Vocca**](https://github.com/haqaliz/vocca) — open-source,
local-first voice dictation for macOS.

> **No cask yet.** The first installable release has not been cut. This tap is
> reserved; `Casks/vocca.rb` lands with it.

Once it does:

```bash
brew install --cask haqaliz/vocca/vocca
xattr -dr com.apple.quarantine /Applications/Vocca.app   # before opening it
open /Applications/Vocca.app
```

Vocca is signed with an Apple Development certificate and is **not notarized
yet**, so macOS quarantines it on download. Run the `xattr` line **before** the
first launch — opening a quarantined app does not warn you, macOS deletes it.

Do not pass `--no-quarantine` to Homebrew: that flag no longer exists, and the
command fails with `Error: invalid option`.

Vocca has no Dock icon and no window at launch — it is a menu bar app. It asks
for Microphone and Accessibility permission (it cannot type into other apps
without Accessibility) and downloads its speech model on first run.

Requires **Apple Silicon** and **macOS 15** or later.

## Note for maintainers

`Casks/vocca.rb` is a **mirror**. The source of truth is
[`homebrew/vocca.rb`](https://github.com/haqaliz/vocca/blob/master/homebrew/vocca.rb)
in the Vocca repo; edit it there, then copy it here. Every release bumps
`version` and pastes the DMG's `sha256` from that release's `SHA256SUMS.txt`.
