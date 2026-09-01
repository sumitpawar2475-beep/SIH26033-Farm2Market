# Farm2Market Architecture

## 1. Architecture Principles

Farm2Market is a platform-managed marketplace. The backend is the source of truth for orders, payments, settlements, communication, demand intelligence, deal optimization, and logistics.

**Mandatory communication rule:** Farmer and Customer never have a direct communication channel. Transport Workers communicate through the platform.

## 2. High-Level System

```text
Farmer App       Customer App       Transport App       Admin Dashboard
     |                 |                   |                    |
     +-----------------+-------------------+--------------------+
                               |
                         Frontend / Web App
                               |
                           FastAPI API
                               |
       +-----------------------+------------------------+
       |          |             |          |             |
       v          v             v          v             v
   Identity    Order &      Payment &   Messaging     Admin/
   & Access    Matching     Settlement  Gateway      Operations
       |          |             |          |             |
       +----------+-------------+----------+-------------+
                              |
                  +-----------+-----------+
                  |                       |
                  v                       v
             MySQL Database        AI/Optimization Layer
                                      |
                     +----------------+----------------+
                     |                |                |
                     v                v                v
                Price AI         Demand AI        Deal Engine
                                                      |
                                                      v
                                               Logistics Engine
                                                      |
                                         +------------+------------+
                                         |                         |
                                         v                         v
                                   Route Optimizer            Cost Engine
                                         |
                                         v
                                  Maps / Routing APIs
```

## 3. Frontend

Technology:
- React
- JavaScript/TypeScript where adopted by the existing frontend
- CSS

Role-specific views:
- Farmer
- Customer
- Transport Worker
- Admin

The frontend must never expose another user's private contact information unless explicitly required by an authorized platform operation.

## 4. Backend

Technology:
- Python
- FastAPI

Suggested service modules:
- Authentication/authorization
- User/profile verification
- Produce/catalog
- Orders
- Deal optimization
- Payments
- Settlements
- Transport
- Route optimization
- Demand forecasting
- Notifications/messaging
- Admin analytics

## 5. Database

Technology:
- MySQL

Core entities:
- User
- FarmerProfile
- CustomerProfile
- TransportWorker
- Vehicle
- Produce
- ProduceListing
- Order
- OrderItem
- Payment
- Settlement
- Commission
- TransportAssignment
- Route
- RouteStop
- TransportCost
- DemandObservation
- DemandForecast
- Recommendation
- Message/Conversation
- Notification
- Dispute
- AuditLog

Sensitive contact data must be access-controlled. Do not return farmer/customer contact details through marketplace APIs.

## 6. AI and Optimization Layer

Technology:
- Python
- Pandas
- NumPy
- Scikit-learn

### Price Recommendation
Inputs:
- Item/crop
- Region
- Historical prices
- Season
- Quantity
- Demand
- Supply

Output:
- Estimated price
- Recommended range
- Confidence/quality indicator

### Demand Forecasting
Forecast demand by:
- Item
- Region
- Month
- Season

Also estimate:
- Supply-demand gap
- Oversupply risk
- Shortage risk
- Demand trend

### Farmer Recommendation Engine
Combines demand, expected price, production cost, transport cost, supply concentration, season, and risk to generate early diversification/opportunity suggestions.

### Deal Optimization Engine
Evaluates candidate farmer-customer order combinations using:
- Customer total cost/savings
- Farmer expected settlement/profitability
- Platform revenue sustainability
- Logistics cost
- Delivery reliability
- Product quality/quantity

It should return the selected deal, score components, and alternatives.

## 7. Logistics Architecture

Potential technologies:
- OpenStreetMap
- OSRM
- Other routing provider when required

### Logistics Engine
1. Collect pending compatible orders.
2. Group orders by geographic and operational compatibility.
3. Check vehicle capacity and product constraints.
4. Build candidate routes.
5. Score routes by cost, distance, time, capacity utilization, and delay risk.
6. Select the best feasible route.
7. Calculate/allocate shared transport cost.
8. Create transport assignment.
9. Monitor route milestones.

The system should support multiple pickup stops and multiple delivery stops.

## 8. Transport Cost Architecture

Separate these values:

- Estimated actual logistics cost
- Customer transport charge
- Transport worker payout
- Platform logistics margin

Inputs may include distance, time, weight/volume, vehicle type, fuel/operational rate, stops, handling, waiting, and shared-route allocation.

The cost engine must provide a breakdown that can be audited by Admin.

## 9. Payment Architecture

```text
Customer
   |
   v
Payment Provider
   |
   v
Farm2Market Order Payment Record
   |
   v
Fulfilment / Delivery
   |
   v
Settlement Engine
   +----> Farmer Settlement
   +----> Transport Payout
   +----> Platform Commission/Margin
```

For a production system, use a compliant payment provider and follow applicable payment, escrow/settlement, tax, and marketplace regulations. A hackathon frontend may simulate these states.

## 10. Communication Architecture

```text
Farmer --------> Platform <-------- Customer
                    ^
                    |
             Transport Worker
                    ^
                    |
                  Admin
```

No direct Farmer <-> Customer chat, phone disclosure, or email disclosure.

Transport Worker communication is also platform-mediated. The system may relay operational messages without exposing unnecessary personal contact data.

## 11. Admin Architecture

Admin consumes controlled aggregates and operational records from:
- Orders
- Payments
- Settlements
- Transport
- Demand forecasts
- Deal engine
- Route engine
- User verification
- Disputes

Admin actions must be authenticated, authorized, logged, and auditable.

## 12. API Pattern

Frontend
-> FastAPI
-> Authentication/Authorization
-> Domain Service
-> Database / AI / Logistics / Payment Provider

Examples:
- `GET /orders`
- `POST /orders`
- `POST /payments/checkout`
- `GET /payments/{id}`
- `GET /settlements/{id}`
- `POST /transport/assign`
- `PATCH /transport/jobs/{id}/status`
- `GET /routes/{id}`
- `GET /demand/forecast`
- `GET /recommendations/farmer`
- `POST /admin/deals/recalculate`

Exact API contracts should be finalized before dependent frontend/backend work.

## 13. Scalability

Keep domain services modular. AI and route calculations should be separable from request handling so expensive calculations can later run asynchronously. Cache read-heavy forecasts and route results when appropriate.

## 14. Observability and Audit

Record:
- Order state changes
- Payment state changes
- Settlement decisions
- Transport assignments
- Route calculations
- AI recommendation versions/results
- Admin actions
- Disputes/refunds

Never log passwords, payment secrets, or unnecessary personal data.

## 15. Deployment

Deployment is implementation-dependent. Keep configuration in environment variables and never commit secrets. External map/routing/payment services should be replaceable through adapters.
