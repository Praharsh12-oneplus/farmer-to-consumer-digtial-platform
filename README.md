# FarmLink: Farmer-to-Consumer Local Network

FarmLink connects local farmers directly with consumers within a 10 km radius, enabling fresh produce sales, price negotiations, and online payments without middlemen.

## Features

### 1. Proper Email Authentication
- **Sign In & Create Account**: Clean email and password authentication with a tabbed interface.
- **Strict Email Validation**: Validates email syntax, trims and normalizes input, checks minimum password length, and displays clear error feedback.
- **Role-Based Registration**:
  - **Farmers**: Farm name, email, password, farm location area, phone number, and customizable settlement bank / UPI details.
  - **Consumers**: Full name, email, password, delivery area, and phone number.
- **Password Visibility**: Interactive toggle (`👁️` / `🙈`) to view/hide password.
- **Header Profile Badge**: Displays the currently logged-in user's name, email, and avatar with one-click "Switch account" and "Logout".

### 2. Isolated Per-Email Data ("Different Data for Different Emails")
The system starts with a clean slate (no preloaded dummy data). All data is created and tied to each user's email:
- **Farmers (`farmer.html`)**:
  - **My Products (Inventory)**: Displays ONLY products listed by the logged-in farmer's email.
  - **Incoming Orders**: Displays ONLY orders placed for this farmer's products. Actions (Accept, Reject, Mark Paid) only affect their orders and adjust stock.
  - **Negotiation Offers**: Displays price negotiation offers sent by consumers for this farmer's produce, allowing the farmer to Accept or Send a revised offer.
  - **Earnings & Settlement**: "Received Today" and "Pending" totals are calculated solely from this farmer's orders. Bank account and UPI details are loaded and saved to their profile.
  - **Add Product**: Newly listed items are automatically stamped with the logged-in farmer's email and farm name, making them available in the consumer marketplace.
- **Consumers (`consumer.html`)**:
  - **Marketplace**: Browse all fresh produce listed by nearby local farmers within a 10 km radius.
  - **My Orders**: Tracks ONLY orders placed by the logged-in consumer's email.
  - **My Negotiations**: Displays offers sent by this consumer, including farmers' counter-offers with one-click "Accept revised offer".
  - **Online Payment Checkout**: Dropdown only lists unpaid orders placed by this consumer to pay via UPI, Card, or Cash.

### 3. Multilingual Support
Full instant translation for **English**, **हिंदी (Hindi)**, and **मराठी (Marathi)**.

---

## How to Test

1. Open `farmer.html` in your browser.
2. Click **Create Account** and register with a farmer email (e.g. `farmer1@test.com`, password `1234`).
3. Fill out the **Add Product** form to list your first produce (e.g. Fresh Tomatoes, 40 kg, Rs 30/kg).
4. Notice it appears under **My Products**.
5. In a new tab (or window), open `consumer.html`.
6. Click **Create Account** and register with a consumer email (e.g. `consumer1@test.com`, password `1234`).
7. You will see the farmer's produce in the marketplace! Place an order or send a negotiation offer.
8. Switch back to `farmer.html`: the incoming order or offer appears immediately under the farmer's dashboard.
9. Register another farmer (e.g. `farmer2@test.com`) on `farmer.html`: they will start with 0 products and will NOT see `farmer1@test.com`'s inventory or orders.
