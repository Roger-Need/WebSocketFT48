# WebSocket FT4/8 v1.0

WebSocket FT4/8 is a self-contained FT8 and FT4 decoder that runs entirely in a browser with no installation required. It connects to SDRplay's SDRconnect software via WebSocket and decodes FT8 and FT4 signals in real time. Select a band, adjust the audio level, and click Decode to begin. Decoded messages are displayed after each cycle and can be explored in a split window. A live spectrum and waterfall display the signal environment, and a station map plots decoded callsigns on a world map for the session.

## Features

- **FT8 and FT4 decoding**

  - Pure browser-based decoder — no external software or plugins required.

  - **FT8 / FT4** — switch between modes at any time. The current mode is shown on the button.

  - **Fast / Normal / Deep** — sets the decoder depth. Fast uses minimal CPU; Normal is the recommended default; Deep attempts more aggressive decoding at the cost of higher CPU usage.

  - **Country display** — optionally show the country alongside decoded callsigns. Three modes: Off, CQ (CQ messages only), or All (every decode).

- **Decode window**

  - Messages are displayed after each decode cycle showing UTC time, dB, DT, frequency, and message text.

  - **Left-click any message** — opens a split window showing all messages decoded on that frequency.

  - **Right-click any message** — opens the sender's QRZ page in a new tab. This works in both the main decode window and the split window.

  - **Clear** — clears the decoded messages list and map display.

- **Band selection**

  - Eleven amateur radio bands supported: 160m, 80m, 60m, 40m, 30m, 20m, 17m, 15m, 12m, 10m, and 6m.

  - Selecting a band resets the decoder and retunes SDRconnect to the correct frequency.

- **Band hopping**

  - Automatically cycles through up to 11 bands in sequence.

  - Each band can be configured individually with its own cycle time and FT8/FT4 mode.

  - When hopping is active, the Decode, Mode, and Band controls are locked.

  - The hopping modal shows current band, next hop, cycle position, and session decode totals.

  - Each band tracks its own decode, callsign, and country counts, with a Reset Stats button to clear them.

  - Your band hopping configuration is saved automatically and restored the next time you open the app.

- **Station map**

  - All decoded stations for the session are plotted on a world map.

  - Stations are located using their transmitted Maidenhead grid square when available, otherwise by country.

  - Map markers are colour-coded by band. Click any marker to see station details, including a QRZ button beside the callsign for resolved stations that opens the station's QRZ page in a new tab.

  - Zoom in and out using the mouse wheel. Pan by holding left-click and dragging.

  - The map resets when the decode panel is cleared, when disconnecting, or when changing bands.

- **Spectrum and waterfall**

  - Live spectrum display shows signal levels across the FT8/FT4 audio passband (0–3320 Hz).

  - Waterfall shows signal history over time, with stronger signals appearing brighter.

  - **Slow / Fast** — sets the waterfall scroll speed.

  - **Cumulative** — toggles frame averaging for a smoother spectrum display.

  - **Autoscale** — automatically adjusts the Min and Max dB levels to fit the current signal environment.

  - **Min / Max** — set the dB range of the colour scale manually using the input fields or ▲▼ buttons.

  - **Clear** — clears the spectrum and waterfall display.

- **Audio level and metering**

  - Volume slider and mute button control the audio output level.

  - Audio Meter shows the input signal level. Adjust the Audio Level so the meter shows green bars to mid-scale with no orange or red bars.

- **Filter bandwidth**

  - Sets the SDRconnect receiver filter bandwidth in Hz.

  - Adjustable by typing a value directly or using the ▲▼ step buttons (100 Hz steps, 0–3300 Hz).

- **AGC**

  - Enables or disables the Automatic Gain Control in SDRconnect.

  - The recommended setting is disabled (AGC Off).

- **Signal displays**

  - **S-Meter** — graphical signal strength display from S1 to S9+60 dB.

  - **Signal Power** — numeric signal power reading from SDRconnect.

  - **SNR** — signal-to-noise ratio.

  - **Frequency** — current VFO frequency as reported by SDRconnect.

- **WebSocket connection**

  - Connects to SDRplay's SDRconnect via WebSocket.

  - Default connection: 127.0.0.1 port 5454 (both configurable).

  - IP address field remembers previously entered addresses and shows them as a drop-down history.

## Requirements

- **SDRconnect** — SDRplay's SDRconnect software must be running on the same machine or local network with WebSocket access enabled.

- **Supported browsers** — Google Chrome, Microsoft Edge, or Firefox.

- **Accurate system clock** — for correct FT8/FT4 decoding your system clock must be synchronized to UTC within 1 second. Windows users should run a dedicated NTP sync tool such as Nettime or Dimension 4.

- **Internet connection required for the station map** — the map uses MapLibre GL and OpenFreeMap tiles, both loaded from the internet. All other features work without an internet connection.

- No installation and no server required.

## Typical Workflow

1. **Open WebSocket FT4/8** in your browser. Just double-click the file.

2. Enter the SDRconnect server IP address (default **127.0.0.1**) and port (default **5454**), then click **Connect**.

3. Adjust the **Audio Level** slider so the Audio Meter shows green bars to mid-scale with no orange or red bars.

4. Select a **Band** from the drop-down to tune SDRconnect to the correct frequency.

5. Click **Decode Off** to start decoding. The button turns green when active.

6. Decoded messages appear in the decode window after each cycle. Left-click any message to open the split window for that frequency.

7. Use **Country Off / CQ / All** to optionally display the country alongside decoded callsigns.

8. Click **Map** to open the station map and see decoded callsigns plotted on a world map.

9. To scan multiple bands automatically, click **Hop Off** to open the Band Hopping modal, configure your bands and cycle times, then enable hopping.

10. Adjust **Min** and **Max** or click **Autoscale** to optimise the spectrum and waterfall display for your signal environment.

## License

This program is free software: you can redistribute it and/or modify it under the terms of the **GNU General Public License** as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

You must:

- Keep the copyright and license header.

- Release any modifications or derivative works under GPLv3 (or later).

See [https://www.gnu.org/licenses/gpl-3.0.html](https://www.gnu.org/licenses/gpl-3.0.html) for the full license text.
