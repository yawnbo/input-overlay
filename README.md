# Input-Overlay

A input overlay for OBS and other broadcast software.

> [!NOTE]  
> hello, this project is pretty much just something i made for myself and a few friends,.. im going to try to fix bug etc as best as i can but keep in mind that im not that skilled of a dev so expect updates to roll out slowly or eventually to stop due to lack of time

## Features

- **WebSocket connection with authentication** with support to stream your inputs to a secondary PC (for example a dedicated streaming PC)
- **Hall effect keyboard support** via the [AnalogSense SDK](https://github.com/AnalogSense/JavaScript-SDK) ported to py
  <details>
  <summary>Keyboards/Devices</summary>

  - Everything by Wooting
  - Everything by NuPhy
  - Everything by DrunkDeer
  - Razer Huntsman V2 Analog<sup>R</sup>
  - Razer Huntsman Mini Analog<sup>R</sup>
  - Razer Huntsman V3 Pro<sup>R</sup>
  - Razer Huntsman V3 Pro Mini<sup>R</sup>
  - Razer Huntsman V3 Pro Tenkeyless<sup>R</sup>
  - Keychron Q1 HE<sup>P, F</sup>
  - Keychron Q3 HE<sup>P, F</sup>
  - Keychron Q5 HE<sup>P, F</sup>
  - Keychron K2 HE<sup>P, F</sup>
  - Lemokey P1 HE<sup>P, F</sup>
  - Madlions MAD60HE<sup>P</sup>
  - Madlions MAD68HE<sup>P</sup>
  - Madlions MAD68R<sup>P</sup>
  - Redragon K709HE<sup>P</sup>

  <sup>R</sup> Razer Synapse needs to be installed and running for analogue inputs to be received from this keyboard.  
  <sup>P</sup> The official firmware only supports polling, which can lead to lag and missed inputs.  
  <sup>F</sup> [Custom firmware with full analog report functionality is available](https://analogsense.org/firmware/).

  **Tested devices:**
  - Wooting 60HE
  - Redragon K709HE

  All other devices are theoretical and have not been tested. If you have a one of these devices and it works please open a pr to update the readme (or if its brokey open an issue or pr with the fix)
  </details>
- **Customizable layouts and lables** (lables support html img src tags although not officialy)

<table>
  <tr>
    <td><img src="https://files.catbox.moe/qzqhnc.avif" width="400"/></td>
    <td><img src="https://femboy.beauty/MKZmJt.png" width="400"/></td>
  </tr>
</table>

## Single PC Setup
 
1. Get the [input-overlay-ws](https://github.com/girlglock/input-overlay/releases) server
2. Run it and right click the tray icon to open the settings
3. Copy your auth token
 
   > **Tip:** You can change the token to whatever you like
 
4. Paste the token in the auth token field above
5. Configure your overlay to your liking, then click the `⎘ Copy URL` button and paste the copied URL as an OBS browser source
 
> **Tip:** You can configure the key whitelist in the server settings to ensure you are only sending keys over your network that are configured in the overlay
 
## Sending Keys to Another PC
 
> e.g. from a gaming PC to a streaming PC
 
1. Edit `config.json` to set the address/port of your gaming PC
 
   > Run `ipconfig` in cmd and copy the local IPv4 address (usually `192.168.0.1` or `192.168.X.X` with X being 0–255)
 
2. Enter the gaming PC's address in both the **input-overlay-ws** and **configurator**
3. Download the overlay as a local HTML file and add it as a browser source in OBS on your streaming PC instead of copying the URL