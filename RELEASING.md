# Pushing an update

1. In the source repo, set the new version in src/common/Version.hpp
   (CHATTERINO_VERSION), rebuild, then run .CI/package-thisge.sh. It reads the
   version from Version.hpp and produces
   dist/out/Chatterino7Thisge-Setup-<ver>.exe and
   dist/Chatterino7Thisge-portable-<ver>.zip.
2. On GitHub, go to Releases, then "Draft a new release". Tag it v<ver>, drag in
   both files, and Publish.
3. Edit win-stable.json: set "version" to <ver> and point both URLs at the new
   release assets (.../releases/download/v<ver>/<file>). Commit.
4. Installed clients pick up the update within a few minutes.

Keep the "version" in win-stable.json equal to the current released build. The
app compares it to its own version and shows the update button only when the
manifest is higher. Downgrades are ignored.
