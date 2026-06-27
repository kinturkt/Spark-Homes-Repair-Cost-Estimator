# Spark Homes Repair Cost Estimator

## Overview

This project is a mobile-first repair cost estimator web app built for the Spark Homes Developer Contest.

The app is designed for acquisition agents who are walking through properties in the field and need a fast, structured way to estimate repair costs before submitting an offer. Agents can create property projects, add rooms, select repair items, enter quantities, override prices, attach photos, track completion, and export the estimate package.

## Live Demo

Paste hosted app link here:

```text
[Live demo URL]
```

## GitHub Repository

Paste repository link here:

```text
[GitHub repository URL]
```

## Files Included

The repository contains a small static file set:

```text
index.html
manifest.webmanifest
README.md
sw.js
```

### index.html

Main application file. It contains the mobile UI, repair estimator logic, project management, room management, pricing behavior, photo handling, localStorage persistence, progress tracking, and export workflow.

### sw.js

Service worker file used for offline support. It caches the app shell so the estimator can continue working after it has been loaded from a supported hosted environment.

### manifest.webmanifest

PWA manifest file used for installable app behavior, including app name, display mode, theme color, and mobile home screen support.

### README.md

Project documentation, setup notes, feature summary, and submission notes.

## How to Run Locally

No build step, server-side app, Node.js install, or dependency installation is required.

### Option 1: Open the app directly

1. Download or clone the repository.
2. Open `index.html` in a modern browser.
3. Use the app locally.

This is enough to review the main estimator features.

### Option 2: Test PWA and offline behavior locally

Some browsers restrict service workers when opening files directly from the file system. For better PWA testing, run the folder on localhost:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

For the final submitted version, the app should be tested from the hosted URL, such as GitHub Pages, because service workers work best on HTTPS or localhost.

## Suggested GitHub Pages Setup

1. Upload all files to the root of the GitHub repository.
2. Make sure `index.html`, `sw.js`, and `manifest.webmanifest` are not inside a nested folder.
3. Go to repository Settings.
4. Open Pages.
5. Select deployment from the main branch and root folder.
6. Copy the published GitHub Pages URL.
7. Test the URL on a phone before submitting.

## Technical Approach

The app is intentionally built as a static front-end application so it can run in the field without a backend dependency.

Key technical decisions:

- Vanilla JavaScript, HTML, and CSS
- Mobile-first layout for phone and tablet walkthroughs
- localStorage for project persistence
- Service worker for offline support
- Web app manifest for PWA install behavior
- Static-file structure with no build tools
- Export flow that generates the estimate package from the browser

## Core Features

### Project Management

- Create multiple property projects
- Name and save projects
- Switch between projects without losing data
- Store each project's repair selections, quantities, notes, pricing overrides, rooms, and photos
- Persist data locally in the browser

### Repair Estimating

- 75+ repair line items
- Repair items organized into the required Spark Homes sections and groups
- Collapsible repair groups for faster mobile navigation
- Item name, unit type, quantity, unit cost, and line total display
- Running total visible during the walkthrough
- Per-project unit cost overrides
- Global standard pricing updates
- Add custom line items
- Remove existing line items on a per-project basis
- "No Action Needed" option for reviewed groups with no required repairs

### Adjustable Room Support

The app supports configurable room types so each estimate can match the actual property.

Supported room types include:

- Bathroom
- Kitchen
- Interior / General
- Systems & Structure
- Exterior
- Bedroom
- Living / Common Areas

Room instances are labeled clearly, for example:

```text
Bathroom 1: Vanity & Countertop
Bathroom 2: Tub & Shower
Bedroom 1: Flooring
```

Agents can add or remove room instances during the walkthrough.

### Progress Tracking

The app includes a completion indicator based on repair groups.

A group is treated as complete when an agent either selects at least one repair item in that group or marks the group as "No Action Needed." This helps reduce missed sections before export.

### Photo Capture

The app supports project photos from a phone or tablet.

Photo features include:

- Device camera or file upload support
- Photo thumbnails inside the project
- Individual photo removal
- Photos included in the export package

Photos are useful for documenting property condition, HVAC labels, water heaters, appliances, serial number plates, and other field details. Automatic OCR or guaranteed serial number extraction is not treated as a required feature in this build.

### Export

The current project can be exported as a ZIP package containing:

- Excel repair cost breakdown
- Project photos

The Excel breakdown includes selected repair items, room or group location, quantity, unit type, unit cost, line total, and grand total.

### PWA and Offline Support

The app includes:

- `manifest.webmanifest` for installable PWA behavior
- `sw.js` for service worker caching
- localStorage persistence for project data
- Offline-friendly static app structure

After the app has been opened from a supported hosted environment, it is designed to continue working without a network connection.

## Creative Addition

The creative addition is a deal analysis tool that helps an acquisition agent connect repair cost to offer strategy.

The estimator calculates the repair total, and the deal calculator can be used to estimate a maximum allowable offer based on assumptions such as after repair value, target margin, holding costs, and repair budget. This is useful because repair estimating is not just a checklist task. It directly affects whether a property is a good deal.

## Data Persistence

The app stores data in browser localStorage.

Saved data can include:

- Projects
- Repair selections
- Quantities
- Notes
- Room instances
- Photos
- Price overrides
- Global pricing edits

Because data is stored locally, clearing browser storage or using a different device may remove or hide saved projects.

## Browser Support

Target browsers:

- Chrome for Android
- Safari for iOS
- Chrome desktop
- Safari desktop

The app should be tested on a phone before submission because the primary use case is an acquisition walkthrough in the field.

## Known Limitations

- Project data is stored locally on the device, not synced across devices.
- Very large photo sets may increase browser storage usage.
- Full PWA behavior depends on HTTPS or localhost because browsers limit service workers on direct file URLs.
- Offline support should be tested from the hosted version after the app has been opened once.
- Automatic serial number extraction from photos is not guaranteed in this version.
- There is no user account system or backend database.

## What I Would Improve Next

With two more days, I would focus on:

- Stronger photo compression and storage handling
- Cloud sync or export history across devices
- More detailed contractor-ready scope-of-work output
- More advanced deal comparison between projects
- Validation warnings before export if groups are incomplete
- Better reporting views for management review
- Optional OCR for serial numbers on HVAC equipment and appliances

## AI Tool Usage

AI tools were used to assist with planning, code organization, debugging, documentation, and checking the project against the contest requirements. Final feature choices, testing, and submission preparation were reviewed manually.

## Submission Notes

Recommended submission package:

```text
1. Hosted live app URL
2. GitHub repository link
3. Completed app files
4. One-page PDF writeup
```

For confidentiality, do not upload the original contest brief or original price list file to a public repository. For the safest submission, use a private repository and share access with Spark Homes.
