# ✈️ Delta Price Tracker

**Automatically track Delta flight prices and get notified when they drop.**

---

## 📥 Download & Install

### [⬇️ Download Latest Version](../../releases/latest)

**Windows:**
1. Download **DeltaFlightTracker-Setup-Windows.exe**
2. Run the installer
3. Done! The app opens automatically and runs in your **system tray** (bottom-right, near the clock)

**Mac:**
1. Download and unzip **DeltaFlightTracker-Mac.zip**
2. Double-click `install_mac.command` (one-time setup, 2-5 min)
3. Double-click `run_mac.command` to start
4. Press `Ctrl+C` in Terminal to stop

> **Mac Note:** If macOS blocks the scripts, right-click → Open → Click "Open" in the dialog.

*No account needed. Runs entirely on your computer.*

---

## ✨ Features

- **Automatic price monitoring** – Checks prices daily (3-5 AM recommended)
- **Email alerts** – Get notified when prices drop
- **Screenshot proof** – Captures Delta.com as evidence of prices
- **Track what you paid** – Only alert when price drops below your purchase price
- **Claim savings** – Log actual savings when you rebook at lower prices
- **Price history** – See trends over time
- **Cash or Miles** – Track dollar prices or SkyMiles awards separately
- **Specific flight times** – Track exact departures (e.g., 8:03am)
- **Export/Import** – Backup your flight data as JSON
- **Runs in background** – Minimizes to system tray (Windows)
- **100% free** – No ads, no subscriptions

---

## 📖 How to Use

### Adding a Flight
1. Enter origin & destination airports (e.g., MSP → SJU)
2. Select your travel dates
3. Optionally specify exact departure time
4. Click **Add Flight**

### Setting Up Email Alerts
1. Go to **Settings**
2. Enter your Gmail and create an [App Password](https://myaccount.google.com/apppasswords)
3. Test and save

### Background Monitoring (Windows)
- Close the browser window – app keeps running in your system tray
- Right-click the tray icon to quit completely

### Background Monitoring (Mac)
- Keep the Terminal window open (can be minimized)
- Press `Ctrl+C` or close the Terminal to stop

---

## ⚙️ Settings

| Setting | Description |
|---------|-------------|
| **Daily Check Time** | When to automatically check prices (e.g., 3:00 AM) |
| **Alert Threshold** | Minimum price drop to trigger notification (e.g., $25) |
| **Headless Mode** | Run browser invisibly (recommended) |
| **Email Alerts** | Send price drops to your email (requires App Password) |

---

## 💾 Data Storage

Your data stays on your computer:

| Location | Windows | Mac |
|----------|---------|-----|
| **App Data** | `%LocalAppData%\DeltaFlightTracker\` | Same folder as app |
| **Database** | `flights.db` | `flights.db` |
| **Screenshots** | `screenshots/` | `screenshots/` |
| **Settings** | `settings.json` | `settings.json` |

---

## 🔧 Troubleshooting

<details>
<summary><strong>Windows: App won't start</strong></summary>

1. Look for the icon in your **system tray** (click the ^ arrow if hidden)
2. Run `Delta Flight Tracker - Reset Tool` from the Start Menu
3. Check `launcher.log` in the app folder for errors
</details>

<details>
<summary><strong>Windows: "Port already in use"</strong></summary>

The app is already running. Check your system tray, or run the Reset Tool.
</details>

<details>
<summary><strong>Mac: "Permission denied"</strong></summary>

```bash
chmod +x install_mac.command run_mac.command
```
</details>

<details>
<summary><strong>Mac: Scripts blocked by Gatekeeper</strong></summary>

Right-click the file → Open → Click "Open" in the security dialog.
</details>

<details>
<summary><strong>Price check fails</strong></summary>

- Make sure you have a stable internet connection
- Delta.com may have changed their layout (check for app updates)
- Try running with headless mode disabled to see what's happening
</details>

---

## ❓ FAQ

<details>
<summary><strong>Is it safe?</strong></summary>

Yes. The app runs 100% on your computer. No data is sent anywhere except to Delta.com (for price checks) and your email server (for alerts).
</details>

<details>
<summary><strong>Why is there an 8 flight limit?</strong></summary>

To avoid being detected as a bot by Delta, we limit how many flights you can track. Each flight is checked ~20 minutes apart, so 8 flights takes about 2.5 hours to check. You can archive completed trips to make room for new ones.
</details>

<details>
<summary><strong>Does it work when my computer is off?</strong></summary>

No. Your computer needs to be on and connected to the internet. The app can run minimized in your system tray (Windows) or Terminal (Mac).
</details>

<details>
<summary><strong>Why do I need a Google App Password?</strong></summary>

For security. App Passwords are separate from your main password and can be revoked anytime at [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords).
</details>

---

## 🛠️ Building from Source

<details>
<summary><strong>Windows</strong></summary>

1. Install [Python 3.11+](https://www.python.org/downloads/)
2. Install [Inno Setup](https://jrsoftware.org/isinfo.php)
3. Download [Python Embeddable](https://www.python.org/downloads/) (Windows x64 embeddable)
4. Extract to `BuildKit/python/`
5. Run `BUILD.bat`
6. Compile `DeltaFlightTracker.iss` with Inno Setup
</details>

<details>
<summary><strong>Mac</strong></summary>

```bash
# Clone the repo
git clone https://github.com/yourusername/delta-flight-tracker.git
cd delta-flight-tracker

# Install dependencies
pip3 install flask pillow playwright
python3 -m playwright install firefox

# Run
python3 -c "import web_ui; web_ui.init_db(); web_ui.app.run(port=5000)"
```
</details>

---

## 💝 Support

If this tool saves you money, consider buying me a coffee!

[![Cash App](https://img.shields.io/badge/Cash_App-$SteveVogt-00D632?style=for-the-badge)](https://cash.app/$SteveVogt)
[![PayPal](https://img.shields.io/badge/PayPal-SteveVogt-0070BA?style=for-the-badge)](https://paypal.me/SteveVogt)
[![Venmo](https://img.shields.io/badge/Venmo-SteveVogt-008CFF?style=for-the-badge)](https://venmo.com/u/SteveVogt)

<details>
<summary>Bitcoin</summary>

```
bc1qpdex8jrvyj3lh7q56av2k53nrh7u63s6t65uer
```
</details>

---

## 📬 Contact

**Developer:** Steve Vogt  
**Email:** steve@stevevogt.com  
**Issues:** [Report a bug](../../issues)

---

## 📜 License

MIT License - Use freely, modify freely.

---

## ⚠️ Disclaimer

This tool is for personal use only. It is not affiliated with, endorsed by, or connected to Delta Air Lines in any way. Use responsibly and in accordance with Delta's terms of service. Flight prices and availability are subject to change. Always verify prices on Delta.com before booking.

---

<p align="center">
  <sub>Version 2.4.1 • Made with ❤️ for travelers who hate overpaying for flights</sub>
</p>
