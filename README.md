# Sound Radar

Sound Radar is a Windows app that helps you see where game audio comes from.

It listens to multichannel or stereo game sound, draws sound events on a radar overlay, optionally improves the audio, and then plays the result back to your headphones or speakers.

The project is mainly designed for people with single-sided hearing loss, but it can also help anyone who wants a clearer visual cue for directional sound.

## Important

Sound Radar is free and is distributed only from this repository.

Do not buy it from third-party sites. If you want to support development, use the support links in the app or in this README.

## Support And Ukraine

Sound Radar is made in Ukraine and shared for free.

If the app helps you, there are two good ways to support it:

- [Support Sound Radar development](https://donatello.to/sound-radar)
- [Support Ukraine through United24](https://u24.gov.ua/)

No pressure, no locked features. The app stays free either way.

## How It Works

Most games can output surround sound if they see a 7.1 playback device. Sound Radar uses a virtual audio cable to make that possible.

Typical route:

```text
Game
  -> VB-Cable / Voicemeeter virtual playback device
  -> Sound Radar capture
  -> direction detection and optional audio processing
  -> your real headphones or speakers
```

For stereo-only games, Sound Radar can use stereo radar mode. It will not invent true 7.1 information, but it can still show left, right, and center movement clearly.

## Demonstration

[Watch the demo on YouTube](https://youtu.be/sHK7LD7p8Ug)


<a href="https://youtu.be/sHK7LD7p8Ug">
  <img src="https://img.youtube.com/vi/sHK7LD7p8Ug/maxresdefault.jpg" alt="Program demonstration on YouTube" width="480" />
</a>

## Quick Start

1. Install VB-Cable or Voicemeeter Banana.
2. Configure the virtual playback/capture pair as 7.1 where possible.
3. Install the latest Sound Radar release.
4. Start Sound Radar.
5. Follow the setup guide.
6. In your game, set the output device to the virtual cable input.
7. Start Sound Radar capture and run the sound/radar test.

If the first run feels confusing, use the setup video:

[VB-Cable setup tutorial](https://www.youtube.com/watch?v=72eES99VVq8)

## Recommended Audio Setup

Use Windows sound settings (`Win + R`, then `mmsys.cpl`).

For VB-Cable:

- Playback tab: configure `CABLE Input` as 7.1 surround.
- Playback tab: set `CABLE Input` format to 24 bit, 48000 Hz when available.
- Recording tab: set `CABLE Output` format to 8 channels, 24 bit, 48000 Hz when available.
- Your real headphones or speakers should use a compatible sample rate, usually 48000 Hz.

In Sound Radar:

- Input: `CABLE Output` or the equivalent Voicemeeter output.
- Output: your real headphones or speakers.
- Radar mode: Surround radar for 7.1, Stereo radar for stereo-only games.
- Start Sound Radar, then press `Test sound and radar`.

## Radar Options

Sound Radar can show the radar in two ways:

- Desktop overlay: best default for most games.
- Web radar: useful for a second monitor, browser capture, a phone, or games that do not like overlays.

For web radar, `0.0.0.0` is the recommended host. It listens on all local network interfaces, so the radar can be opened from this PC or another device on the same network.

The radar tab includes a point preview button. It animates colored dots across the radar so you can tune size, opacity, fade time, skin, and placement without running a game.

## Presets

Presets can store the settings that usually differ between games:

- radar mode
- mono/stereo mode
- gain and output boost
- DRC and Duck settings
- groups and colors
- sample rate and block size

Local presets live on your PC. Shared presets can be browsed from inside the app.

Sound Radar only shows presets that are compatible with the current app version. Older incompatible presets are hidden so outdated settings do not break a new setup.

## Troubleshooting

### No sound or no radar points

Use the setup guide or the Audio tab:

1. Select the virtual input device.
2. Select your real output device.
3. Start Sound Radar.
4. Press `Test sound and radar`.
5. Confirm that you hear sound and see radar points.

If that fails, try `Find working device pair`. It tests many possible input/output pairs and lets you confirm the one that actually works.

### Invalid sample rate or stream open errors

PortAudio errors can be misleading. An "invalid sample rate" can also mean the selected device cannot open the requested channel layout.

Check:

- VB-Cable or Voicemeeter is configured as 7.1/8-channel when using Surround radar.
- Input and output devices support the selected sample rate.
- WASAPI variants are selected when possible.
- Stereo radar is selected for stereo-only games/devices.

### SteelSeries Sonar or other virtual audio stacks

Some virtual audio stacks can conflict with VB-Cable. If the route looks correct but no sound or points appear, try disabling extra virtual devices or use Voicemeeter Banana as the routing layer.

## Settings And Files

User settings are stored in:

```text
%APPDATA%\SoundRadar
```

The app includes buttons to open the settings folder, reset settings, create a diagnostic report, and open the report folder.

Localization files live next to the installed executable:

```text
locales\en.json
locales\uk.json
```

You can add another translation by copying one of these files and translating the values.

## Links

- [GitHub repository](https://github.com/dmytro-kahitin/Sound-Radar)
- [Reddit community](https://www.reddit.com/r/SoundRadar/)

## License

Sound Radar is released under the [Apache License 2.0](LICENSE).
