# food_map 🗺️

Personal food/restaurant map for Hà Nội. Built and maintained by agent on behalf of C V (cuongvuong).

## What this is

A static web app showing a map of restaurants/eating places. Click a pin → see photo, address, rating, hours, price range, and a link to Google Maps.

## Tech

- `index.html` — the map UI (Leaflet.js + OpenStreetMap)
- `places.json` — restaurant database (all data lives here)
- `img/` — local photos (from user screenshots or scraped)

## Current restaurants (as of 2026-03-30)

| Name | Category | Area | Rating |
|---|---|---|---|
| XINU - Xiên Nướng Hoàng Cầu | Xiên nướng · Trung Quốc | Hoàng Cầu, Đống Đa | 4.3★ |
| A Báo Nướng Xiên Quê Trung Hoa | Xiên nướng · Trung Quốc | 285 Kim Mã, Ba Đình | 4.2★ |
| Thực Hương Lẩu · 蜀香楼 | Lẩu Tứ Xuyên · Trung Quốc | 83-85 Trung Hòa, Cầu Giấy | 4.1★ |
| Chả Cá Bảo Linh | Chả cá · Hải sản | An Dương, Tây Hồ | 4.5★ |

## How to update

The agent manages this repo. To add a restaurant:
- Send a screenshot of the restaurant (from Google Maps, Foody, Telegram, etc.) to the agent
- Agent will research it online (name, address, hours, price, rating) and add to `places.json`
- Agent will also grab an image and push to `img/`
- Agent commits and pushes to this repo

## `places.json` schema

```json
{
  "id": "unique-slug",
  "name": "Restaurant Name",
  "category": "Food type",
  "address": "Full address",
  "lat": 21.0247,
  "lng": 105.8297,
  "phone": "0xxx xxx xxx",
  "hours": "HH:MM – HH:MM",
  "price": "XXX,000 – YYY,000₫/người",
  "rating": 4.3,
  "review_count": 100,
  "tags": ["tag1", "tag2"],
  "note": "Short note about the place",
  "image": "img/filename.jpg",
  "maps_url": "https://maps.google.com/?q=..."
}
```

## Serving locally

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

Agent spins up a tunnel on demand (ask: "show me food map") — live for 15 minutes then auto-killed.
