# Agility CMS GraphQL API

Source: https://agilitycms.com/docs/developers/graphql-api

## Overview

Agility CMS provides a GraphQL API for fetching content from the Content area of your instance. The GraphQL API offers a flexible query interface as an alternative to the REST Content Fetch API.

## Limitations

- Fetching Pages, Page Templates, or Page Modules is not currently supported via GraphQL.
- GraphQL is limited to content (items and lists) queries only.

## Access

The GraphQL IDE is accessible from within your Agility instance:

1. Navigate to **Settings > API Keys**
2. Click **Explore GraphQL API**

## Authentication

Include your API Key as a request header with each GraphQL query:

- **Fetch API Key**: Use for published (production) content
- **Preview API Key**: Use for draft/staging content

Both keys are available under **Settings > API Keys** in the Agility dashboard.

## Endpoint

The GraphQL endpoint is instance-specific and tied to the instance GUID. The pattern is:

```
https://api.aglty.io/{guid}/{fetch|preview}/{locale}/graphql
```

Regional variants are also available:
- US (default): `https://api.aglty.io/{guid}/...`
- Canada: `https://api-ca.aglty.io/{guid}/...`
- EU: `https://api-eu.aglty.io/{guid}/...`
- Australia: `https://api-aus.aglty.io/{guid}/...`

The GraphQL IDE (Altair) is accessible from within your Agility instance under **Settings > API Keys > Explore GraphQL API**.

## Use Cases

- Querying specific content items by reference name
- Fetching lists of content with filtering and sorting
- Requesting only the fields needed (avoids over-fetching compared to REST)

## Related APIs

- **Content Fetch API (REST)**: `https://api.aglty.io/{guid}/{apitype}` — full REST API including pages and sitemaps
- **Content Sync API**: Bulk sync for build-time workflows
- **Content Management API**: Programmatic content creation and updates
