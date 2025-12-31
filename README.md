# 📟 ESP32 Simon Game — FreeRTOS, RFID Profiles, LCD, RTC


**Link to demo:** [Watch on YouTube](https://www.youtube.com/watch?v=-iWkOZgTMfk)

<img width="1284" height="895" alt="image" src="https://github.com/user-attachments/assets/cc7e272e-7efc-4f7f-a301-5cff1dca22e9" />

<br>

A feature-rich Simon memory game built on the ESP32-S3, using FreeRTOS multitasking, RFID player profiles, LCD UI, persistent high scores, and real-time timestamps.

*This project was built as a final embedded systems project by **Easton Anderson** and **Muhammad Rahman**.*

---

## 🎮 Features

### 🧠 Classic Simon Game
* Randomly generated pattern up to 32 levels
* LED + buzzer tone feedback
* Real-time validation of player input

### 👤 RFID Player Profiles
* Tap an RFID tag to load a profile
* **Stores:**
  * Player ID
  * High score
  * Timestamp of best performance
* Supports default local profile

### 🕒 Real-Time Clock (RTC) Support
* Time-stamps high scores using DS3231 RTC
* Displays last high score date/time on LCD

### 💾 Persistent Storage
* Uses Preferences (NVS) to permanently store:
  * High scores
  * Timestamps
  * Per-player data

### 🔊 Audio & LED Effects
* Startup intro song
* Scan-in stingers
* High-score celebration animation
* Game over jingle + flash
* Pattern playback sounds

### ⚙️ FreeRTOS Multicore Architecture
* **Core 0** → Button input + debouncing
* **Core 1** → Game logic, UI, animations
* Queue-based communication using `xQueueSend` / `xQueueReceive`

---

## 🧱 Hardware Used

| Component | Purpose |
| :--- | :--- |
| **ESP32-S3** | Main microcontroller with FreeRTOS support |
| **4 LEDs** | Simon game buttons |
| **4 Push Buttons** | Player input (active-low, pull-up) |
| **Piezo Buzzer** | Tone feedback |
| **I2C 16×2 LCD** | UI / menu display |
| **MFRC522 RFID Reader** | Player ID scanning |
| **DS3231 RTC** | Timestamping high scores |

---

## 📁 Project Structure

```text
simon-game-esp32-freertos/
│
├── SimonGame.ino        # Main sketch (fully commented)
├── README.md            # Project documentation
└── /media               # (Optional) Photos, demo GIFs
