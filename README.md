# Platform Chat API

Official API definitions and Postman resources for the Platform Chat API.

This repository is the public source of truth for our API contract. If you want to explore the API, import it into Postman, generate SDKs, or build backend integrations, start here.

## What you can do with this repository

- Review the latest public API definition
- Import the API into Postman
- Generate client SDKs from the OpenAPI spec
- Track changes to the API contract over time
- Report issues or request improvements

## Quick start

1. Read the official documentation at [docs.nexconn.ai/platform-chat-api](https://docs.nexconn.ai/platform-chat-api).
2. Confirm your regional API host from the Base URL guide.
3. Prepare your `App ID` and `App Key`.
4. Generate the required request signature for each server-side request.
5. Import the OpenAPI file or Postman collection from this repository.
6. Start with the access token issuance flow to verify connectivity and authentication.

Example request:

```bash
curl --request POST \
  --url "https://YOUR_API_HOST/v4/auth/access-token/issue" \
  --header "Content-Type: application/json" \
  --header "App-Key: YOUR_APP_KEY" \
  --header "Nonce: RANDOM_STRING" \
  --header "Timestamp: YOUR_UNIX_TIMESTAMP_IN_MILLISECONDS" \
  --header "Signature: YOUR_GENERATED_SIGNATURE" \
  --data '{
    "userId": "demo-user-001",
    "name": "Demo User",
    "avatarUrl": "https://example.com/avatar.png"
  }'
```

## Base URLs

Use the API host for the region where your service is deployed. Refer to the official Base URL guide for the latest regional domains:

- Base URL reference: [https://docs.nexconn.ai/platform-chat-api/prepare-to-use-api/base-url](https://docs.nexconn.ai/platform-chat-api/prepare-to-use-api/base-url)

## Authentication

This API is designed for server-side use and requires signed requests.

Typical headers include:

```http
App-Key: YOUR_APP_KEY
Nonce: RANDOM_STRING
Timestamp: YOUR_UNIX_TIMESTAMP_IN_MILLISECONDS
Signature: GENERATED_SIGNATURE
```

For the exact signing rules and required request parameters, refer to the official authentication overview:

- Authentication guide: [https://docs.nexconn.ai/platform-chat-api/prepare-to-use-api/overview](https://docs.nexconn.ai/platform-chat-api/prepare-to-use-api/overview)

## Open in Postman

Use this repository to explore the API in Postman and test authentication flows.

- Documentation: [https://docs.nexconn.ai/platform-chat-api](https://docs.nexconn.ai/platform-chat-api)

If you prefer importing manually, use the OpenAPI file from this repository and import it into Postman as an API or collection.

## Typical workflow

1. Import the OpenAPI definition into Postman.
2. Create an environment with your API host, app key, nonce, and timestamp variables.
3. Test the access token flow first.
4. Try read-only or low-risk endpoints before production write operations.
5. Keep secrets in private environments and use production credentials only after validation.

## Versioning

We use semantic versioning for API contract changes where possible.

- Patch: non-breaking fixes or clarifications
- Minor: backward-compatible additions
- Major: breaking changes

Breaking changes will be announced in advance whenever possible.

## Support

If you need help, start with the official documentation:

- Docs home: [https://docs.nexconn.ai/platform-chat-api](https://docs.nexconn.ai/platform-chat-api)
- Issues: [GitHub Issues](../../issues)

## Security

Please do not report security vulnerabilities in public issues.

Never commit production credentials, app keys, or signing secrets to this repository.

## Maintained by

This repository is maintained by the API team.

For internal maintainers: use pull requests for contract updates and keep the Postman public workspace in sync with the latest approved OpenAPI definition.
