<p align="center">
  <a href="https://deskcast.app"><img src="assets/hero.jpg" alt="Deskcast on a desk showing SPY: live price, day move, high and low, and the intraday chart" width="100%"></a>
</p>

<h1 align="center">Deskcast</h1>

<p align="center">
  <b>The market, on your desk.</b><br>
  A live LED display for your stocks, crypto and broker portfolio.<br>
  Check a price with a glance, not your phone.
</p>

<p align="center">
  <a href="https://deskcast.app"><img alt="Join the waitlist" src="https://img.shields.io/badge/Join_the_waitlist-deskcast.app-22c55e?style=for-the-badge"></a>
</p>

<p align="center">
  <a href="https://github.com/IvanDuhov/deskcast-firmware/releases/latest"><img alt="Latest firmware" src="https://img.shields.io/github/v/release/IvanDuhov/deskcast-firmware?label=firmware&color=3b82f6"></a>
  <img alt="Signed with Ed25519" src="https://img.shields.io/badge/updates-signed_%C2%B7_Ed25519-8b5cf6">
  <img alt="ESP32-S3" src="https://img.shields.io/badge/ESP32--S3-16MB_%C2%B7_8MB_PSRAM-e7352c">
  <img alt="128 x 64 RGB LEDs" src="https://img.shields.io/badge/LEDs-128_%C3%97_64_RGB-f59e0b">
  <a href="https://www.instagram.com/deskcast.app"><img alt="Instagram" src="https://img.shields.io/badge/Instagram-@deskcast.app-e1306c?logo=instagram&logoColor=white"></a>
  <a href="https://www.tiktok.com/@deskcast.app"><img alt="TikTok" src="https://img.shields.io/badge/TikTok-@deskcast.app-000000?logo=tiktok&logoColor=white"></a>
</p>

---

## The screens

It rotates through the screens you turn on. Every one below is filmed on the
real prototype.

<table>
  <tr>
    <td width="50%" valign="top">
      <img src="assets/price.gif" alt="Price screen: SPY price ticking up with the intraday chart" width="100%"><br>
      <b>📈 Live price</b><br>
      Price, day move, high and low, the intraday chart and a countdown to the next bell.
    </td>
    <td width="50%" valign="top">
      <img src="assets/heatmap.gif" alt="Heat map: eight watchlist tiles in green and red" width="100%"><br>
      <b>🟩 Heat map</b><br>
      Your watchlist as tiles that glow with the day's move.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="assets/portfolio.gif" alt="Portfolio screen: IBKR positions and today's gain" width="100%"><br>
      <b>💼 Your portfolio</b><br>
      Your account's value, today's move and every position, page by page.
    </td>
    <td width="50%" valign="top">
      <img src="assets/news.gif" alt="News screen: a headline card about one of your symbols" width="100%"><br>
      <b>📰 Headlines</b><br>
      News about your symbols as cards. A chime when a new one lands, and the
      built-in speaker can read it out loud.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img src="assets/premarket.gif" alt="Pre-market: the price with a small sun before the open" width="100%"><br>
      <b>🌅 Pre-market and after-hours</b><br>
      From 4:00 New York time. A small sun before the open, a moon after the close.
    </td>
    <td width="50%" valign="top">
      <img src="assets/indices.jpg" alt="Indices screen: Nasdaq, VIX and the 10-year yield with their charts" width="100%"><br>
      <b>🪙 Indices and crypto</b><br>
      The Nasdaq, the VIX and yields side by side. Bitcoin, Ethereum or any coin, around the clock.
    </td>
  </tr>
</table>

## Your broker, on the panel

<img src="assets/portfolio-desk.jpg" alt="Deskcast at night showing Interactive Brokers positions" align="right" width="45%">

Connect **Trading 212**, **eToro** or **Interactive Brokers** with a read-only
key. Deskcast shows what your account is worth, how today went, and every
position with its weight and move.

- 🔒 **Read-only.** It can never place an order.
- 🗝️ Keys are stored encrypted and deleted when you disconnect.
- 🙈 Hide the amounts and show only percentages.

Missing a broker you use? Founding customers choose the next integration.

<br clear="right">

## Built to sit on your desk

<p>
  <img src="assets/heatmap-desk.jpg" alt="Deskcast on a wooden desk at night showing the heat map" width="49%">
  <img src="assets/desk.jpg" alt="The Deskcast prototype next to a laptop, showing MU" width="49%">
</p>

|  |  |
|---|---|
| **Display** | 128 × 64 RGB LEDs, 2 mm pitch |
| **Size** | 256 × 128 mm, readable from 40 cm to 4 m |
| **Brains** | ESP32-S3, 16 MB flash, 8 MB PSRAM |
| **Connectivity** | 2.4 GHz Wi-Fi, USB-C power |
| **Sound** | Speaker for headline chimes and read-aloud news |
| **Setup** | From your phone, over the panel's own Wi-Fi. No app to install. |
| **Refresh** | Every 15 seconds up to once an hour, your choice |
| **Updates** | Signed, over the air, with two firmware slots |

Designed and assembled by hand in Bulgaria. 🇧🇬

## It keeps itself up to date

This repo is where your Deskcast gets its updates. Each release ships two files
and nothing else:

| File | What it is |
|---|---|
| `esp32s3.ino.bin` | The firmware image for the ESP32-S3 inside the panel |
| `esp32s3.ino.bin.sig` | Its Ed25519 signature |

```mermaid
flowchart LR
    A["New release<br/>.bin + .sig"] --> B{"Signature valid?<br/>Newer version?"}
    B -- no --> X["Rejected,<br/>keeps running"]
    B -- yes --> C["Installed to<br/>the spare slot"]
    C --> D{"Reaches Deskcast<br/>after reboot?"}
    D -- yes --> E["✅ Running the<br/>new version"]
    D -- no --> F["↩️ Rolls back to<br/>the previous build"]
```

The device checks every download against the public key built into it, and
refuses anything that doesn't verify or is older than what it runs. You never
need to flash these by hand. The source code isn't public.

## Get one

The first 50 units are a founding batch, and those 50 never pay a subscription.
**[Join the waitlist on deskcast.app →](https://deskcast.app)**

- [Stock ticker display](https://deskcast.app/stock-ticker-display) ·
  [Crypto price display](https://deskcast.app/crypto-ticker-display) ·
  [Coming from a Tidbyt?](https://deskcast.app/tidbyt-alternative)
- [Setup and support](https://deskcast.app/support)
- Follow the build: [Instagram](https://www.instagram.com/deskcast.app) ·
  [TikTok](https://www.tiktok.com/@deskcast.app)

---

<sub>Every screen shown is the real prototype; some backgrounds are staged.
Deskcast only shows prices. It doesn't trade, market data may be delayed, and
nothing on it is investment advice. Ticker symbols belong to their respective
owners.</sub>
