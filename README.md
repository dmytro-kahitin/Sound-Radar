# Sound Radar

---

## Overview  
Sound Radar is a Windows application designed for people with single-sided deafness and for users who want to better perceive directional audio in games and other applications.  
It processes multichannel sound in real time, displays a radar interface to visualize sound direction, and returns enhanced audio back to the playback device.  

The program uses a virtual audio cable for routing, adds almost no latency, and offers both a desktop and web-based settings interface. The web interface can also be accessed from a mobile browser when properly configured (same WiFi network or etc).  

Currently, Sound Radar has been tested with **PUBG**, but it should work with any application or game that supports 7.1 surround sound.  

⚠️ **Note**: This is a **free application** and will only be shared through this repository.  
Do not download it from other sources and do not buy it — if you want to support the project, a donation is welcome (see link above).

---

### Demonstration

[![Program demonstration on YouTube](https://img.youtube.com/vi/sHK7LD7p8Ug/maxresdefault.jpg)](https://youtu.be/sHK7LD7p8Ug)

[Program demonstration on YouTube](https://youtu.be/sHK7LD7p8Ug)
---

### Donation
This application is developed and shared for free.  
If you find it useful and would like to support future development, you can make a donation here: [Donate via Donatello](https://donatello.to/sound-radar)  

---

## Features  
- **Real-time radar visualization** of sound sources for improved spatial awareness.  
- **Dynamic Range Compression (DRC)**  
  - Makes important sounds (like footsteps or reloading) stand out by automatically reducing overly loud sounds and boosting quieter ones.  
  - Improves clarity in chaotic environments where multiple sounds overlap.  
- **Duck Feature**  
  - Automatically reduces background or repetitive noises (like vehicle engines or ambient sounds) without silencing critical sounds.  
  - Helps keep focus on important directional audio.  
- **Noise Reduction (Denoiser)**  
  - Uses the RNNoise algorithm to filter out background noise and keep only speech/voice sounds.  
  - Useful for voice-heavy games or communication scenarios where clarity is key.  
- Integrated web-based settings interface with remote access.  
- Global hotkey support.  
- Extensive configuration and customization options.  
- Minimal latency for seamless audio experience.  
- Low CPU usage.

---

## Installation Tutorial  
**The setup may seem complex, but once configured, daily use is straightforward.**  

[Installation Tutorial on YouTube](https://youtu.be/72eES99VVq8?si=z3tcSkzYd6Ze9HxN)

### It seems that VB Cable conflicts with Steelseries Sonar, so if you want to use Sound Radar, you must uninstall Sonar or try to work around it somehow.

Follow these steps carefully to install and configure Sound Radar:

1. Download `Sound_Radar_1.0_Installer.exe` from the **Releases** section and `VBCABLE.zip` from the official site: https://vb-audio.com/Cable/.  
2. Extract the contents of `VBCABLE.zip` and run the installer for the **x64** version of VB-Cable.  
3. Restart your PC to ensure VB-Cable installs correctly.
4. Return your sound devices as default, because VB-Cable sets its CABLE Input and CABLE Output as sound devices by default after installing.
5. Open the Windows audio device settings (`Win + R`, type `mmsys.cpl`).  
   - In the **Playback** tab, verify that **CABLE Input** is listed.  
   - In the **Recording** tab, verify that **CABLE Output** is listed.  
6. Right-click on **CABLE Input**, select **Configure**, and choose **7.1 Surround** as the configuration. Proceed through the wizard without changing other options.  
7. Right-click on **CABLE Input**, select **Properties**, go to the **Advanced** tab, and ensure the format is set to **24 bit, 48000 Hz**.  
8. Right-click on **CABLE Output**, select **Properties**, go to the **Advanced** tab, and ensure the format is set to **8 channels, 24 bit, 48000 Hz**.  
9. Install `Sound_Radar_1.0_Installer.exe` and launch the program.  
10. Once running (first run may require some time), the radar interface will be visible, and an application icon will appear in the system tray.  
    - To open settings, either press the default hotkey (**Ctrl+Shift+F3**) or right-click the tray icon and select **Settings**.  
11. In the Sound Radar app in the **Audio** tab, under **Audio I/O**:  
    - Set **Input** to **CABLE Output (Windows WASAPI)**. There will be several CABLE Output devices listed, but you must select the WASAPI version for minimum latency.  
    - Set **Output** to your usual playback device (**Windows WASAPI version** of your headphones, speakers, etc.).  
      This device must support **stereo, 24 bit, 48000 Hz**.  
12. Start the application or game you want to use with Sound Radar.
    - Set Borderless display mode, or you will not see radar overlay.
    - In Windows sound settings, set its **Output Device** to **CABLE Input**.  
    - The sound will be routed through CABLE Input → CABLE Output → Sound Radar → your playback device.  
13. Restart the application/game (may not be required, but just do it once).  
    - If it supports surround sound, it will provide **8 channels (7.1)**.  
    - If not, it will remain **stereo**, which does not allow sound localization.  
14. Enable audio capture via hotkey, the **Audio Capture** button, or the tray icon.  
    - Sound Radar will begin processing and outputting the enhanced audio.  
15. Once setup is complete, in next session simply start Sound Radar, enable capture, and launch your game or application.

---

## Settings  
The application provides a comprehensive set of configuration tabs. All settings and tabs have tooltips with descriptions:  

- **Audio**  
  - Mix all sound to mono, stereo, or both (e.g., pull mono sound to both ears for therapeutic effect).  
  - In stereo mode, adjust the volume of each channel individually.  
  - Increase the overall loudness of the application sound.  

- **Radar**  
  - Configure radar position, size, and transparency.  
  - Adjust dot size and transparency.  
  - Select the preferred display for visualization.  

- **Groups**  
  - Fine-tune sound indicators: customize dot colors and set thresholds for sound activation.  

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
  - Use the RNNoise plugin to clean speech from background noise.  
  - Caution: it will preserve only voices, removing other sounds.  
  - Only affects the selected application’s audio, not your microphone input.  

- **Hotkeys**  
  - Configure shortcuts for enabling/disabling Sound Radar, toggling Duck mode, and opening settings.  

- **ESP & Vibro (Future)**  
  - Work-in-progress tab for a vibration belt feature with 12 vibration motors and ESP-based control.  
  - Will allow sound direction to be transmitted as vibrations rather than displayed visually.  
  - Schematics and firmware will be published once available.

---

## Resources  
The installed program includes a `Resources` folder:  
- To change the radar texture, place your own image named `radar.png`, you may use `_radar.png` as example, but don't forget to rename it to the `radar.png`.  
- To change the duck icon, replace `noise.ico` with another image of the same name.  

Make sure replacement files keep the exact same filenames to be recognized by the program.  

---

## Future Work  
Planned extensions of Sound Radar include:  
- A vibration belt for tactile feedback.  
- A device that enables radar functionality in real-world environments.  

---

## License  
This project is licensed under the [Apache License 2.0](LICENSE).