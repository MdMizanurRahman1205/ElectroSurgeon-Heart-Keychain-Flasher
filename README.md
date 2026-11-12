# ElectroSurgeon-Heart-Keychain-Flasher link: https://mdmizanurrahman1205.github.io/ElectroSurgeon-Heart-Keychain-Flasher/

ElectroSurgeon 12-LED Heart Keychain Web Flasher
Files
`index.html` — ElectroSurgeon branded browser installer page
`manifest.json` — ESP Web Tools manifest for ESP8266
`firmware/heart-keychain.bin` — add your compiled firmware binary here
Important: add the firmware binary
The `.ino` source code cannot be flashed directly by ESP Web Tools.
Open the Heart Keychain sketch in Arduino IDE.
Select LOLIN(WEMOS) D1 R2 & mini (ESP8266 board package).
Confirm the sketch's pin definitions match your physical wiring.
Use Sketch > Export compiled Binary.
Copy the generated `.bin` into this folder as:
`firmware/heart-keychain.bin`
Keep the filename and folder path exactly as shown. The manifest flashes this ESP8266 image at offset `0x000000`.
Use the binary generated for the exact board/flash settings you intend to support. Do not use an ESP32 binary.
Test locally
ESP Web Tools requires HTTPS or localhost. For local testing, serve this folder from `http://localhost` using a local development server and open it in Chrome or Edge.
Publish with GitHub Pages
Create a GitHub repository, for example `electrosurgeon-heart-keychain`.
Upload `index.html`, `manifest.json`, and the `firmware/` folder containing `heart-keychain.bin`.
In repository Settings > Pages, deploy from the `main` branch and root folder.
Open the HTTPS GitHub Pages URL and test the installer with a USB-connected D1 Mini.
Device Wi-Fi after flashing
SSID: `ElectroSurgeon_KEYChain`
Password: `Electro123`
Dashboard: `http://192.168.4.1`
Browser / cable
Use desktop Google Chrome or Microsoft Edge and a USB data cable. Web Serial is not supported in iOS browsers.
Wiring note to verify before compiling
Your pasted sketch currently defines:
`LED_PIN D4`
`BUTTON_PIN D5`
But the header comments say Data D5 and Button D4. The `#define` lines are what the firmware actually uses. Make the code and physical wiring agree before exporting the binary.
