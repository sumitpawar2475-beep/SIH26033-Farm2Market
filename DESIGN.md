# Farm2Market Design System

## 1. Design Goals

- Simple and farmer-friendly
- Clean and trustworthy
- Mobile-first for farmers and transport workers
- Clear financial information
- Easy-to-understand AI recommendations
- Strong privacy boundaries
- Consistent visual language across all roles

## 2. Roles and Navigation

### Farmer
1. Login/Verification
2. Dashboard
3. Add Produce
4. My Listings
5. AI Price Recommendation
6. Demand Forecast
7. AI Suggestions
8. Orders
9. Settlement
10. Support/Platform Messages

### Customer
1. Login/Verification
2. Dashboard
3. Search Produce
4. Product Details
5. Deal Comparison
6. Checkout
7. Payment Status
8. Orders
9. Delivery Tracking
10. Support

### Transport Worker
1. Login/Verification
2. Driver Dashboard
3. Available/Assigned Jobs
4. Route Details
5. Pickup Stops
6. Delivery Stops
7. Status Updates
8. Earnings/Payouts
9. Issue Reporting

### Admin
1. Admin Login
2. Operations Overview
3. Orders
4. Farmers
5. Customers
6. Transport Workers
7. Vehicles
8. Live Transport Monitoring
9. Route Optimization
10. Demand Intelligence
11. Deal Optimization
12. Payments & Settlements
13. Revenue Analytics
14. Disputes/Support
15. Audit Logs

## 3. Farmer Dashboard

Show:
- Current listings
- Pending orders
- Expected settlement
- Demand forecast
- Oversupply/shortage alerts
- Recommended opportunities
- Price recommendation
- Order and delivery status

Example demand card:

> **Pune | Next Month**
> - Onion: High demand
> - Potato: Good demand
> - Tomato: Moderate demand
> - Cabbage: Oversupply risk
>
> Review the AI suggestion before making production decisions.

## 4. Customer Experience

Product cards should show:
- Product/item
- Quality/grade
- Quantity
- Product price
- Estimated transport charge
- Platform/service fee
- Applicable taxes/charges
- Total payable amount
- Estimated delivery date

Customer checkout must clearly state:

**Payment is made to Farm2Market.**

Do not display farmer phone number, email, private address, or direct chat controls.

## 5. Deal Comparison Screen

Show why the platform selected an offer.

Example:

| Factor | Result |
|---|---|
| Customer total | ₹X |
| Customer savings | ₹Y |
| Farmer expected settlement | ₹Z |
| Transport cost | ₹A |
| Platform fee/revenue | ₹B |
| Delivery estimate | N days |
| Deal score | 84/100 |

Include alternative offers where useful.

## 6. Payment Screen

Use a transparent breakdown:

```text
Product subtotal          ₹10,000
Transport charge           ₹2,000
Platform/service fee         ₹100
Applicable taxes/fees         ₹XX
---------------------------------
Total payable             ₹12,XXX
```

Status examples:
- Payment pending
- Payment received
- Order confirmed
- Fulfilment in progress
- Delivered
- Settlement processing
- Settled
- Refunded/partially refunded

## 7. Transport Worker Dashboard

Show:
- Assigned route
- Vehicle capacity
- Current load
- Pickup stops
- Delivery stops
- Estimated distance/time
- Route status
- Job payout
- Delay/issue reporting

The worker should receive operational information required for the job, not unnecessary personal data.

## 8. Transport Monitoring

Admin map should show:
- Active routes
- Vehicle/worker identifier
- Route progress
- Pickup and delivery stops
- Delayed stops
- Capacity utilization
- Estimated vs actual cost
- Route efficiency

Use clear status indicators such as planned, assigned, pickup, in transit, delayed, delivered.

## 9. Route Optimization Screen

Show:
- Orders selected for batching
- Vehicle selected
- Capacity used/remaining
- Pickup sequence
- Delivery sequence
- Total distance
- Estimated time
- Estimated actual logistics cost
- Customer transport-charge allocation
- Expected savings from batching

Allow Admin to compare candidate routes before confirming where appropriate.

## 10. Demand Intelligence Dashboard

Filters:
- Item
- Region
- Month
- Season
- Date range

Charts/cards:
- Historical demand
- Forecast demand
- Current supply
- Forecast supply
- Supply-demand gap
- Oversupply risk
- Shortage risk
- Price trend
- Opportunity score

Regional heatmap should highlight demand and supply concentration.

## 11. Farmer Recommendation UI

Recommendations must include the reasoning.

Example:

> **Opportunity: Onion**
> - Expected demand: High
> - Expected supply: Moderate
> - Transport cost: Low
> - Demand trend: Increasing
> - Risk: Medium
>
> **Why:** Forecast demand is stronger than forecast supply in this region.

Never display an AI forecast as a guaranteed profit.

## 12. Admin Finance Dashboard

Cards:
- Customer payments
- Pending settlements
- Farmer settlements
- Transport payouts
- Platform commission
- Logistics margin
- Refunds
- Net platform revenue

Add filters for date, region, product, and order status.

## 13. Communication UI

All communication is platform-mediated.

Allowed:
- Farmer -> Platform support
- Customer -> Platform support
- Transport Worker -> Platform operations
- Admin -> Platform users

Forbidden UI:
- Farmer-to-customer chat
- Customer-to-farmer phone/email disclosure
- Direct farmer/customer contact buttons
- Direct customer/transport-worker personal contact exchange

## 14. Privacy UX

Use neutral identifiers where possible, such as:
- Order ID
- Route ID
- Driver/worker ID
- Farmer ID

Only reveal information required for the current workflow.

## 15. Responsive Design

The system should work on:
- Mobile phones
- Tablets
- Desktop screens

Farmer and transport-worker interfaces should prioritize large touch targets, short text, clear status cards, and low-complexity workflows.

## 16. Design Rule

Do not introduce a completely different visual style for every page. Reuse the same typography, spacing, cards, forms, tables, charts, status indicators, and navigation patterns.
