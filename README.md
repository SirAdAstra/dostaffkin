# 🚚 Dostaffkin — Delivery Service Web App

A modern, responsive multi-page delivery calculator and tracking web application built with **Angular 21 (Standalone Components, Signals)** and **Yandex Maps API**. It allows users to calculate delivery routes and costs interactively based on distance, size, and speed preferences, place orders via a REST API, and track delivery status in real time.

![status](https://img.shields.io/badge/status-active-brightgreen)
![license](https://img.shields.io/badge/license-MIT-blue)
![Angular](https://img.shields.io/badge/Angular-21-DD0031?style=flat&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat&logo=typescript&logoColor=white)
![Yandex Maps](https://img.shields.io/badge/API-Yandex_Maps-FFCC00?style=flat)

**[▶ Live Demo](https://siradastra.github.io/dostaffkin/)**

## ✨ Features

- **Interactive Route & Cost Calculation:** Integrates Yandex Maps API (`MultiRoute`) with address suggestions (`SuggestView`) to compute exact delivery distance, estimated time, and cost based on package size and delivery speed.
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
- **APIs & SDKs:** Yandex Maps JS API (`ymaps.Map`, `SuggestView`, `MultiRoute`), Testologia REST API

## 🌐 APIs Used

| Purpose | Provider | Auth |
|---|---|---|
| Map rendering, address suggestions, & routing | [Yandex Maps API](https://yandex.com/dev/maps/) | API Script / Script Ready |
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
│   │   │   └── delivery-api.ts   # HTTP client wrapper for backend calls
│   │   ├── app.config.ts         # Global app configuration (HttpClient, Router)
│   │   ├── app.routes.ts         # Application route definitions
│   │   └── app.ts                # Root standalone component
│   ├── styles.css                # Global styles & design system variables
│   └── index.html                # App entry point with Yandex Maps script
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

- Maps and Geocoding by [Yandex Maps API](https://yandex.com/dev/maps/)
- Training & Intensive by [Itlogia](https://itlogia.ru/)

## 📄 License

This project is licensed under the MIT License.

## 👤 Author

**Alexandr Cojuhari**
- [GitHub](https://github.com/SirAdAstra)
- [LinkedIn](www.linkedin.com/in/siradastra)
