# SortMyPhoto

Downloads for SortMyPhoto, a Mac app that culls sports and event photos with Gemini and labels them for Adobe Bridge.

## Install

1. Download the latest `.dmg` from [Releases](https://github.com/jimmydeparis/sortmyphoto-releases/releases/latest) (Apple silicon Macs: M1 and later).
2. Open it and drag **SortMyPhoto** to **Applications**.
3. The first time, macOS may say it can't check the app. Open **System Settings → Privacy & Security**, scroll down and click **Open Anyway**. You only do this once.
4. Paste the licence key you were given. The app needs the internet once to activate, then checks the key about once a day; it keeps working offline for up to 14 days.

### Install with Claude or Terminal

Apple silicon Macs only (M1 to M4 and later). These commands download the latest version, replace any older copy in Applications, clear the "downloaded from the internet" flag so macOS doesn't block the first launch, and open the app:

```bash
curl -fL -o /tmp/SortMyPhoto.dmg https://github.com/jimmydeparis/sortmyphoto-releases/releases/latest/download/SortMyPhoto.dmg
hdiutil attach -nobrowse -quiet /tmp/SortMyPhoto.dmg
rm -rf /Applications/SortMyPhoto.app
cp -R /Volumes/SortMyPhoto/SortMyPhoto.app /Applications/
hdiutil detach -quiet /Volumes/SortMyPhoto
rm /tmp/SortMyPhoto.dmg
xattr -dr com.apple.quarantine /Applications/SortMyPhoto.app
open /Applications/SortMyPhoto.app
```

Run the same commands again to update. Paste the licence key into the app yourself; it doesn't need to go to Claude.

You also need your own **paid-tier** Gemini API key (Google AI Studio, linked to billing). The free tier lets Google train on uploaded photos.

## In Adobe Bridge

Rename the colour labels to **Red, Yellow, Green, Blue, Purple** (Bridge → Settings → Labels) so the labels the app writes show up.
