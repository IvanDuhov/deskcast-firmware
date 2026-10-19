# Deskcast firmware

Signed firmware releases for **[Deskcast](https://deskcast.app)**, an LED desk
display that shows one stock, ETF or crypto ticker live: the price, the day's
move in green or red, and the intraday chart. It sits beside your monitor, so
checking a price takes a glance instead of opening an app.

- **[deskcast.app](https://deskcast.app)**: what it is, specifications, FAQ and
  the waitlist
- [Stock ticker display](https://deskcast.app/stock-ticker-display) ·
  [Crypto price display](https://deskcast.app/crypto-ticker-display)
- [Setup and support](https://deskcast.app/support)
- Coming from a Tidbyt? [Deskcast as a Tidbyt alternative](https://deskcast.app/tidbyt-alternative)

## What's here

Only the [releases](https://github.com/IvanDuhov/deskcast-firmware/releases):
each `v<version>` has exactly two files.

| File | What it is |
|---|---|
| `esp32s3.ino.bin` | The firmware image for the ESP32-S3 inside the panel |
| `esp32s3.ino.bin.sig` | Its Ed25519 signature |

A Deskcast updates itself over the air. It downloads both files, checks the
signature against the public key built into it, and refuses anything that
doesn't verify or that is older than what it's running. A build that can't
reach the Deskcast service after installing rolls itself back to the
previous one. You never need to flash these by hand.

The source code isn't public.

## Hardware

- 128 × 64 RGB LED panel, 256 × 128 mm, 2 mm pitch, readable from 40 cm to 4 m
- ESP32-S3 with 16 MB flash and 8 MB PSRAM, 2.4 GHz Wi-Fi, USB-C power
- Set up from a phone over the panel's own Wi-Fi network; no app to install

Deskcast only shows prices. It doesn't connect to a broker, exchange or
wallet, and market data may be delayed; it isn't investment advice.

Follow along: [Instagram](https://www.instagram.com/deskcast.app) ·
[TikTok](https://www.tiktok.com/@deskcast.app)
