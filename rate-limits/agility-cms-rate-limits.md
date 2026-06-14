# Agility CMS Rate Limits

Source: https://agilitycms.com/docs/developers/content-fetch-api

## Content Fetch API (REST)

The Agility CMS Content Fetch API enforces rate limits on direct (non-cached) API requests.

### Request Throttling

- **Limit**: 10 direct requests per 1 second per instance
- **Exceeded response**: HTTP 429 Too Many Requests
- **Timeout limit**: 30 seconds per request; returns HTTP 408 if exceeded

### CDN Cache Behavior

CDN-cached responses do not count toward rate limits. Agility CMS delivers content via a global CDN, so most fetch requests will be served from cache and are not subject to the 10 req/s throttle.

- **US (default)**: `https://api.aglty.io`
- **Canada**: `https://api-ca.aglty.io`
- **Europe**: `https://api-eu.aglty.io`
- **Australia**: `https://api-aus.aglty.io`

## GraphQL API

No specific rate limit figures are published for the GraphQL API. It is accessed through the instance dashboard (Settings > API Keys > Explore GraphQL API) and uses the same Fetch API Key for authentication. Assume similar throttling characteristics as the REST Fetch API.

## Content Management API

No specific rate limit figures are published for the Content Management API. Contact Agility CMS support for management API rate limit details.

## Best Practices

- Rely on CDN-cached responses wherever possible to avoid hitting the direct request throttle.
- Implement exponential backoff when receiving HTTP 429 responses.
- Use the Content Sync API for build-time workflows to pull all content at once rather than making repeated fetch calls.
- Keep individual request durations well under the 30-second timeout to avoid HTTP 408 errors.
