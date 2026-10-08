# Setup (one time, ~10 minutes)

1. **Install Claude Code.** Follow the instructions at https://claude.com/claude-code, then sign in.
2. **Put these files in your repo.** Unzip this folder. On GitHub, open `mmondejarr-code/omyaevents` → **Add file → Upload files**, drag in everything in this folder, and click **Commit changes**.
3. **Link Netlify.** In Netlify, open your site → **Site configuration → Build & deploy → Link repository**, pick `omyaevents`, branch `main`. Leave the build settings empty (`netlify.toml` covers them).
4. **Get the repo on your computer.** In a terminal, run:
   ```
   git clone https://github.com/mmondejarr-code/omyaevents.git
   cd omyaevents
   claude
   ```

From then on, open a terminal in that folder, type `claude`, and ask, for example:
"Add this photo to the San Francisco gallery and push it live." It reads `CLAUDE.md`, makes the change, and pushes. Netlify updates the site.
