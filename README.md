# EduRide

A safe, student-focused ride-hailing web app prototype for campus commutes, inspired by inDrive. Riders name their own fare, drivers send offers, and everyone can choose between private, female-only, and shared rides, both inside a city and between cities.

> **Status:** interactive demo. Drivers, offers, maps, and payments are simulated in the browser. There is no backend yet.

## Features

**Rider**
- Onboarding with name, university email, ID card upload, and role selection
- In-city and city-to-city booking (10 Pakistani cities, distance from real coordinates)
- Three ride types: **Solo**, **Female-only**, **Share ride** (split the fare, about 38% cheaper per seat)
- inDrive-style fare: set your own offer, then pick from driver counter-offers
- Payment method: Cash, JazzCash, Easypaisa, Debit/Credit card
- Live tracking with ETA, driver details, and a 4-digit ride PIN
- Cancellation policy (free within 2 minutes, Rs. 50 fee after)
- Safety: SOS (Police 15, Rescue 1122) and Share live trip
- Driver rating and trip summary

**Driver** (separate green interface)
- Go online or offline
- Incoming ride requests with rider, route, ride type, payment method, and fare
- Accept, counter-offer (+Rs. 20 in city, +Rs. 100 city to city), or decline
- PIN verification at pickup, then ride progress
- Earnings and trip counter (10% platform fee)

## Quick start

No install or build step. Everything is in one file.

1. Open `index.html` in Chrome or Safari, **or** host it (see below).
2. Register as **Rider** or **Driver**. Any name, a valid-looking email, and any image for the ID card will work.
3. Use the **Driver view / Rider view** button at the top to switch sides while testing.

**Demo driver PIN:** `1234`

> Open the page from a web link or a browser. Opening the file from WhatsApp or a file-manager preview will not run it.

## Deploy on GitHub Pages (free)

1. Create a **Public** repository named `eduride` on GitHub.
2. Upload `index.html` (**Add file → Upload files**) and commit.
3. Go to **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After 1 to 2 minutes the app is live at `https://YOUR-USERNAME.github.io/eduride/`.

## QR code for a stall or poster

`eduride-qr.html` generates a printable "Scan to try EduRide" poster. Paste your live app link into the **App link** box and the QR code updates instantly. Use **Print this poster** to print it. This page needs internet access to build the QR code.

## Project files

| File | Purpose |
|---|---|
| `index.html` | The complete EduRide app (HTML, CSS, and JavaScript in one file) |
| `eduride-qr.html` | Printable QR code poster that links to the app |
| `README.md` | This file |

## Tech

- Plain HTML, CSS, and vanilla JavaScript, no frameworks
- Inline SVG maps (no map tiles, so the app works as a single self-contained file)
- `localStorage` for the signed-in profile
- Optional Google Fonts (Plus Jakarta Sans), with a system-font fallback
- Light and dark mode via `prefers-color-scheme`

## Known limitations

- **Simulated data:** drivers, ride requests, and offers are generated randomly in the browser. A rider's booking does not reach a real driver.
- **Schematic maps:** routes are drawn on an SVG map, not on real streets. No GPS.
- **Demo payments:** wallet and card payments are not connected to any provider.
- **ID check:** the uploaded ID card is not verified or stored.
- **No accounts:** the profile lives only in the browser it was created in.

## Roadmap to a production app

1. **Backend and database:** Firebase or Supabase for users, drivers, rides, and real-time updates
2. **Real maps and GPS:** Google Maps or Mapbox for routing, live location, and geocoding
3. **Matching:** send ride requests to nearby online drivers and handle counter-offers in real time
4. **Payments:** JazzCash, Easypaisa, and card gateway integration
5. **Verification:** real ID and driver document review, vehicle details, and background checks
6. **Notifications:** push notifications for offers, arrival, and trip status
7. **Native apps:** React Native or Flutter versions for Android and iOS
8. **Safety:** real emergency-contact sharing, trip recording, and an in-app support flow

## Safety note

SOS buttons in this demo do not place real calls. Before any real-world launch, safety features must be fully implemented and tested, and the service must comply with local transport and data-protection rules.
