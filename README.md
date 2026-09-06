# Deniable API Examples

Official integration examples for the Deniable synthetic test data API.

Use these examples to:

- authenticate with an API key
- list available dataset metadata
- retrieve pre-generated documents
- handle prepaid API credits
- use idempotency keys
- handle rate limits and insufficient credits
- integrate Deniable into server-side workflows

## Documentation

- [Quick start](https://deniable.net/docs/quick-start)
- [API reference](https://deniable.net/docs/api-reference)
- [API overview](https://deniable.net/api)
- [Pricing](https://deniable.net/pricing)

## Important

Never place a Deniable API key in browser code, public repositories, client-side applications, prompts, or URLs.

API responses contain pre-generated synthetic documents. Repeating a request with a new idempotency key creates a new metered delivery.

## Example request

```bash
curl -X POST https://api.deniable.net/v1/documents \
  -H "Authorization: Bearer $DENIABLE_API_KEY" \
  -H "Content-Type: application/json" \
  -H "Idempotency-Key: example-run-001" \
  -d '{
    "dataset": "support-tickets-en-json-starter",
    "count": 3,
    "excludeDelivered": true
  }'
