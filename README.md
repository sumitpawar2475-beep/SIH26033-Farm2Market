# SIH26033 - Farm2Market

AI-powered **platform-managed agricultural commerce and logistics system** for Smart India Hackathon problem SIH26033.

## What Farm2Market Does

Farm2Market connects farmers and customers through a controlled platform instead of direct contact. The platform coordinates product discovery, AI-assisted pricing and demand intelligence, deal optimization, payment workflow, transport, route planning, settlement, and administration.

### Core Flow

```text
Farmer -> Farm2Market Platform -> Customer
                    |
                    +-> Transport Worker
                    +-> Admin
```

**Customer pays the platform first. The platform controls the settlement workflow and then records farmer settlement, transport payout, and platform revenue.**

## Key Features

### For Farmers
- Produce listing
- AI price recommendation
- Regional/monthly/seasonal demand forecast
- Oversupply and shortage alerts
- Early diversification suggestions
- Order and settlement tracking
- Platform-mediated support

### For Customers
- Product search and comparison
- AI-assisted deal selection
- Transparent product + transport + service charges
- Platform payment
- Delivery tracking
- Platform support

### For Transport Workers
- Vehicle/capacity management
- Platform-assigned jobs
- Multi-stop route
- Pickup/delivery status updates
- Route information
- Issue reporting and payout tracking

### For Admin
- Operations dashboard
- User verification
- Order monitoring
- Transport monitoring
- Route optimization
- Demand intelligence
- Deal optimization
- Payments and settlements
- Commission/logistics revenue analytics
- Disputes and audit logs

## AI and Optimization

Farm2Market uses multiple intelligence modules:

1. **Price Recommendation** - estimates a useful price range from market, location, season, demand, supply, and quantity signals.
2. **Demand Forecasting** - forecasts demand by item, region, month, and season.
3. **Supply/Demand Risk** - identifies possible oversupply, shortage, and product concentration.
4. **Farmer Recommendation Engine** - gives early, explainable diversification/opportunity suggestions.
5. **Deal Optimization** - balances customer benefit, farmer benefit, platform sustainability, logistics cost, quality, and reliability.
6. **Route Optimization** - batches compatible orders and selects efficient multi-pickup/multi-delivery routes.
7. **Transport Cost Engine** - calculates estimated actual logistics cost and transparent customer transport charges.

AI outputs are decision support and are not guarantees of prices or profits.

## Privacy Rule

**There must be no direct farmer-customer communication.**

The system must not expose farmer phone/email to customers or customer phone/email to farmers. Transport-worker communication is also platform-mediated.

## Payment and Revenue Model

```text
Customer Payment
       |
       v
Farm2Market Platform
       |
       +--> Farmer Settlement
       +--> Transport Payout
       +--> Platform Commission / Logistics Margin
```

Potential platform revenue sources:
- Transparent transaction/platform commission
- Logistics/service margin where applicable
- Future premium services

For production use, payment and settlement must use a compliant payment provider and follow applicable regulations. Hackathon/demo payment states may be simulated.

## Technology

- Frontend: React / JavaScript or TypeScript as used by the existing frontend
- Backend: Python + FastAPI
- Database: MySQL
- AI: Python, Pandas, NumPy, Scikit-learn
- Maps/Routing: OpenStreetMap + OSRM or another replaceable routing provider

## Documentation

- `PRD.md` - Product requirements and business rules
- `ARCHITECTURE.md` - System architecture and service boundaries
- `DESIGN.md` - UI/UX and screen requirements
- `AI_CONTEXT.md` - Coding/AI implementation context
- `RULES.md` - Team, security, privacy, and product rules
- `PHASES.md` - Development roadmap

## Current Product Status

The current application began as a frontend design/prototype. Backend, AI, payment, database, and logistics services can be integrated incrementally behind the documented interfaces.

## Hackathon Demo

Recommended end-to-end demonstration:

`Farmer Listing -> Demand Alert -> AI Deal -> Customer Order -> Platform Payment -> Multi-Order Batching -> Route Optimization -> Transport Assignment -> Delivery -> Settlement -> Admin Analytics`
