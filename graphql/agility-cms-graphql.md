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

The GraphQL endpoint is instance-specific and accessed through the Agility dashboard. No single public endpoint URL is published; each instance has its own GraphQL endpoint tied to its GUID.

## Use Cases

- Querying specific content items by reference name
- Fetching lists of content with filtering and sorting
- Requesting only the fields needed (avoids over-fetching compared to REST)

## Related APIs

- **Content Fetch API (REST)**: `https://api.aglty.io/{guid}/{apitype}` — full REST API including pages and sitemaps
- **Content Sync API**: Bulk sync for build-time workflows
- **Content Management API**: Programmatic content creation and updates
