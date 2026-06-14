# Agility CMS FinOps

Financial operations guidance for managing Agility CMS costs effectively.

Source: https://agilitycms.com/product/pricing

## Pricing Model

Agility CMS uses fixed-price subscription billing that scales with team size and number of sites — not API call volume. This means:

- **No per-API-call charges**: All plans include unlimited API requests.
- **No bandwidth overages billed by request**: Bandwidth is pooled per plan tier.
- **Predictable monthly costs**: Fixed tiers make budgeting straightforward.

## Plan Cost Summary

| Plan | Monthly (annual) | Users | Content Entries | Asset Storage | Bandwidth |
|------|-----------------|-------|-----------------|---------------|-----------|
| Free | $0 | Limited | Limited | Limited | Limited |
| Starter | $1,425 | 10 | 50,000 | 1 TB | 1 TB/mo |
| Pro | $2,850 | 25 | 250,000 | 5 TB | 2 TB/mo |
| Enterprise | $5,000+ | 50+ | 500,000+ | 20 TB | 15 TB+/mo |

## Cost Optimization Strategies

### Leverage CDN Caching
CDN-cached responses do not count toward rate limits and reduce origin load. Structure content delivery to maximize cache hit rates, particularly for public-facing content that does not change frequently.

### Right-size Your Plan
- Start with the Starter plan if you have a single site and a team under 10 users.
- Upgrade to Pro when you need multiple sites, SSO, or custom roles — not just when you approach entry limits.
- Use the free tier for development, staging, or low-traffic proof-of-concept projects.

### Use Content Sync API for Builds
The Content Sync API pulls all content in bulk at build time. This is more cost-efficient than repeated REST fetch calls and eliminates runtime API dependency for statically generated sites (Next.js, Astro, Gatsby).

### Monitor Content Entry Usage
Content entry limits are the most likely scaling trigger between tiers. Audit unused or duplicate content models regularly to stay within plan limits and avoid unplanned upgrades.

### Annual vs Monthly Billing
Agility CMS publishes annual billing rates. Confirm with sales whether month-to-month billing is available and at what premium, especially for projects with uncertain timelines.

## Budgeting Notes

- Enterprise pricing starts at $5,000/month but may be negotiated based on volume, number of properties, and contract length.
- SSO and SLA features are only available on Pro and Enterprise, which may affect compliance cost planning.
- Asset storage and bandwidth overages should be clarified with Agility CMS sales before signing, as the published pricing does not list overage rates.
