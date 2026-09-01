# AI Coding Context

## Project

SIH26033 - Farm2Market

## Purpose

Build a platform-managed agricultural commerce and logistics system that improves farmer outcomes, customer value, platform sustainability, and transport efficiency.

**Do not implement Farm2Market as a direct farmer-to-buyer contact marketplace.**

## Architecture

Frontend: React / JavaScript or TypeScript as already used by the frontend

Backend: Python + FastAPI

Database: MySQL

AI: Python + Pandas + NumPy + Scikit-learn

Logistics: OpenStreetMap + OSRM or replaceable routing provider

Payments: Use a compliant external payment provider in production; simulation is acceptable for the hackathon frontend.

## Core Product Model

```text
Farmer -> Farm2Market -> Customer
                    |
                    +-> Transport Worker
                    +-> Admin
```

The platform controls order flow, communication, payment records, settlement, transport coordination, and operational analytics.

## Mandatory Business Rules

1. Customer pays the platform, never the farmer directly.
2. Farmer settlement is created/controlled by the platform after configured fulfilment/settlement conditions.
3. No direct farmer-customer chat or personal contact disclosure.
4. Transport workers communicate through the platform.
5. Transport charges must be calculated transparently.
6. Shared routes should support multiple compatible orders.
7. Deal selection must balance customer benefit, farmer benefit, platform sustainability, and logistics efficiency.
8. Demand must be analyzed by item, region, month, and season.
9. Oversupply/shortage risk must be detected.
10. Farmer suggestions must be early, explainable, and not presented as guaranteed profit.

## AI Modules

### 1. Price Recommendation

Inputs:
- Item/crop
- Region
- Historical price
- Season
- Quantity
- Demand
- Supply

Outputs:
- Predicted price
- Recommended range
- Confidence/quality indicator

### 2. Demand Forecasting

Forecast demand by item + region + month + season.

Outputs:
- Forecast demand
- Forecast supply
- Gap
- Demand trend
- Oversupply risk
- Shortage risk

### 3. Farmer Recommendation Engine

Consider:
- Forecast demand
- Expected price
- Production cost where available
- Transport cost
- Supply concentration
- Season
- Risk

Generate early opportunities and diversification suggestions.

### 4. Deal Optimization Engine

Do not choose only the cheapest offer. Score candidate deals using:

- Customer total cost/savings
- Farmer expected settlement/profitability
- Platform commission/margin sustainability
- Transport cost
- Delivery reliability
- Product quality/quantity
- Supply-demand conditions

Return:
- Selected deal
- Score components
- Explanation
- Alternatives when available

All weights should be configurable.

### 5. Logistics/Route Optimization

Group compatible orders using:
- Geographic proximity
- Pickup windows
- Delivery windows
- Vehicle capacity
- Product compatibility
- Cost reduction potential

Optimize for a configurable combination of:
- Distance
- Time
- Cost
- Capacity utilization
- Delay risk

Support multiple pickups and deliveries.

### 6. Transport Cost Engine

Calculate:
- Estimated actual logistics cost
- Customer transport charge
- Transport worker payout
- Platform logistics margin

Use distance, time, vehicle, weight/volume, stops, handling, waiting, shared-route allocation, and configurable business rules.

## Payment and Settlement Logic

Prototype flow:

Customer checkout -> Payment received simulation -> Order fulfilment -> Delivery confirmation -> Settlement calculation -> Farmer/transport/platform ledger records

Do not describe a prototype simulation as a production escrow system. Production payments must use a compliant provider and applicable regulations.

## Communication Logic

Never create APIs/UI that expose farmer/customer private contact data to each other.

Use platform conversations/ticketing for communication. Transport communication is also platform-mediated.

## AI Coding Rules

Read:
- PRD.md
- ARCHITECTURE.md
- RULES.md
- DESIGN.md
- AI_CONTEXT.md

Before coding.

AI must:
- Modify only required files
- Preserve existing architecture
- Avoid duplicate implementations
- Avoid unnecessary dependencies
- Explain important decisions
- Test changes
- Keep demo data clearly marked
- Never commit secrets
- Never invent real payment/AI accuracy claims

## Frontend-First Rule

The current product is primarily a frontend design/prototype. Build interfaces and realistic mock states first where backend services do not yet exist. Keep mock service interfaces replaceable with real APIs later.

## Current Priority

Implement the documented product model consistently across frontend screens before adding unrelated features.
