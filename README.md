# Nodium API — OpenAPI description

The machine-readable description of the [Nodium](https://nodium.io) API, the WhatsApp API gateway for developers. Generated from the code of the API: what is here is what the server does.

| File | What it is |
|---|---|
| [`openapi.json`](./openapi.json) | OpenAPI 3.1: every route, its fields, responses, refusals and code samples (cURL, Node.js, Python). |
| [`webhook-events.json`](./webhook-events.json) | Every webhook event, with its fields and an example. |
| [`llms.txt`](./llms.txt) | Every published route in one text file, for LLMs. |

The live copies are at `https://nodium.io/docs/api/openapi.json`, `https://nodium.io/docs/api/webhook-events.json` and `https://nodium.io/docs/api/llms.txt`.

## Use it

- **Postman, Insomnia, Bruno**: import `openapi.json` (or its URL). Set the bearer token to your API key (`nod_…`).
- **Generate a client** in any language:

  ```bash
  npx @openapitools/openapi-generator-cli generate \
    -i https://nodium.io/docs/api/openapi.json -g python -o ./nodium-client
  ```

- **TypeScript**: use the SDK instead, [`@nodium.io/whatsapp`](https://github.com/Nodium-io/sdk).

## The API in three lines

- Base URL `https://nodium.io/api/v1`, JSON over HTTPS, `Authorization: Bearer nod_…`.
- Answers are `{ "data": … }` or `{ "error": { "code", … } }`. Branch on `error.code`.
- One key acts for every client of your account; the `Nodium-Tenant` header names the client.

Guide: https://nodium.io/en/docs/api · Reference: https://nodium.io/en/docs/api/reference

MIT © By-Tech.io
