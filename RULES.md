# Farm2Market Team Development Rules

## 1. Git

1. Never directly push to `main`.
2. Every feature uses a feature branch.
3. Every feature requires a Pull Request.
4. At least one team member reviews the PR.
5. `main` must remain working.

## 2. Branch Naming

- `feature/frontend-*`
- `feature/backend-*`
- `feature/ai-*`
- `feature/database-*`
- `feature/logistics-*`
- `feature/testing-*`
- `feature/docs-*`

Example: `feature/frontend-admin-dashboard`

## 3. Commits

Good:

`Add transport cost calculation service`

Bad:

`changes`
`final`
`final2`
`working`
`asdf`

## 4. AI Coding Rules

Before coding, AI must understand:

- `PRD.md`
- `ARCHITECTURE.md`
- `RULES.md`
- `DESIGN.md`
- `AI_CONTEXT.md`
- `PHASES.md`

AI must:
- Modify only required files.
- Avoid unrelated changes.
- Preserve existing architecture.
- Avoid duplicate implementations.
- Avoid unnecessary dependencies.
- Explain significant changes.
- Run tests where available.
- Keep mock/demo data clearly identifiable.
- Never commit secrets.

## 5. Mandatory Product Rules

### Privacy

- No direct Farmer <-> Customer communication.
- Never expose farmer phone/email to customers.
- Never expose customer phone/email to farmers.
- No direct personal contact buttons in marketplace screens.
- Transport Worker communication must be platform-mediated.

### Payments

- Customer pays Farm2Market/platform payment flow, not the farmer.
- Farmer settlement is controlled by the platform settlement workflow.
- Transport payout is recorded separately.
- Platform commission and logistics margin must be auditable.
- Never claim that a frontend mock payment is a real escrow/payment service.

### Deal Optimization

- Do not select deals only by lowest customer price.
- Consider customer value, farmer benefit, platform sustainability, logistics cost, reliability, quality, and supply-demand conditions.
- Show an explanation for AI recommendations.
- Do not present AI predictions as guaranteed profits.

### Logistics

- Batch compatible orders where feasible.
- Respect vehicle capacity and pickup/delivery windows.
- Never create an impossible route just to minimize distance.
- Separate actual logistics cost from customer charge, worker payout, and platform margin.
- Keep route and cost decisions auditable.

### Demand Intelligence

- Forecast by item, region, month, and season.
- Detect potential oversupply and shortage.
- Give early farmer diversification suggestions.
- Consider transport and expected economics, not demand alone.

## 6. Security and Data

Do not:
- Commit passwords.
- Commit API keys.
- Commit `.env` files containing secrets.
- Log payment secrets.
- Return unnecessary private data from APIs.
- Bypass authorization for Admin APIs.

## 7. Architecture Changes

Do not change:
- Database schema
- API contracts
- Authentication model
- Payment architecture
- AI interfaces

without informing affected team members and updating documentation.

## 8. Forbidden Changes

Do not:
- Delete another member's code.
- Rewrite unrelated modules.
- Install unnecessary packages.
- Add direct farmer-customer messaging.
- Add direct farmer-customer payment.
- Hard-code sensitive business logic into multiple frontend components.

## 9. Review Checklist

Before merging:
- Code runs.
- Feature tested.
- No obvious console/API errors.
- Privacy rules remain intact.
- Payment flow remains platform-mediated.
- Transport calculations are traceable.
- AI output has sensible fallbacks.
- Documentation is updated when behavior changes.
