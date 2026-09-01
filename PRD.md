# SIH26033 - Farm2Market Product Requirements Document

## 1. Product Overview

Farm2Market is an AI-powered, platform-managed agricultural commerce and logistics system. It helps farmers reach verified customers through the platform, optimizes deals for farmers, customers, and the platform, coordinates transport, forecasts regional demand, and manages payment settlement.

Farm2Market is **not** a direct farmer-to-customer contact marketplace. The platform is the controlled intermediary for orders, communication, payments, and logistics.

## 2. Problem Statement

Farmers can face uncertain demand, weak price visibility, inefficient logistics, and supply concentration. Customers can face high prices and delivery costs. Transport may be inefficient when separate orders use separate vehicles.

The system must coordinate the complete transaction while protecting user contact information and improving economic and logistics efficiency.

## 3. Core Objectives

- Platform-mediated farmer-customer commerce
- No direct farmer-customer contact
- Transparent product and price discovery
- AI-based price recommendation
- Three-sided deal optimization
- Customer payment to the platform before fulfilment
- Controlled farmer settlement after fulfilment according to settlement rules
- Transport-worker assignment and communication through the platform
- Accurate and transparent transport-charge calculation
- Multi-order pickup and route optimization
- Regional, monthly, and seasonal demand forecasting
- Oversupply/shortage detection
- Early diversification suggestions for farmers
- Centralized Admin Dashboard

## 4. Users and Access

### Farmer
- Register and verify profile
- Add produce, quantity, quality, location, availability date, and asking price
- View AI price and demand recommendations
- View platform-generated opportunities
- Accept/confirm platform orders
- View fulfilment and settlement status
- Communicate with the platform only
- Never receive customer personal contact information

### Customer
- Register and verify profile
- Search and compare platform-approved produce offers
- View price, quality, quantity, estimated delivery, and charges
- Place orders through Farm2Market
- Pay the platform
- Track orders and delivery
- Raise support requests through the platform
- Never receive farmer personal contact information

### Transport Worker
- Register/verify vehicle and capacity
- View assigned jobs
- Accept or reject assignments
- Receive required pickup/delivery instructions from the platform
- Update pickup, transit, delay, and delivery status
- Share location/route status where supported
- Report issues to Admin/platform
- Do not directly exchange personal contact information with farmers or customers

### Administrator / Operations
- Manage users and verification
- Monitor orders and payments
- Approve/manage transport workers and vehicles
- Assign and monitor transport
- Review AI deal recommendations
- Monitor demand and supply by region/month/season
- Manage commissions and pricing rules
- Monitor farmer settlements and transport payouts
- Handle disputes, refunds, exceptions, and fraud/risk alerts

## 5. End-to-End Order Flow

1. Farmer lists produce.
2. AI evaluates price, demand, supply, location, and logistics.
3. Platform discovers compatible customer demand.
4. Deal Engine evaluates candidate deals.
5. Platform selects/recommends a balanced deal.
6. Customer reviews the complete price breakdown.
7. Customer pays the platform.
8. Platform confirms the order/payment state.
9. Logistics Engine batches compatible orders.
10. Route Engine selects an efficient route and vehicle.
11. Transport worker receives the assignment through the platform.
12. Goods are picked up and delivered.
13. Delivery is confirmed.
14. Platform performs settlement according to the configured settlement policy.
15. Farmer receives the farmer settlement; transport worker receives the transport payout; platform records commission/logistics revenue.

## 6. Payment and Settlement

Customer payment flow:

Customer -> Payment Provider/Platform -> Order Fulfilment -> Settlement -> Farmer/Transport/Platform

Rules:
- Customer does not pay the farmer directly.
- Farmer does not collect customer payment directly.
- Customer sees product price, transport charge, service/platform fee, and applicable taxes/charges separately.
- Farmer sees expected settlement and applicable deductions/fees.
- Settlement status must be auditable.
- Production implementation must use a compliant payment provider and applicable payment/marketplace regulations. The prototype may simulate payment and settlement states.

## 7. Platform Revenue Model

The platform may earn through configurable, transparent sources:

- Transaction/platform commission
- Logistics/service margin where applicable
- Optional future premium services

Revenue must never be hidden from the customer or farmer. Admin can configure rates subject to business and legal rules.

## 8. Transport Charge Engine

The system estimates the transport cost using:

- Route distance
- Estimated travel time
- Vehicle type/capacity
- Weight/volume
- Number of pickup and delivery stops
- Fuel/operational rate
- Loading/unloading or handling cost
- Waiting/extra-distance rules
- Route sharing with other orders
- Platform logistics margin, if configured
- Applicable taxes/fees

The engine should distinguish:

`Estimated Actual Logistics Cost`
`Customer Transport Charge`
`Transport Worker Payout`
`Platform Logistics Margin`

Shared-route costs must be allocated fairly among participating orders using a documented allocation method such as distance, weight/capacity usage, or incremental route cost.

## 9. Three-Sided Deal Optimization

The Deal Engine must not optimize only for the cheapest customer price. It should balance:

- Customer total cost and savings
- Farmer expected settlement/profitability
- Platform sustainable revenue
- Transport efficiency
- Delivery time/reliability
- Product quality and quantity
- Supply-demand conditions

A configurable prototype score may use:

`Deal Score = Customer Benefit + Farmer Benefit + Platform Benefit + Logistics Efficiency + Reliability`

Weights must be configurable. The system must show why a deal was selected and may provide alternative deals.

AI recommendations are decision support, not guaranteed prices or profits.

## 10. Multi-Order Logistics Optimization

The Logistics Engine should identify compatible orders that can share transport when:

- Pickup locations are geographically compatible
- Delivery locations are compatible
- Vehicle capacity is sufficient
- Product compatibility/safety rules permit consolidation
- Pickup and delivery time windows can be satisfied
- Combined routing reduces cost or improves utilization

The Route Engine should minimize a configurable combination of distance, travel time, transport cost, delay risk, and unnecessary empty capacity.

## 11. Demand Intelligence

Demand Forecasting must monitor:

- Item/product
- Region
- Month
- Season
- Historical orders
- Current orders
- Current and expected supply
- Price trends
- Regional consumption patterns
- Events/festivals where relevant
- Weather or market signals when reliable data is available

Outputs:
- Forecast demand
- Forecast supply
- Supply-demand gap
- Shortage risk
- Oversupply risk
- Demand trend
- Opportunity score
- Farmer diversification suggestions

The system should detect concentration/"traffic" of a specific item and warn when expected supply is substantially above expected demand.

## 12. Early Farmer Recommendations

The platform should provide early alerts such as:

- High expected demand
- Stable/balanced demand
- Oversupply risk
- Potential alternate region
- Potential product diversification opportunity

Recommendations must consider demand together with expected price, production cost, transport cost, supply concentration, season, and risk. The platform must not guarantee that a recommended crop/product will be profitable.

## 13. Admin Dashboard Requirements

### Operations
- Live order pipeline
- Pending/confirmed/in-transit/delivered orders
- Exceptions and delays

### Transport Monitoring
- Active vehicles/workers
- Assignments
- Capacity utilization
- Route status
- Pickup/delivery milestones
- Estimated vs actual transport cost

### Demand Intelligence
- Regional demand heatmap
- Item/month/season filters
- Forecast demand vs supply
- Oversupply and shortage alerts
- Farmer recommendation monitoring

### Finance
- Customer payments
- Farmer settlements
- Transport payouts
- Platform commission
- Logistics margin
- Refunds/disputes
- Net platform revenue

### Deal Engine
- Recommended deals
- Deal score breakdown
- Customer benefit
- Farmer benefit
- Platform benefit
- Alternative deals

## 14. Privacy and Communication Requirement

**Mandatory:** There must be no direct farmer-customer contact channel.

The platform must not expose:
- Farmer phone/email to customer
- Customer phone/email to farmer
- Direct personal messaging between farmer and customer

Operational communication is routed through Farm2Market. Transport workers also communicate through the platform and receive only information required to fulfil assigned jobs.

## 15. MVP

The MVP should demonstrate:

Farmer onboarding -> Produce listing -> Demand/price recommendation -> Customer order -> Customer platform payment simulation -> Deal optimization -> Multi-order transport planning -> Transport monitoring -> Delivery -> Settlement simulation -> Admin analytics

## 16. Success Criteria

A successful demonstration should show:

1. Customer pays the platform, not the farmer.
2. Farmer and customer remain contact-isolated.
3. Platform selects a balanced deal.
4. Transport worker receives an assignment through the platform.
5. Multiple compatible orders can be batched.
6. Route and transport charge are calculated transparently.
7. Demand is forecast by item, region, month, and season.
8. Oversupply is detected and early farmer suggestions are generated.
9. Admin can monitor operations, logistics, finance, demand, and AI decisions from one dashboard.
