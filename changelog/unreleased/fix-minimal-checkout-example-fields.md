## Fix minimal checkout session request example

Corrected the `minimal` inline OpenAPI example on `POST /checkout_sessions` in the 2026-04-17 `agentic_checkout` spec. The example used an `items` field with a per-item `quantity`, but `CheckoutSessionCreateRequest` declares `additionalProperties: false` and requires `line_items`, `currency`, and `capabilities`. Anyone copying the example would send a request the schema (and any merchant validating against it) must reject.

### Changes
- `minimal` example: replaced `items` with `line_items` (matching the `Item` schema shape) and added the required `currency` and `capabilities` fields

### Files Updated
- `spec/2026-04-17/openapi/openapi.agentic_checkout.yaml`

### Reference
- Issue: #278
