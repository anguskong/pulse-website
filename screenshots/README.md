# Screenshots for App Store

## Required Screenshots

Place your iPhone 16 Pro Max (6.7" display) screenshots here.

### Naming Convention

Use these exact filenames for clarity:

1. `01-idle-state.png` - Timer at rest, Quick Focus selected, play button visible
2. `02-work-mode.png` - Timer running, red progress ring, counting down
3. `03-rest-mode.png` - Green progress ring, REST phase active
4. `04-preset-picker.png` - Preset selection sheet showing built-in and custom presets
5. `05-create-preset.png` - Create new preset form with all fields

### Expected Dimensions

- **Resolution**: 1284 × 2778 pixels
- **Format**: PNG (preferred) or JPEG
- **Orientation**: Portrait

### How to Capture

1. Open Xcode
2. Run Pulse on iPhone 16 Pro Max simulator
3. Navigate to each screen as described in the main README
4. Press **Cmd+S** in simulator to save
5. Move screenshots from Desktop to this directory
6. Rename according to convention above

### Quick Verification

After capturing all screenshots, run:
```bash
cd ~/monorepo/ios/app-landing-pages/pulse-website/screenshots
ls -la *.png
file *.png  # Should show 1284x2778 for each
```

You should see 5 PNG files, each exactly 1284×2778 pixels.

---

**Once you have all 5 screenshots, you're ready to upload them to App Store Connect!**
