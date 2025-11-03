# Sound Radar

---

## Overview
Sound Radar is a Windows application designed for people with single-sided deafness and for users who want to better perceive directional audio in games and other applications.  
It processes multichannel (7.1) or stereo sound in real time, displays a radar interface to visualize sound direction (desktop or web), and returns enhanced audio back to the playback device.

The program uses a virtual audio cable for routing, adds almost no latency, and offers both a desktop and web-based settings interface. The web interface can also be accessed from a mobile browser when properly configured (same Wi-Fi network, port forwarding, etc.).

⚠️ **Note**: This is a **free application** and will only be shared through this repository.  
Do not download it from other sources and do not buy it — if you want to support the project, a donation is welcome (see link below).

---

### Demonstration

<a href="https://youtu.be/sHK7LD7p8Ug">
  <img src="https://img.youtube.com/vi/sHK7LD7p8Ug/maxresdefault.jpg" alt="Program demonstration on YouTube" width="480" />
</a>

[Program demonstration on YouTube](https://youtu.be/sHK7LD7p8Ug)


---

### Donation
This application is developed and shared for free.  
If you find it useful and would like to support future development, you can make a donation here:  
[Donate via Donatello](https://donatello.to/sound-radar)

---

## Features
- **Real-time radar visualization** of sound sources for improved spatial awareness.
- **Stereo Radar Mode**  
  - For games/apps that only output stereo (e.g. CS2).  
  - Shows direction as left / right / center even without 7.1.
- **Web Radar**  
  - Radar can be opened in a browser (PC or mobile) for games that block overlays.  
  - Mirrors normal radar, including stereo radar.
- **Preset System**  
  - Save your full configuration as presets for different games.  
  - Presets can be exported/imported for backup or sharing.  
  - App config still stores your personal things (devices, skin, etc.).
- **Shared Presets**  
  - Browse, download, test, and rate public presets from inside the app.  
  - Search by name, author, or metadata.
- **Dynamic Point Categories**  
  - Up to 10 configurable groups with their own color, amount, and sensitivity.
- **Dynamic Range Compression (DRC)**  
  - Makes important sounds stand out by reducing overly loud sounds and boosting quiet ones.
- **Duck Feature**  
  - Automatically reduces background/repetitive noises without silencing critical sounds.
- **Noise Reduction (Denoiser)**  
  - RNNoise-based filtering to keep voice/speech and remove background noise.
- **16-bit Device Support**  
  - Output can work with 16-bit devices (common for wireless headsets) while VB-Cable stays at 24-bit.
- **Integrated web-based settings interface** with remote access.
- **Global hotkey support.**
- **Minimal latency and low CPU usage.**
- **Update Checker**  
  - Automatically checks GitHub releases and notifies about new versions.

---

## Installation Tutorial
**The setup may seem complex, but once configured, daily use is straightforward.**

[Installation Tutorial on YouTube](https://youtu.be/72eES99VVq8?si=z3tcSkzYd6Ze9HxN)

Follow these steps carefully to install and configure Sound Radar:

1. Download `Sound_Radar_1.8.1_Installer.exe` from the **Releases** section and `VBCABLE.zip` from the official site: https://vb-audio.com/Cable/.  
2. Extract the contents of `VBCABLE.zip` and run the installer for the **x64** version of VB-Cable.  
3. Restart your PC to ensure VB-Cable installs correctly.
4. Return your sound devices to default, because VB-Cable sets its **CABLE Input** and **CABLE Output** as sound devices by default after installing.
5. Open the Windows audio device settings (`Win + R`, type `mmsys.cpl`).  
   - In the **Playback** tab, verify that **CABLE Input** is listed.  
   - In the **Recording** tab, verify that **CABLE Output** is listed.
6. Right-click on **CABLE Input**, select **Configure**, and choose **7.1 Surround** as the configuration. Proceed through the wizard without changing other options.
7. Right-click on **CABLE Input**, select **Properties → Advanced**, and set the format to **24 bit, 48000 Hz**.
8. Right-click on **CABLE Output**, select **Properties → Advanced**, and set the format to **8 channels, 24 bit, 48000 Hz**.
9. Install `Sound_Radar_1.8.1_Installer.exe` and launch the program.
10. On first run, wait until the app finishes initialization; an icon will appear in the tray and the radar will be visible.
11. Open settings with the default hotkey **Ctrl+Shift+F3** or by right-clicking the tray icon → **Settings**.
12. In **Audio** tab in Sound Radar:
    - **Input** → **CABLE Output (Windows WASAPI)** (pick the WASAPI variant for lower latency).
    - **Output** → your regular playback device (**Windows WASAPI** headphones/speakers).  
      This device may be 24-bit or 16-bit now, but prefer **48000 Hz**.
13. Start the game/app you want to use with Sound Radar.
    - Set borderless display mode if you want to see the desktop overlay.
    - In Windows sound settings, set the game’s **Output Device** to **CABLE Input**.
    - Signal path: **Game → CABLE Input → CABLE Output → Sound Radar → Your device**.
14. Restart the game/app once if it doesn’t immediately output 7.1.
15. Enable audio capture in Sound Radar (hotkey, button, or tray icon).

Next time: start Sound Radar → enable capture → start your game.

---

## Settings
The application provides a comprehensive set of configuration tabs. All settings and tabs have tooltips with descriptions:

- **Audio**
  - Mix to mono, stereo, or both.
  - Per-channel level for stereo.
  - Overall loudness boost.
  - Stereo Radar enable/disable (for stereo-only games).
- **Radar**
  - Position, size, transparency.
  - Dot size and transparency.
  - Desktop vs web radar use.
  - Skin selection (custom images you added).
- **Groups / Point Categories**
  - Up to 10 groups.
  - Colors, thresholds, quantity per group.
  - Fine-tune what is shown on radar for different sound types.
- **Presets**
  - Save current settings as a preset.
  - Load preset for a specific game.
  - Export / import preset files.
  - Browse / download shared presets.
- **DRC (Dynamic Range Compression)**
  - Reduce loud sounds and boost quiet ones (e.g., make footsteps clearer while preventing loud gunfire from overwhelming).  
  - Multiple presets available plus detailed customization.  
  - Separate DRC settings for what the radar detects and what you hear.
- **Duck**  
  - Suppress repetitive background sounds (e.g., engine noise) without affecting other sounds.  
  - Multiple presets available plus detailed customization.  
  - Separate Duck settings for radar detection and playback.  
  - Can be toggled via the **Duck Mode** button or hotkey. When enabled, a small icon appears in the top-left of the screen.  
  - Duck mode automatically disables when settings are changed and needs to be re-enabled.
- **Denoiser**
  - RNNoise on game audio.
  - Keeps voice, removes background.
- **Hotkeys**
  - Enable/disable capture.
  - Toggle duck.
  - Open settings.
- **Updates**
  - Check for new version on GitHub.

---

## Tips & Troubleshooting

### 1. Counter-Strike 2 (stereo-only games)
CS2 does not output 7.1, so use Stereo Radar:

1. In **Sound Radar → Audio**, enable **Stereo Radar** (or “Stereo mode”).
2. In **CS2 → Settings → Audio**:
   - **Audio Device**: select **CABLE Input**.
   - **EQ Profile**: **CRISP**
   - **L/R Isolation**: **100**
   - **Perspective Correction**: **No**
3. Now radar will show **left / right / center** directions for CS2.

### 2. No sound and no dots, but no errors in Sound Radar
Check the usual causes:

- **SteelSeries Sonar installed**  
  For some reason VB-Cable may not work together with Sonar.  
  → Try **uninstalling Sonar** or disabling its virtual devices and re-selecting CABLE Input/Output.

- **Alternative: VOICEMEETER BANANA**  
  If you don’t want to remove Sonar or if VB-Cable still behaves incorrectly (Sound Radar doesn’t show any error, you made everything right, but it doesn’t draw any dots and doesn’t play sound), try using Voicemeeter Banana as the routing layer.  
  - Download from official site: https://vb-audio.com/Voicemeeter/banana.htm  
  - Install it and reboot your PC.  
  - Open **Voicemeeter Banana x64** (not just Voicemeeter, you need exactly Voicemeeter Banana x64).  
  - Disable A1, A2, A3 and B2 buttons like on screenshot:  
    [<img src="https://raw.githubusercontent.com/dmytro-kahitin/Sound-Radar/main/resources/voicemeeter-banana.png" width="220" alt="Voicemeeter Banana setup" />](https://raw.githubusercontent.com/dmytro-kahitin/Sound-Radar/main/resources/voicemeeter-banana.png)
  - Now make the same settings for **Voicemeeter Input** device as for **CABLE Input** device, and set the same settings for **Voicemeeter Out B1** as for **CABLE Output**.  
  - In the game, set the output device to **Voicemeeter Input**.  
  - In Sound Radar, on the **Audio** tab, in **Input** device, choose **Voicemeeter Input**.

If the graph is correct and capture is enabled, you should both **hear** sound and **see** dots.

---

## Future Work
Planned extensions of Sound Radar include:
- A vibration belt for tactile feedback.
- A device that enables radar functionality in real-world environments.

---

## License
This project is licensed under the [Apache License 2.0](LICENSE).