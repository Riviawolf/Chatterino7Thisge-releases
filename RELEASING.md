# Pushing an update

1. In the source repo, set the new version in src/common/Version.hpp
   (CHATTERINO_VERSION), rebuild, then run .CI/package-thisge.sh. It produces
   dist/out/Chatterino7Thisge-Setup-<ver>.exe and
   dist/Chatterino7Thisge-portable-<ver>.zip.
2. Upload both files to the CDN under downloads/, so they are served at
   https://cdn.thisge.app/downloads/<file>.
3. Draft a GitHub release here tagged v<ver> with the changelog notes. Attaching
   the two files is optional; downloads come from the CDN.
4. Edit win-stable.json: set "version" to <ver> and both URLs to the new CDN
   files. Commit.
5. Installed clients pick up the update within a few minutes.

Keep the "version" in win-stable.json equal to the current released build.
Downgrades are ignored.
