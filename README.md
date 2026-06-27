# Spark Homes Repair Cost Estimator

A mobile-first Progressive Web App (PWA) built for the **Spark Homes Developer Contest**. The application helps acquisition agents estimate renovation costs while walking through residential properties by organizing repairs, calculating costs, capturing photos, and exporting a complete estimate package.

---

## Live Demo

🌐 **https://spark-homes-repair-cost-estimator.vercel.app/**

---

## GitHub Repository

**https://github.com/kinturkt/Spark-Homes-Repair-Cost-Estimator**

---

# Features

* Mobile-first responsive interface
* Progressive Web App (PWA)
* Offline support using Service Worker
* Multiple property project management
* 75+ repair line items
* 19 collapsible repair groups
* Adjustable room instances
* Progress tracking
* Per-project and global price overrides
* Custom repair items
* Project notes
* Photo capture and management
* ZIP export with Excel cost breakdown
* Deal Analyzer (Creative Feature)
* Local persistence using browser localStorage

---

# Project Structure

```text
.
├── index.html
├── sw.js
├── manifest.webmanifest
└── README.md
```

### index.html

Main application containing the UI, repair estimation logic, project management, pricing, exports, photo handling, and persistence.

### sw.js

Caches application assets to provide offline functionality after the application has been loaded once.

### manifest.webmanifest

Provides installable PWA support, application metadata, icons, display mode, and theme colors.

### README.md

Project documentation.

---

# Technology Stack

* HTML5
* CSS3
* Vanilla JavaScript (ES6)
* localStorage
* Service Workers
* Web App Manifest (PWA)

No frontend frameworks or backend services are required.

---

# Running the Application

## Option 1 (Recommended)

Open the hosted application:

https://spark-homes-repair-cost-estimator.vercel.app/

---

## Option 2 (Run Locally)

Clone or download the repository.

Run a local web server:

```bash
python -m http.server 8000
```

Open:

```text
http://localhost:8000
```

Using a local web server enables full PWA functionality including Service Workers.

---

# Core Functionality

## Project Management

* Create multiple projects
* Save project-specific repair estimates
* Switch between projects
* Store rooms, notes, pricing overrides, and photos

## Repair Estimation

* 75+ repair items
* Running repair total
* Quantity-based calculations
* Unit cost overrides
* Custom repair items
* Remove repair items
* "No Action Needed" workflow

## Adjustable Rooms

Supports configurable room instances including:

* Bathroom
* Bedroom
* Kitchen
* Interior / General
* Systems & Structure
* Exterior
* Living / Common Areas

## Photo Capture

* Camera support
* Image gallery
* Photo deletion
* Photos included in exported estimate

## Export

Exports a ZIP package containing:

* Excel repair estimate
* Project photos

---

# Creative Feature

### Deal Analyzer

The application includes a Deal Analyzer that estimates a Maximum Allowable Offer (MAO) using:

* After Repair Value (ARV)
* Repair costs
* Holding costs
* Target profit margin

This provides acquisition agents with immediate insight into whether a property represents a viable investment opportunity.

---

# Browser Support

Tested for:

* Chrome (Android)
* Safari (iOS)
* Chrome Desktop
* Safari Desktop

---

# Known Limitations

* Data is stored locally using browser localStorage.
* Projects are not synchronized across devices.
* Large image collections may consume browser storage.
* Full offline functionality requires HTTPS or localhost.
* No backend authentication or cloud synchronization.

---

# Future Improvements

Given additional development time, planned enhancements include:

* Cloud synchronization
* OCR for HVAC and appliance serial numbers
* Contractor scope-of-work generation
* Advanced project comparison
* Improved reporting dashboard
* Enhanced photo compression
* Validation before export

---

# AI Usage

AI tools were used during planning, UI refinement, debugging, documentation, and validation against the project requirements.

All implementation decisions, testing, and final verification were completed manually.

---

# License

This project was created solely for the Spark Homes Developer Contest.

Please do not redistribute the original contest materials or pricing data contained in the contest package.
