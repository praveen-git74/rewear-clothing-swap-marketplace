# ReWear: Clothing Exchange & Swap Marketplace

## 1. Abstract
ReWear is a web-based clothing exchange marketplace concept that helps people pass on wearable clothing and discover pre-loved items from other users. Instead of focusing on monetary purchases, the platform encourages direct barter-style exchanges. Users can browse listings, filter by category, size, condition, and location, view estimated swap values, and send swap requests with a message describing their offer. The current implementation is a responsive frontend prototype built with HTML, CSS, and JavaScript. Browser localStorage is used to demonstrate persistence without a backend.

## 2. Introduction
Fast fashion contributes to high clothing consumption and textile waste. Many people own clothing that is still usable but no longer fits their style or needs. ReWear proposes a community-driven alternative by making clothing reuse and exchange easier to explore. The platform aims to make existing clothes more useful for longer and provide a simple way for people to discover possible swaps.

## 3. Problem Statement
- People often have wearable clothes they no longer use but lack a convenient exchange channel.
- Traditional e-commerce platforms primarily support buying and selling.
- Pricing and resale can add friction when users would prefer a direct exchange.
- Dedicated clothing-swapping communities can be difficult to discover locally.
- Users need basic item details and location information to decide whether an exchange is practical.

## 4. Objectives
### Primary objectives
- Provide a marketplace interface dedicated to clothing exchange.
- Let users create clothing listings and request swaps without payment functionality.
- Encourage reuse and sustainable fashion habits.
- Display item location to help users discover nearby possibilities.
- Show an estimated swap value to support discussion.

### Secondary objectives
- Allow users to include an offer or negotiation message.
- Filter items by category, size, condition, and location.
- Demonstrate a basic admin moderation panel.
- Keep the interface responsive across desktop and mobile screens.

## 5. Scope
### Included in this prototype
- Marketplace browsing with eight sample listings.
- Search and category/size/condition/location filters.
- Create a listing with name, category, size, condition, value, location, owner, description, and optional image URL.
- Send swap requests with a free-text offer/message.
- View requests and mark them accepted or declined in the local demo.
- Favourite/unfavourite listings.
- Admin-style view for counts and removal of listings.
- localStorage persistence in the same browser.

### Not included in this prototype
- Real user accounts or secure authentication.
- Shared cloud database or cross-device data synchronisation.
- Live/private chat, push/email notifications, or dispute resolution.
- Actual location services, maps, automatic matching, or courier integration.
- Payments, AI recommendations, or AR try-on.
- Production-grade administrator access control.

## 6. Technologies Used
- **HTML5:** page structure, forms, navigation, and semantic content.
- **CSS3:** responsive layout, cards, modals, mobile breakpoints, and visual styling.
- **Vanilla JavaScript:** search/filter logic, form handling, swap request workflow, favourites, demo admin controls, and UI updates.
- **Web Storage API (localStorage):** persists demo listings, requests, favourites, and display name in the current browser.
- **Unsplash image URLs:** illustrative sample clothing imagery; internet access is needed for remote images.
- **GitHub Pages (planned deployment):** static hosting option for the project.

## 7. System Modules
### 7.1 Marketplace module
Displays clothing cards with category, size, condition, location, description, estimated swap value, and a swap-request action.

### 7.2 Search and filtering module
Users can search across item names, descriptions, owners, categories, and locations. Dropdowns filter category, size, and condition; a location field filters by city or area.

### 7.3 Listing module
A form collects item information and publishes a card into the current browser's marketplace. If no image URL is provided, a default image is used.

### 7.4 Swap request module
A user selects an item and submits a display name and offer/message. The request is stored with a date and a Pending status. In the demo request panel, a request can be marked Accepted or Declined.

### 7.5 Value display
Each listing displays the owner's estimated swap value in Indian rupees. The prototype does not claim to calculate market value automatically; the value is supplied by the person listing the item and should be discussed between users.

### 7.6 Favourites module
Users can mark items as favourites. The selection persists in localStorage in the current browser.

### 7.7 Admin demonstration module
Shows listing/request/pending counts and permits removal of local demo listings. This is only a UI demonstration and is not secured; it must not be used as a real administrator console.

## 8. Functional Requirements
1. The system shall display available clothing listings.
2. The system shall allow searching and filtering listings.
3. The system shall validate required listing fields before publishing.
4. The system shall allow users to submit a swap request with an offer message.
5. The system shall display submitted requests and their statuses.
6. The demo shall allow a request status to be changed to Accepted or Declined.
7. The system shall allow listings to be saved as favourites.
8. The demo admin panel shall display counts and remove listings.
9. The system shall persist demo information in localStorage.
10. The layout shall adapt to common desktop, tablet, and mobile widths.

## 9. Non-Functional Requirements
- **Usability:** straightforward navigation and clear forms.
- **Responsiveness:** responsive cards, forms, and navigation for mobile and desktop.
- **Maintainability:** separate HTML, CSS, and JavaScript files.
- **Performance:** no build step or application framework is required.
- **Privacy:** this demo warns users not to enter sensitive information; browser data remains local to that browser.
- **Security limitation:** client-side localStorage and the demo admin controls are not secure storage or access control.

## 10. Basic Workflow
1. Open the marketplace.
2. Search or filter the sample listings.
3. Select **Request swap** on an item.
4. Enter a display name and describe the item or exchange being offered.
5. Submit the request.
6. Open the swap request panel to view its status; demo requests can be accepted or declined.
7. To contribute an item, select **List an item**, complete the required fields, and publish.

## 11. Data Model (Prototype)
### Listing
- `id`: unique local identifier
- `name`: item title
- `category`: item category
- `size`: clothing size
- `condition`: Like new, Gently used, or Well loved
- `value`: estimated swap value in INR
- `location`: city or area text
- `owner`: display name
- `description`: item details
- `image`: optional HTTPS image URL

### Swap request
- `id`: unique local identifier
- `itemId` and `itemName`: requested listing reference
- `owner`: listing owner display name
- `requester`: requester display name
- `offer`: offer or negotiation message
- `created`: date string
- `status`: Pending, Accepted, or Declined

## 12. Testing and Validation
The following manual checks should be completed in a browser before submission:
- Open the page at desktop and mobile widths; confirm navigation and cards adapt.
- Search by an item title and verify unrelated cards are filtered out.
- Apply category, size, condition, and location filters, then clear filters.
- Submit a listing with all required fields; confirm it appears in the marketplace.
- Try submitting the listing form with a required field missing; browser validation should block submission.
- Request a swap and confirm it appears in the request panel with Pending status.
- Accept and decline requests; confirm the displayed status changes.
- Favourite an item and refresh the page; confirm the favourite state persists.
- Remove a listing from the admin demo and confirm it disappears from the marketplace.
- Reset demo data and confirm the sample listings return.
- Disconnect from the internet to note that remote images and Google Fonts may not load; the core interface should still work.

## 13. Limitations
The project is a client-side demonstration. localStorage data is not available to other users, browsers, or devices. Swap requests are not actually delivered to another account. Display names are not verified, the admin panel is not access-controlled, and item values are user-entered estimates rather than verified valuations. Location is plain text rather than GPS/map-based matching. Image URLs are external. These limitations should be addressed before any real-world launch.

## 14. Future Enhancements
- Backend API and database for shared listings and requests.
- Secure account registration, login, password reset, and role-based authorization.
- Real-time private messaging and notifications.
- Better value guidance using condition, brand, age, and comparable items.
- Distance-based matching and optional map integration with user consent.
- Courier/logistics partnerships and exchange status tracking.
- Reporting, moderation queues, user ratings, safety guidance, and dispute handling.
- Image uploads with validation and storage controls.
- Accessibility testing, automated tests, analytics, and privacy policy.

## 15. Conclusion
ReWear demonstrates the main user journey for a clothing swap marketplace: discover items, filter by practical attributes, publish a listing, and initiate an exchange request. It communicates the concept of reuse through a simple responsive interface. The current prototype is suitable for demonstrating frontend functionality and project scope, while real multi-user exchanges require backend services and appropriate security controls.
