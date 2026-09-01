# Farm2Market — Project Memory

## Project Identity

Farm2Market is an AI-powered agricultural commerce, demand intelligence, payment, and logistics platform.

The platform connects farmers, customers, transport workers, and administrators through a controlled intermediary system.

The platform is **not** a direct farmer-to-customer communication marketplace.

---

## Core Business Model

The mandatory transaction flow is:

**Farmer → Farm2Market Platform → Customer**

Customer payments are processed through the Farm2Market platform/order system before the farmer settlement workflow is completed.

The platform generates revenue through configurable:

* Platform commission
* Logistics/service margin
* Future premium services

All charges must be transparent.

---

## Critical Privacy Rule

### NEVER create direct Farmer ↔ Customer contact.

Farmers must NOT receive:

* Customer phone number
* Customer personal email
* Customer private contact details
* Direct messaging access to customers

Customers must NOT receive:

* Farmer phone number
* Farmer personal email
* Farmer private contact details
* Direct messaging access to farmers

Communication must happen through Farm2Market.

The platform may relay necessary operational messages without exposing personal contact information.

---

## Transport Communication

Transport workers communicate through Farm2Market.

Allowed:

* Transport Worker → Platform
* Platform → Transport Worker
* Transport Worker → Admin
* Admin → Transport Worker

The system provides transport workers with only the information necessary to complete assigned deliveries.

---

## Payment Flow

The intended business workflow is:

1. Customer selects a product/order.
2. Farm2Market calculates product price, transport charge, service/platform charges, and applicable taxes/fees.
3. Customer sees the complete price breakdown.
4. Customer pays through the platform's payment workflow.
5. Order is confirmed.
6. Farm2Market coordinates fulfilment and transportation.
7. Delivery is completed.
8. Platform records/initiates farmer settlement according to the configured settlement policy.
9. Transport worker payout is recorded separately.
10. Platform revenue is recorded.

For prototypes, payment and settlement may use mock/demo data and must be clearly labelled.

Real deployment must use compliant payment infrastructure.

---

## AI Deal Optimization

Farm2Market should not simply select the cheapest product.

The Deal Optimization Engine evaluates multiple objectives:

* Customer total cost
* Farmer expected benefit
* Platform sustainability/revenue
* Transport cost
* Delivery time
* Product quality
* Supply availability
* Demand
* Reliability
* Logistics efficiency

The objective is to find a balanced deal that provides value to:

**Customer + Farmer + Farm2Market**

AI recommendations are decision-support recommendations and must never be presented as guaranteed profits.

---

## Transport Cost Optimization

The platform calculates transport costs using relevant factors such as:

* Distance
* Route distance
* Vehicle type
* Vehicle capacity
* Load weight
* Fuel/operating assumptions
* Number of stops
* Handling
* Waiting time
* Extra distance
* Other configured logistics costs

The system should maintain separate values for:

* Estimated logistics cost
* Customer transport charge
* Transport worker payout
* Platform logistics margin

Transport pricing must be explainable and auditable.

---

## Multi-Order Route Optimization

Farm2Market should attempt to combine compatible orders into efficient transportation routes.

Possible combined orders should be evaluated using:

* Pickup proximity
* Delivery proximity
* Vehicle capacity
* Product compatibility
* Pickup windows
* Delivery deadlines
* Travel time
* Traffic/road conditions when available
* Vehicle availability
* Total route cost

The objective is to:

* Reduce transportation cost
* Reduce unnecessary travel
* Increase vehicle utilization
* Reduce empty capacity
* Maintain delivery reliability

Never create an infeasible route merely to reduce distance.

---

## Demand Intelligence

Farm2Market continuously analyzes demand patterns by:

* Product/item
* Region
* Month
* Season
* Historical orders
* Current orders
* Available supply
* Price trends
* Relevant market signals

The Demand Intelligence Engine should generate:

* Demand forecasts
* Supply-demand gaps
* Shortage warnings
* Oversupply warnings
* Regional opportunities
* Seasonal opportunities
* Product concentration analysis
* Diversification suggestions

---

## Early Farmer Recommendations

Farmers should receive demand-related decision support early enough to help with planning.

Example:

**Pune — Next Month**

* Onion → High expected demand
* Potato → Good expected demand
* Tomato → Moderate expected demand
* Cabbage → Oversupply risk

The system should recommend diversification when excessive supply concentration is detected.

Recommendations should consider:

* Expected demand
* Expected supply
* Expected price
* Production economics when available
* Transport cost
* Regional competition
* Season
* Risk

The system must not guarantee that a recommendation will produce profit.

---

## Regional Demand Transfer

The platform should identify opportunities where:

**Region A has potential oversupply**

while:

**Region B has stronger demand.**

The platform can then use its deal and logistics engines to determine whether moving products between regions is economically worthwhile.

Example:

**Pune → Tomato oversupply**

**Mumbai → Tomato demand opportunity**

The system can evaluate:

* Product price
* Additional transportation cost
* Demand
* Customer price
* Farmer benefit
* Platform margin
* Route availability

Only recommend the transfer if the overall deal remains beneficial and feasible.

---

## Admin Dashboard

The Admin Dashboard is the central operational control system.

It should provide:

### Orders

* Pending
* Confirmed
* Processing
* Transport assigned
* In transit
* Delivered
* Cancelled
* Disputed

### Farmers

* Farmers
* Inventory
* Products
* Orders
* Settlement status

### Customers

* Customers
* Orders
* Payment status
* Delivery status
* Refunds/disputes

### Transport

* Transport workers
* Vehicles
* Capacity
* Availability
* Active routes
* Multi-order routes
* Pickup status
* Delivery status
* Delays
* Route efficiency

### Demand Intelligence

* Regional demand
* Monthly demand
* Seasonal demand
* Supply-demand gap
* Oversupply
* Shortage
* Product concentration
* Farmer recommendations

### Finance

* Customer payments
* Farmer settlements
* Transport payouts
* Platform commission
* Logistics margin
* Refunds
* Net platform revenue

---

## User Roles

Farm2Market has four primary roles:

### Farmer

Can:

* Manage profile
* Add/manage produce
* Manage inventory
* View orders
* View settlement status
* Receive demand recommendations
* Receive platform notifications

Cannot:

* Directly contact customers

### Customer

Can:

* Browse products
* Search/filter products
* View recommended deals
* Place orders
* Pay through platform
* Track orders
* View invoices
* Contact platform support

Cannot:

* Directly contact farmers

### Transport Worker

Can:

* Manage availability
* View assigned transport tasks
* View required pickup/delivery information
* Accept/reject assignments where permitted
* Update transport status
* Receive optimized routes
* Report problems
* Confirm pickup/delivery

Should not receive unnecessary private contact information.

### Admin

Can monitor and manage:

* Users
* Orders
* Payments
* Settlements
* Transport
* Routes
* Demand
* AI recommendations
* Platform revenue
* Disputes
* System operations

---

## Source of Truth

The following documentation files define the project:

1. `README.md`
2. `PRD.md`
3. `ARCHITECTURE.md`
4. `DESIGN.md`
5. `AI_CONTEXT.md`
6. `RULES.md`
7. `PHASES.md`
8. `MEMORY.md`

When implementing features, AI coding tools should read these files before making architectural decisions.

If code conflicts with these requirements, the documentation should be treated as the intended product specification.

---

## Frontend Principle

The frontend must clearly represent Farm2Market as a managed platform.

Do not design the UI as a simple social marketplace where farmers and customers directly negotiate.

The UI should emphasize:

**AI Matching + Demand Intelligence + Platform Payments + Managed Logistics + Admin Control**

---

## Demo Principle

For hackathon/demo purposes:

* Mock data is acceptable.
* Simulated payments are acceptable.
* Simulated GPS/route data is acceptable.
* AI forecasts may use demo datasets.
* Clearly label simulated/demo data.
* Do not present simulated results as real-world financial guarantees.

---

## Development Principle

Build modularly.

Expected major modules:

```text
frontend/
backend/
ai/
database/
logistics/
tests/
docs/
```

The frontend should be capable of consuming backend APIs later rather than hardcoding the entire business logic into UI components.

---

## Non-Negotiable Rules

1. No direct Farmer ↔ Customer contact.
2. Customer payment goes through Farm2Market.
3. Farmer settlement is controlled by the platform workflow.
4. Transport communication is platform-mediated.
5. Transport charges must be explainable.
6. Deal optimization must consider all three parties.
7. Route optimization must consider multiple compatible orders.
8. Demand must be analyzed by region, month, and season.
9. Oversupply must trigger diversification/opportunity analysis.
10. Farmer recommendations must be provided early.
11. AI predictions are not guaranteed profits.
12. Admin must have operational visibility.
13. Personal contact information must be protected.
14. Never sacrifice route feasibility for theoretical cost savings.
15. Demo/mock functionality must be clearly identified.
