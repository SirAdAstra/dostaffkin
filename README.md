# 🚚 Dostaffkin — Delivery Service Web App

A modern, responsive multi-page delivery calculator and tracking web application built with **Angular 21 (Standalone Components, Signals)** with **Leaflet**, **OpenStreetMap** and the **Geoapify API**. It allows users to calculate delivery routes and costs interactively based on distance, size, and speed preferences, place orders via a REST API, and track delivery status in real time.

![status](https://img.shields.io/badge/status-active-brightgreen)
![license](https://img.shields.io/badge/license-MIT-blue)
![Angular](https://img.shields.io/badge/Angular-21-DD0031?style=flat&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat&logo=typescript&logoColor=white)
![Leaflet](https://img.shields.io/badge/Leaflet-1.9-199900?style=flat&logo=leaflet&logoColor=white)
![OpenStreetMap](https://img.shields.io/badge/Map-OpenStreetMap-7EBC6F?style=flat&logo=openstreetmap&logoColor=white)
![Geoapify](https://img.shields.io/badge/API-Geoapify-4A90E2?style=flat)

**[▶ Live Demo](https://siradastra.github.io/dostaffkin/)**

> 🚧 **Migration in progress:** the map, address suggestions and routing are moving from Yandex Maps to Leaflet + OpenStreetMap + Geoapify. This README already describes the new stack; the code and the live demo still use Yandex Maps until the migration is finished.

## ✨ Features

- **Interactive Route & Cost Calculation:** Renders the map with Leaflet and OpenStreetMap tiles, uses Geoapify Address Autocomplete for address suggestions and Geoapify Routing API to build the route and compute exact delivery distance, estimated time, and cost based on package size and delivery speed.
- **Dynamic Pricing & Speed Tiers:** Custom pricing tiers (from XS to Max) with configurable rates and express delivery multipliers (`+15%` cost, `-30%` delivery time).
- **Order Placement & Management:** Reactive forms with validation for customer details and backend integration with automated error handling via RxJS.
- **Real-time Order Tracking:** Dedicated tracking page allowing users to query shipment status using order ID numbers.
- **Modern Angular Architecture:** Built entirely with Angular standalone components, reactive signals (`signal()`), and modern dependency injection.
- **Responsive Layout:** Adaptive styling optimized for desktop, tablet, and mobile screens.

## 🛠️ Tech Stack

- **Framework:** [Angular 21](https://angular.dev/) (Standalone Components, Signals, Reactive Forms)
- **Language:** TypeScript 5.9
- **Routing & Networking:** Angular Router, HttpClient with RxJS (`catchError`, `Observable`)
- **Styling:** CSS3, Flexbox/Grid, Responsive Media Queries
- **Maps:** Leaflet (`L.map`, `L.tileLayer`, `L.geoJSON`) with OpenStreetMap tiles
- **APIs:** Geoapify Address Autocomplete API, Geoapify Routing API, Testologia REST API

## 🌐 APIs Used

| Purpose | Provider | Auth |
|---|---|---|
| Map rendering | [Leaflet](https://leafletjs.com/) + [OpenStreetMap](https://www.openstreetmap.org/) tiles | None |
| Address suggestions | [Geoapify Address Autocomplete API](https://www.geoapify.com/address-autocomplete/) | API key (free plan) |
| Route distance & geometry | [Geoapify Routing API](https://apidocs.geoapify.com/docs/routing/) | API key (free plan) |
| Backend order creation & tracking info | [Testologia REST API](https://testologia.ru/) | None (Public Test Endpoint) |

## 📁 Project Structure

```
dostaffkin-main/
├── src/
│   ├── app/
│   │   ├── header/               # Shared navigation header component
│   │   ├── pages/
│   │   │   ├── home/             # Landing / welcome page
│   │   │   ├── order/            # Calculator, map view, and order form
│   │   │   └── track/            # Shipment tracking page
│   │   ├── services/
│   │   │   ├── delivery-api.ts   # HTTP client wrapper for backend calls
│   │   │   └── geoapify-api.ts   # Address autocomplete & routing requests
│   │   ├── maps.config.ts        # Map settings & Geoapify API key
│   │   ├── app.config.ts         # Global app configuration (HttpClient, Router)
│   │   ├── app.routes.ts         # Application route definitions
│   │   └── app.ts                # Root standalone component
│   ├── styles.css                # Global styles & design system variables
│   └── index.html                # App entry point
├── angular.json                  # Angular CLI build & deployment settings
└── package.json                  # Dependencies & npm scripts
```

## 🚀 Getting Started

Prerequisites: Node.js (v20+ recommended) and npm.

```bash
# Clone the repository
git clone https://github.com/SirAdAstra/dostaffkin.git
cd dostaffkin

# Install dependencies
npm install

# Add your Geoapify API key to src/app/maps.config.ts
# (free key, no credit card: https://myprojects.geoapify.com)

# Start development server
npm start
```

Then open `http://localhost:4200` in your browser.

## 🗺️ Roadmap / TODO (Refactoring & Enhancements)

- [ ] **Custom Backend Integration:** Develop a dedicated custom backend service (e.g., ASP.NET Core Web API) to handle order processing and shipment tracking, replacing the temporary test external API endpoint (`testologia.ru`).
- [ ] **State Management & Services:** Extract route calculation and pricing logic out of `Order` component into a dedicated `PricingService` for better separation of concerns.
- [ ] **Reactive Forms Enhancement:** Add robust custom validators for phone numbers and email formats in `orderForm`.
- [ ] **Error Handling & Feedback:** Replace browser native `alert()` calls with a clean toast notification service or inline error state banners.
- [ ] **Loading States & Skeletons:** Implement loading spinners / skeleton loaders during map initialization, route calculation, and API requests.
- [ ] **TypeScript Strictness:** Remove `any` types across components and replace them with strict interface definitions for API payloads, routes, and responses.
- [ ] **Unit Testing:** Add comprehensive unit tests with Vitest for services and components (`delivery-api.spec.ts`, `order.spec.ts`).

## 🙏 Credits

- Map library: [Leaflet](https://leafletjs.com/)
- Map data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright)
- Address autocomplete and routing by [Geoapify](https://www.geoapify.com/)
- Training & Intensive by [Itlogia](https://itlogia.ru/)

## 📄 License

This project is licensed under the MIT License.

## 👤 Author

**Alexandr Cojuhari**
- [GitHub](https://github.com/SirAdAstra)
- [LinkedIn](www.linkedin.com/in/siradastra)
