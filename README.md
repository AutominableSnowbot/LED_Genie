# LED Genie

A tiny static PWA for controlling an **SP110E / LED Hue** Bluetooth LED pixel controller from a browser with Web Bluetooth.

## Supported browsers

- Works best in Android Chrome, desktop Chrome, or desktop Edge.
- Web Bluetooth is not supported in iPhone Safari or Firefox.

## Controls

- Connect/disconnect over BLE
- On/off
- Touch-friendly colour wheel, native color picker, and quick swatches
- Brightness
- Named pattern preset browser with animated offline preview, category filter, dropdown, previous/next buttons, and speed slider

## SP110E protocol used

- Service: `ffe0`
- Init characteristic: `ffe2` when present; some SP110E BLE variants expose only `ffe1`
- Write characteristic: `ffe1`
- Init writes: `01 00` to `ffe2` if available, then `01 b7 e3 d5` to `ffe1`
- The app logs discovered characteristics during connect to help identify firmware variants
- Commands:
  - On: `fa 0e c7 aa`
  - Off: `b0 4f c2 ab`
  - Color: `RR GG BB 1e`
  - Brightness: `VV ed 29 2a`
  - Preset: `VV 09 fa 2c`
  - Speed: `VV 10 34 03`

## Deploy

This is a no-build app. Serve the repository root over HTTPS. GitHub Pages URL should be:

<https://autominablesnowbot.github.io/LED_Genie/>
