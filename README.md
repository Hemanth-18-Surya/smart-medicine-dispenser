# Smart Medicine Dispenser

An ESP32-based medicine reminder with three compartments. At the scheduled time, it lights an LED, sounds a buzzer, and opens the correct box with a servo. An IR sensor detects whether the medicine was taken, and the result appears on the LCD and a web dashboard.

## Features

- 3 independent medicine boxes with separate schedules
- NTP internet time sync (IST, UTC+5:30)
- Servo lids open for 15 seconds
- Buzzer, LED and LCD alerts
- IR detection of Taken / Missed
- Web dashboard to set times and view live status
- Daily status reset at midnight

## Hardware

ESP32, 16x2 LCD, 3 servos, 3 IR sensors, 3 LEDs, buzzer.

## Pin Connections

| Component | GPIO |
|-----------|------|
| LCD RS, EN | 15, 2 |
| LCD D4-D7 | 4, 16, 17, 5 |
| LEDs | 23, 21, 22 |
| IR sensors | 19, 18, 26 |
| Servos | 32, 33, 25 |
| Buzzer | 27 |

## Setup

1. Install Arduino IDE with ESP32 support and the `ESP32Servo` library.
2. Open `smart_medicine_dispenser.ino`.
3. Enter your Wi-Fi details:
   ```cpp
   #define WIFI_SSID     "YOUR_WIFI_NAME"
   #define WIFI_PASSWORD "YOUR_PASSWORD"
   ```
4. Upload to the ESP32. The LCD shows its IP address.

## Usage

Open the IP address in a browser on the same network, choose a time for each box, and press **Set Time**.

## Future Improvements

- Save reminders in flash memory
- Repeat reminders for missed doses
- Caregiver notifications

## License

MIT
