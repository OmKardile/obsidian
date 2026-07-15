Now let's do a final syntax check across every single file before packaging:23 files, all clean. Let's package the final zip:Complete production package. 38 files, everything included.

---

**Gameplay clips — 3 ways to use it:**

```bash
node autoClip.js "C:\path\to\your-stream-recording.mp4" --clips 6 --duration 40 --mode crop --out assets/output/bgmi

# Option 1: Your own recordings (best — zero copyright)
# Drop .mp4 files into assets/gameplay-clips/ then:
node pipeline.js --mode commentary --game "Minecraft"

# Option 2: Twitch clips (free, legitimate — clips are meant to be shared)
# Get keys at dev.twitch.tv → Register App → Client ID + Secret
# Add to .env: TWITCH_CLIENT_ID= / TWITCH_CLIENT_SECRET=
node pipeline.js --mode funny --game "GTA 5"

# Option 3: yt-dlp (broadest coverage)
pip install yt-dlp
node pipeline.js --mode savage --game "Valorant"

# Multiple games for variety:
node pipeline.js --mode gaming --series "Speed Test" --game "GTA 5,Minecraft,Forza"

# Full combo — series + gameplay + Hindi:
node pipeline.js --mode commentary --lang hi --series "Gaming Facts" --game "BGMI"
```

**Gameplay mode vs regular mode:**

- With `--game`: full-screen gameplay footage, AI script is commentary over it, no split-screen
- Without `--game`: stock footage top 60% + satisfying loop bottom 40%

**For Twitch keys** (takes 2 minutes):

1. Go to `dev.twitch.tv` → Console → Register Your Application
2. Name it anything, redirect URL `http://localhost`, category `Other`
3. Copy Client ID + Client Secret → paste into `.env`