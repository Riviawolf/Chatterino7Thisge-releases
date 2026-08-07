# Pushing an update

1. **Source repo:** bump the version at `CMakeLists.txt` line 71
   (`VERSION 7.5.5` -> new number), rebuild, then run `.CI/package-thisge.sh`.
   It produces `dist/out/Chatterino7Thisge-Setup-<ver>.exe` and
   `dist/Chatterino7Thisge-portable-<ver>.zip`.
2. **Here → Releases → "Draft a new release":** tag `v<ver>`, drag in both
   files, then **Publish**.
3. **Edit `win-stable.json`:** set `"version"` to `<ver>` and point both URLs at
   the new release's assets (`.../releases/download/v<ver>/<file>`). Commit.
4. Installed clients pick up the update within a few minutes.

Keep `win-stable.json`'s `"version"` equal to the current released build. The app
compares it to its own version and shows the update button only when the
manifest is higher; downgrades are ignored.
