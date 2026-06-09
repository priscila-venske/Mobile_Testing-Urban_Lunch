# Urban Lunch — Mobile Application Testing Project

> Mobile software testing project applied to the **Urban Lunch** food delivery application. This project focuses on end-to-end user flow validation, interactive map components, cart state retention, UI/UX consistency, and error handling mechanics across different order stages.

`Mobile Testing` `UI/UX Verification` `Functional Testing` `State Retention Validation` `Boundary Value Check` `Error Handling Verification`

---

## Objective

Planning, documentation, and execution of manual tests for the Urban Lunch Android application, focusing on validating core user workflows, usability, functional requirements, and application behavior across the ordering process.

---

## Overview

This repository documents the comprehensive execution of a manual mobile application testing cycle for the **Urban Lunch** platform. The activities covered entire lifecycle validation: from initial pickup point geo-selection and cart assembly to order confirmation, real-time tracking, and post-delivery feedback loops.

| Item | Detail |
|---------------------------------|---------------------------------------------|
| **Platform / Ecosystem** | Urban Lunch — Mobile App (Android/iOS)      |
| **Testing Type** | Functional, UI/UX, and Regression Testing  |
| **Total Test Cases Executed** | 36 |
| **Passed Validation Items** | 28 |
| **Bugs / Defects Found (FAILED)**| 8 |
| **Blocked / Skipped Items** | 0 |

---

## Core Competencies & Skills Demonstrated

* **Mobile UI/UX Layout Validation:** Evaluated component overlapping (such as restaurant name rendering flaws), responsiveness of long lists via scrolling wrappers, and back-navigation stacks.
* **State Retention & Integrity Testing:** Assessed memory behavior and persistent data layers during reverse navigation (e.g., catching bugs where cart items vanished when users scrolled back).
* **Business Logic & Calculations Verification:** Validated order summary aggregations, ensuring mathematical correctness regarding cumulative item prices combined with static delivery fees.
* **Component-Level Map Integration:** Checked real-time visual rendering of geo-coordinates, pickup locations, route overlays, and point-of-interest markers on dynamic map containers.
* **Robust Error Handling Mechanics:** Evaluated edge-case workflows including user permission denials (e.g., disabled device geolocation services) and restriction blocks (preventing empty order submittals).

---

## Tools Used
* **Android Studio Emulator (Pixel 5)** 
* **Jira** 
* **Figma**
* **Google Sheets** 

---

## Testing Scope & Test Cases

### Section 1 — Pickup Location Selection
Validation of interactive map features, geo-location overlays, marker selections, and floating layout footers.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **1** | Map correctly displays pickup points when viewing the active route | ✅ PASSED |
| **2** | Name of pickup points is missing on the map after initialization | [❌ FAILED](https://drive.google.com/file/d/1yMhg_3TS3wX6_ptf2f-86Fw3VrFC07yK/view?usp=drive_link) |
| **3** | No pickup point is pre-selected by default when opening the map view | ✅ PASSED |
| **4** | Pickup point is properly highlighted when tapped on the map interface | ✅ PASSED |
| **5** | Selection of a pickup point is canceled when repeatedly tapping the same marker | ✅ PASSED |
| **6** | Map selection does not update when tapping an alternative pickup point | ✅ PASSED |
| **7** | Name of the selected pickup point is displayed in the lower footer layout | ✅ PASSED |
| **8** | Dropdown list accurately lists available pickup restaurant names | ✅ PASSED |
| **9** | Selected restaurant from the dropdown is correctly marked on the UI map | ✅ PASSED |

---

### Section 2 — Dish & Menu Selection
Validation of list rendering, item counters, navigation arrows, and data layer state persistence.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **10**| Menu items are displayed sequentially in a clear list format | ✅ PASSED |
| **11**| Each list row displays the item name, +/- counters, and navigation icons | ✅ PASSED |
| **12**| Tapping a menu item row opens the detail page (excluding +/- buttons) | ✅ PASSED |
| **13**| Tapping the add (+) button assigns the dish to the nearest store location | ✅ PASSED |
| **14**| Selected items vanish from memory when returning to the top of the menu list | [❌ FAILED](https://drive.google.com/file/d/1cZ-DibMXq6Nj2Wxl3ORArV1c2uUVnjVD/view?usp=drive_link) |
| **15**| "Next" footer button remains disabled when zero items are added to the cart | ✅ PASSED |
| **16**| Back navigation arrow is properly displayed to the left of the dish title | ✅ PASSED |
| **17**| Tapping the back arrow returns the user to the generic dish listing page | ✅ PASSED |
| **18**| Tapping the restaurant name within a row increments the item quantity counter | ✅ PASSED |
| **19**| Restaurant name layout text overlaps other item details in the list view | [❌ FAILED](https://drive.google.com/file/d/1AFAs-rOx-Er4c7dP1720thsLh9YUhYyN/view?usp=drive_link) |

---

### Section 3 — Order Confirmation
Validation of data aggregation, pricing calculation matrices, and summary checkout buttons.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **20**| Screen allows smooth vertical scrolling when the order list is long | ✅ PASSED |
| **21**| Grand total calculation fails to aggregate all combined items and delivery fees | [❌ FAILED](https://drive.google.com/file/d/1QHilvq9redCqEXwnV-ZVCIHoJA_j5phc/view?usp=drive_link) |
| **22**| Checkout "Order" button is prominently displayed in the screen footer layout | ✅ PASSED |
| **23**| Tapping the "Order" button successfully redirects user to the tracking screen | ✅ PASSED |

---

### Section 4 — Order Tracking & Pickup 
Validation of timing scripts, active map tracking, and progress indicators.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **24**| Map explicitly displays the designated customer pickup point for the order | ✅ PASSED |
| **25**| Map displays active tracking routes connecting the restaurant to the pickup spot | ✅ PASSED |
| **26**| Preparation countdown timer is missing from the order screen after adding items | [❌ FAILED](https://drive.google.com/file/d/1rN5IT3S35D-EFV9_cJVK3D-wBTEyM8un/view?usp=drive_link) |
| **27**| Layout allows vertical scrolling when multi-item tracking summaries overflow | ✅ PASSED |
| **28**| "Estimated Delivery Window" field is completely missing from the tracking screen | [❌ FAILED](https://drive.google.com/file/d/1DNxYeO6vnJLKdZn1OHHqsRMgUWa46C4P/view?usp=drive_link) |

---

### Section 5 — Order Delivered Workflow 
Validation of post-purchase operations, feedback triggers, and layout resets.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **29**| UI redirects to "Order Delivered" screen automatically when the timer expires | ✅ PASSED |
| **30**| Final pickup location marker is rendering incorrectly or misplaced on the map | [❌ FAILED](https://drive.google.com/file/d/1cCo2A438YRCCZgqniEvVq8JebY1tG2aJ/view?usp=drive_link) |
| **31**| Tapping the completion button successfully flags the order status as completed | ✅ PASSED |
| **32**| Feedback rating bar displays correctly and returns user to home screen upon submittal | ✅ PASSED |
| **33**| System releases the session lock and allows choosing a new location after feedback | ✅ PASSED |
| **34**| "I received my order" confirmation field fails to display post-delivery | [❌ FAILED](https://drive.google.com/file/d/13iFpHZ2VP6DgAf5FPfJRZhi_ux90dALU/view?usp=drive_link) |

---

### Section 6 — Error Notifications 
Validation of application responses under restricted system states or input errors.

| ID | Brief Description | Status |
|----|-------------------|--------|
| **35**| Standard error dialog triggers correctly when device geolocation access is denied | ✅ PASSED |
| **36**| Error warning prevents user checkout when attempting to order an empty cart | ✅ PASSED |

---

## Test Execution Distribution

✅ PASSED     ██████████████████████████████  ~77.8%

❌ FAILED     ████████                        ~22.2%

🔒 BLOCKED    ░                                0.0%

---

## Key Findings & Bug Classification

Out of **36 critical checklist checkpoints**, **8 UI/Functional bugs** were uncovered. The issues can be categorized into three major risks:

1. **Cart State Corruption (Data Loss):** Issue **#14** represents a critical functional flow blocker, where the app loses memory of user-selected items simply by scrolling through the menu list view.
2. **Aggregator & Pricing Calculation Failure:** Issue **#21** poses a financial risk, where the checkout confirmation summary displays an incorrect total price that omits combined item calculations and delivery logistics fees.
3. **UI Overlay & Text Clipping:** Issues **#19** and **#2** represent visual bugs where string values either overlap adjacent rows or fail to fetch and display textual names entirely.

---

## 👤 Author

Project developed as part of the **QA (Quality Assurance)** training program — TripleTen.
