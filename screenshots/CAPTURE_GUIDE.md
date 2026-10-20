# Screenshot Capture Guide - Step by Step

Follow these steps to capture all 5 required screenshots. **Estimated time: 15-20 minutes**

---

## 🎬 Setup (One Time)

Xcode should now be open. If not:
```bash
open -a Xcode ~/monorepo/ios/Pulse/Pulse.xcodeproj
```

### Step 1: Select iPhone 16 Pro Max Simulator
1. In Xcode's top toolbar, you'll see a device selector (next to the Run button)
2. Click it
3. Select **iPhone 16 Pro Max**
4. If you don't see it, click "Add Additional Simulators..." and download it

### Step 2: Run the App
1. Click the ▶️ (Play/Run) button in Xcode, OR press `Cmd+R`
2. Simulator will launch and the app will appear
3. Wait for the app to fully load

---

## 📸 Screenshot 1: Idle State

**What to show**: Timer at rest with Quick Focus preset selected

### Steps:
1. App should already be in idle state when it launches
2. Make sure it shows:
   - "Quick Focus" at the top
   - "0:30" timer display
   - Large play button visible
   - Reset button NOT visible (should be idle)

3. **Capture**: Press `Cmd+S` in the Simulator window
4. Save dialog appears:
   - Save as: `01-idle-state.png`
   - Location: Desktop (default) - we'll move it later
5. Click Save

✅ Screenshot 1 complete!

---

## 📸 Screenshot 2: Work Mode Active

**What to show**: Timer running during work phase with red progress ring

### Steps:
1. In the simulator, tap the large **Play button**
2. Timer starts counting down
3. Wait **5-8 seconds** for a nice visual (ring about 1/4 filled)
4. You should see:
   - "WORK" indicator
   - Red/orange progress ring partially filled
   - Timer showing around 0:22 - 0:25
   - Pause button (instead of play)

5. **Capture**: Press `Cmd+S` in the Simulator window
6. Save as: `02-work-mode.png`
7. Click Save

✅ Screenshot 2 complete!

---

## 📸 Screenshot 3: Rest Mode Active

**What to show**: Timer during rest phase with green progress ring

### Steps:

**Option A: Quick Method (Recommended)**
1. Stop the app: Xcode → Stop button (⏹) or `Cmd+.`
2. In Xcode, open: `Pulse/Models/TimerPreset.swift`
3. Find the `quickFocus` preset (around line 50)
4. Temporarily change work duration:
   ```swift
   // Change this:
   workDuration: 30,
   // To this:
   workDuration: 3,  // Just 3 seconds for testing
   ```
5. Save the file (`Cmd+S`)
6. Run app again (`Cmd+R`)
7. Tap Play button
8. Wait 3 seconds for work phase to complete
9. App automatically transitions to REST phase with green ring
10. **Capture**: Press `Cmd+S`
11. Save as: `03-rest-mode.png`
12. **IMPORTANT**: Revert the change:
    ```swift
    workDuration: 30,  // Back to 30 seconds
    ```
13. Save (`Cmd+S`)

**Option B: Patient Method**
1. Just wait the full 30 seconds from Screenshot 2
2. Timer automatically transitions to REST
3. Capture when you see the green ring

You should see:
- "REST" indicator (or green ring)
- Green progress ring
- Timer counting down rest time

✅ Screenshot 3 complete!

---

## 📸 Screenshot 4: Preset Picker

**What to show**: Preset selection sheet with all presets visible

### Steps:
1. Make sure app is still running (if not, press `Cmd+R`)
2. In the simulator, tap **"Quick Focus"** text at the top of the screen
3. A sheet slides up from the bottom showing:
   - "BUILT-IN PRESETS" section with 3 presets
   - "MY PRESETS" section (probably empty)
   - "+" button in top-right corner
4. **Capture**: Press `Cmd+S` in the Simulator window
5. Save as: `04-preset-picker.png`
6. Click Save

✅ Screenshot 4 complete!

---

## 📸 Screenshot 5: Create Preset Form

**What to show**: Create new preset interface with all input fields

### Steps:
1. The preset picker should still be open from Screenshot 4
2. Tap the **"+"** button in the top-right corner
3. Create preset sheet appears showing:
   - "Name" text field
   - "Work Duration" picker
   - "Rest Duration" picker
   - "Rounds" picker
   - "Finite Rounds" / "Continuous" toggle
   - "Save" button

4. **Optional**: Fill in some sample data to make it look realistic:
   - Tap "Name" and type "Focus Session"
   - Adjust work duration to something like 45 or 50 minutes
   - This makes the screenshot more interesting!

5. **Capture**: Press `Cmd+S` in the Simulator window
6. Save as: `05-create-preset.png`
7. Click Save

✅ Screenshot 5 complete!

---

## 📦 Organize Screenshots

All 5 screenshots are now on your Desktop. Let's move them to the right location:

```bash
cd ~/Desktop

# Verify you have all 5
ls -la 0*.png

# Move to screenshots directory
mv 01-idle-state.png ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/
mv 02-work-mode.png ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/
mv 03-rest-mode.png ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/
mv 04-preset-picker.png ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/
mv 05-create-preset.png ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/

# Verify they're in the right place
ls -la ~/monorepo/ios/app-landing-pages/pulse-website/screenshots/*.png
```

---

## ✅ Verify Screenshots

Let's make sure they're the right size:

```bash
cd ~/monorepo/ios/app-landing-pages/pulse-website/screenshots
file *.png
```

You should see:
```
01-idle-state.png: PNG image data, 1284 x 2778, ...
02-work-mode.png: PNG image data, 1284 x 2778, ...
03-rest-mode.png: PNG image data, 1284 x 2778, ...
04-preset-picker.png: PNG image data, 1284 x 2778, ...
05-create-preset.png: PNG image data, 1284 x 2778, ...
```

All should be **1284 × 2778** pixels (App Store required size for 6.7" displays).

---

## 🎨 Preview Screenshots (Optional)

Want to see how they look?

```bash
cd ~/monorepo/ios/app-landing-pages/pulse-website/screenshots
open *.png
```

This opens all screenshots in Preview.app so you can review them.

---

## 🚀 Commit Screenshots

Once you're happy with them:

```bash
cd ~/monorepo

git add ios/app-landing-pages/pulse-website/screenshots/*.png
git commit -m "Add App Store screenshots (5 iPhone 16 Pro Max captures)"
```

---

## ✨ Done!

You now have all 5 required screenshots! 🎉

Next steps:
1. Customize privacy policy (add email & GitHub username)
2. Follow submission guide in `START_HERE.md`

---

## 🆘 Troubleshooting

**Q: Simulator saved screenshots somewhere else**
A: Check these locations:
- Desktop (default)
- `~/Desktop`
- `~/Documents`

**Q: Wrong size (not 1284×2778)**
A: Screenshots are automatically resized to App Store specs (1284×2778). Raw simulator captures may vary.

**Q: Screenshots are too dark/light**
A: This is normal - iOS adjusts based on system appearance. Screenshots should match the simulator's appearance.

**Q: I closed the preset picker, how do I reopen it?**
A: Tap "Quick Focus" at the top of the screen again, or press Esc to dismiss sheets and start over.

**Q: App crashed or behaving weirdly**
A: Stop the app (Cmd+. in Xcode), clean build (Cmd+Shift+K), then run again (Cmd+R)

---

*Good luck with your screenshots! They'll make Pulse look great on the App Store.* 🎬
