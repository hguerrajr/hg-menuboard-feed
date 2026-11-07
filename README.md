# HG Menu Board playlist

This repo controls what plays on the HG menu board TVs.
Playlist link the TVs read: https://hguerrajr.github.io/hg-menuboard-feed/menu.json

Changes show on the TVs within about 5 minutes. No restart needed.

## Add a new slide or video (works from a phone)

1. Open the `slides` folder, tap **Add file > Upload files**, pick the file, tap **Commit changes**.
   - Images: 1920 x 1080, JPG or PNG. Videos: MP4 (H.264). Max 25 MB through the website.
   - **Always use a new file name** (for example `lunch-special-v2.jpg`). TVs keep saved copies by name.
2. Open `menu.json`, tap the pencil (Edit), add a line under the TV it belongs to:
   ```json
   { "type": "image", "url": "https://hguerrajr.github.io/hg-menuboard-feed/slides/NEW-FILE.jpg", "duration": 15 },
   { "type": "video", "url": "https://hguerrajr.github.io/hg-menuboard-feed/slides/NEW-VIDEO.mp4" }
   ```
3. Tap **Commit changes**.

## Rules for menu.json

- Each TV has its own list under `screens` (`atv1`, `atv2`, ...). Slides play top to bottom, then loop.
- Items are separated by commas. **No comma after the last item in a list.**
- `duration` is seconds (images only). Videos play to the end.
- Optional schedule on any item: `"days": ["mon","tue"]`, `"startTime": "11:00"`, `"endTime": "15:00"` (TV's time zone).
- If you make a typo, the TVs keep playing what they had. Nothing goes blank.

## Remove a slide

Delete its line from `menu.json` (watch the commas). You can also delete the file from `slides`.
