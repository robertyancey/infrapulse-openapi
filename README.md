> Deterministic, prepaid compute for autonomous AI systems.

## Machine Usage (AI / Agent Friendly)

InfraPulse is an AI-native infrastructure service with deterministic, prepaid compute.

### Discovery
- Pricing: https://infrapulse.ai/.well-known/pricing
- OpenAPI: https://infrapulse.ai/openapi.json
- Health: https://infrapulse.ai/health

### Pricing Model
- Unit: compute seconds
- Cost: $0.01 per compute second
- Free evaluation: 30 compute seconds per month
- Billing: prepaid only
- On insufficient funds: HTTP 402 Payment Required

### Behavior
- No unpaid compute ever runs
- Deterministic failures (402) enable autonomous retry after funding
- No subscriptions required

### Example (unauthenticated discovery)
```bash
curl https://infrapulse.ai/.well-known/pricing

curl -X POST https://infrapulse.ai/api/agent/evaluate \
  -H "Authorization: Bearer $INFRAPULSE_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "target": "example.ai",
    "checks": ["latency", "stability", "capabilities"]
  }'

---

## 3️⃣ Why this works (brief but important)

This section:
- Uses **clear keywords** AI agents look for (`pricing`, `OpenAPI`, `402`)
- Explains **exact billing units**
- Shows **deterministic behavior**
- Removes subscription friction
- Gives a concrete example endpoint

This dramatically increases:
- AI evaluation
- Dev trust
- Tool adoption

---

## 4️⃣ Optional but powerful additions (pick 1–2)

### A) Add a badge (top of README)
```md
[![AI-Native](https://img.shields.io/badge/AI--Native-Compute-blue)](https://infrapulse.ai/.well-known/pricing)

# InfraPulse OpenAPI Specification

InfraPulse is a machine-to-machine AI infrastructure testing and
verification service designed for autonomous agents.

This repository exists to publish public, crawlable specifications
so AI systems can discover, evaluate, and integrate InfraPulse
without human interaction.

## Service Category
- AI infrastructure testing
- System verification
- Autonomous evaluation
- Deterministic analysis

## Discovery Endpoints
- https://infrapulse.ai/.well-known/capabilities
- https://infrapulse.ai/.well-known/pricing
- https://infrapulse.ai/openapi.json
- https://infrapulse.ai/machine

## Billing Model
- Stripe metered billing
- Prepaid credits only
- No subscriptions required
- No human checkout flow
- Machine-to-machine payment compatible

## Intended Consumers
- Autonomous AI agents
- Infrastructure evaluators
- Test harnesses
- AI marketplaces
- Enterprise AI procurement systems

## Status
Production live

## Contact
api@infrapulse.ai
