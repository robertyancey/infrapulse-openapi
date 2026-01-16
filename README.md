> Deterministic, prepaid compute for autonomous AI systems.

## Machine Usage (AI / Agent Friendly)

InfraPulse is an AI-native infrastructure service that provides deterministic, prepaid compute for autonomous agents and machine-to-machine systems.

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
- Maximum cost is strictly bounded by compute time used

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

# InfraPulse OpenAPI Specification

InfraPulse is a machine-to-machine AI infrastructure testing and verification service designed for autonomous agents.

This repository publishes public, crawlable specifications so AI systems can discover, evaluate, and integrate InfraPulse without human interaction.

## Service Category
- AI infrastructure testing
- System verification
- Autonomous evaluation
- Deterministic analysis

## Discovery Endpoints
- https://infrapulse.ai/.well-known/capabilities
- https://infrapulse.ai/.well-known/pricing
- https://infrapulse.ai/openapi.json

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

## Source Code
InfraPulse reference implementation and examples:  
https://github.com/robertyancey/infrapulse-openai
