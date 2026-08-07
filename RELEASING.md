# Pushing an update

1. In the source repo, set the new version in src/common/Version.hpp
   (CHATTERINO_VERSION), rebuild, then run .CI/package-thisge.sh. It builds the
   installer and portable zip, then prints the SHA-256s, a ready gh release
   command, and the win-stable.json snippet.
2. Create the GitHub release (its assets host the binaries):
   gh release create v<ver> dist/out/Chatterino7Thisge-Setup-<ver>.exe dist/Chatterino7Thisge-portable-<ver>.zip --repo Riviawolf/Chatterino7Thisge-releases --title "v<ver>" --notes "<changelog>"
   Or use the web UI: Releases, then "Draft a new release", tag v<ver>, drag in
   both files, Publish.
3. Update win-stable.json here: set "version" to <ver> and both URLs to the new
   release assets (.../releases/download/v<ver>/<file>). Commit.
4. Hand the two asset URLs and SHA-256s to the site (Admin, Site, Download links).
5. Installed clients pick up the update within a few minutes.

Keep "version" in win-stable.json equal to the current released build.
Downgrades are ignored.
