# SailPoint V3 Search Rest Collector

## **About This Pack**

----

The /v3/search endpoint in the SailPoint IdentityNow API allows you to query a variety of object types, but specifically for events, you can retrieve audit or system activity logs that track changes, actions, and processes within your Identity Security Cloud environment
 The following objects are searchable: identities, roles, access profiles, entitlements, events, and account activities.

[SailPoint API Docs](https://developer.sailpoint.com/docs/api/v3/search)

## **Usage**

---
1. Configure Variables:
Within the Pack > Knowledge > Variables 

    - **datatype-events:**

    - **datatype-identities:**

    - **client_id:**

    - **endpoint_host:**

2. Configure Secret:
Within the Pack > Sources > Rest > _vct_rest_sailpoint_v3_search > Configure as json > Click back to configure > enter client_secret

3. Configure Destination:
Within the Pack > Destinations

4. Adjust Route:
Current route uses default:default Destination

## **Authors**

---

Andrew Hendrix - Andrewh@VisiCoreTech.com

Paul Stout - Paul@VisiCoreTech.com

Brian Yearwood - byearwood@cribl.io

## **Release Notes**

---

Version 1.1.2 - 2026-08-23
  - Events Collector: Incremental collection - the search query now filters on created time using scheduled collection state tracking, so each run only pulls events created since the last run.
  - Events Collector: Changed pagination from response body (searchAfter cursor) to request offset (offset/limit parameters, 1000 per page) and enabled stop on empty results.
  - Events Collector: Sort changed from id to +created to support the state tracking watermark.
  - Events Collector: Added latest: now to the schedule time range and removed the hardcoded limit/count query string from the collect URL.

Version 1.1.1 - 2026-02-19
  - Events Collector fix: Resolved a connection failure caused by a missing top-level domain (.com) in the authentication URL.
  - Location: LoginUrl configuration.

Version 1.1.0 - 2025-12-03
  - Pagination Support
  - Added identities Rest Source
  - Updated Collect Post Body
  - Updated DataType Variables 

Version 1.0.0 - 2025-10-21
  - Initial release

## **Contributing to the Pack**

---

To contribute to this Pack, or to report any issues or enhancement requests, please contact us at <CriblPacks@VisiCoreTech.com>

## **License**

---

This Pack uses the following license: [`Apache 2.0`](https://github.com/criblio/appscope/blob/master/LICENSE).