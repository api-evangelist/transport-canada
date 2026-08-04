# Transport Canada (transport-canada)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Transport Canada (Transports Canada) is the federal department that regulates aviation, marine, rail and road transportation in Canada under the Aeronautics Act and the Canadian Aviation Regulations. In travel it is the safety-and-security regulator rather than a participant in distribution — it certifies air operators, registers aircraft on the Canadian Civil Aircraft Register, licenses pilots and drone operators, runs the Civil Aviation Daily Occurrence Reporting System (CADORS) and the Air Cargo Security program, and publishes the Canadian airports layer. It sits entirely outside the GDS/NDC distribution chain; airline economic licensing, all-in fare advertising and the Air Passenger Protection Regulations belong to the separate Canadian Transportation Agency. Its API posture is thin but genuinely open — no developer portal exists at tc.canada.ca, developer./developers./docs. subdomains do not resolve, and no OpenAPI is published anywhere. What does exist is real and ungated: a self-describing JSON/XML Vehicle Recalls Database API at data.tc.gc.ca, an ArcGIS REST and OGC WMS service for Canadian airports with air navigation services, and bulk CSV/XML extracts of CADORS, the Air Cargo Security members list and the vessel registers, all indexed through the Treasury-Board-operated open.canada.ca CKAN Action API under the Open Government Licence – Canada. No key, no account, no accreditation, no contract.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/transport-canada/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/transport-canada/refs/heads/main/apis.yml)

## Tags

- Travel
- Canada
- Aviation
- Regulator
- Government
- Airports
- Aircraft Registry
- Aviation Safety
- Drones
- Open Data
- Transportation

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

### Transport Canada Vehicle Recalls Database API

Transport Canada's only first-party public REST API. Returns safety-related recall records for vehicles, tires and child restraints recorded by the Defect Investigations and Recalls Division. The service root is self-describing — GET the application root and it returns the tables (`recall`, `recall-summary`) and the query parameters each accepts (`recall-number`, `make-name`, `manufacturer-name`, `minimum-model-year`, `maximum-model-year`, `year-range`, `model-name`) in both English and French. Path-segment query style, `format=json` or `format=XML`, no API key, no rate limit published. English and French service trees are mirrored at `/eng/` and `/fra/`.

- **Human URL:** [https://open.canada.ca/data/en/dataset/1ec92326-47ef-4110-b7ca-959fab03f96d](https://open.canada.ca/data/en/dataset/1ec92326-47ef-4110-b7ca-959fab03f96d)
- **Base URL:** `https://data.tc.gc.ca/v1.3/api/eng/vehicle-recall-database`

#### Tags

- Recalls
- Vehicle Safety
- Road Transportation
- Open Data

#### Properties

- [Documentation](https://open.canada.ca/data/en/dataset/1ec92326-47ef-4110-b7ca-959fab03f96d)
- [API Reference](https://data.tc.gc.ca/v1.3/api/eng/vehicle-recall-database/?format=json)
- [Service Descriptor](capabilities/transport-canada-vehicle-recalls-api-root.json)
- [Bulk Download — CSV](https://opendatatc.tc.canada.ca/vrdb_full_monthly.csv)
- [Bulk Download — XML](https://opendatatc.tc.canada.ca/vrdb_full_monthly.xml)
- [Data Dictionary](https://opendatatc.blob.core.windows.net/opendatatc/recalls_variables.txt)
- [License — Open Government Licence Canada](https://open.canada.ca/en/open-government-licence-canada)

### Transport Canada Canadian Airports ArcGIS REST API

Queryable Esri ArcGIS REST MapServer (currentVersion 10.81) published by Transport Canada through the Government of Canada geospatial platform, covering Canadian airports served by NAV CANADA control towers or flight service stations. The layer 0 `/query` operation returns JSON features carrying `TC_ID`, `IATA` code, `ICAO` code, airport name, type (Control Tower / Flight Service Station), city, province, latitude and longitude. No key required. French service tree mirrored at the `_fr` path.

- **Human URL:** [https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf](https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf)
- **Base URL:** `https://maps-cartes.services.geo.ca/server_serveur/rest/services/TC/canadian_airports_w_air_navigation_services_en/MapServer`

#### Tags

- Airports
- Aviation
- Geospatial
- Open Data

#### Properties

- [Documentation](https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf)
- [API Reference](https://maps-cartes.services.geo.ca/server_serveur/rest/services/TC/canadian_airports_w_air_navigation_services_en/MapServer?f=json)
- [Service Descriptor](capabilities/transport-canada-airports-arcgis-mapserver.json)
- [Bulk Download — CSV](https://ftp.cartes.canada.ca/pub/tc_tc/Airports_Aeroport/canadian_airports_w_air_navigation_services/Airports_Aeroports.csv)
- [License — Open Government Licence Canada](https://open.canada.ca/en/open-government-licence-canada)

### Transport Canada Canadian Airports OGC WMS

OGC Web Map Service 1.3.0 endpoint for the same Canadian Airports with Air Navigation Services layer. GetCapabilities returns a conformant `WMS_Capabilities` document declaring GetMap, GetFeatureInfo and GetLegendGraphic. This is the one Transport Canada interface that is an actual open standard — any WMS client can consume it and any other WMS server could serve the same layer.

- **Human URL:** [https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf](https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf)
- **Base URL:** `https://maps-cartes.services.geo.ca/server_serveur/services/TC/canadian_airports_w_air_navigation_services_en/MapServer/WMSServer`

#### Tags

- Airports
- Aviation
- Geospatial
- OGC
- WMS

#### Properties

- [Documentation](https://open.canada.ca/data/en/dataset/3a1eb6ef-6054-4f9d-b1f6-c30322cd7abf)
- [WMS Capabilities](capabilities/transport-canada-airports-wms-capabilities.xml)
- [Specification — OGC WMS](https://www.ogc.org/publications/standard/wms/)
- [License — Open Government Licence Canada](https://open.canada.ca/en/open-government-licence-canada)

## Common Properties

- [Website](https://tc.canada.ca/en)
- [Documentation — Civil Aviation](https://tc.canada.ca/en/aviation)
- [Open Data — 49 datasets](https://open.canada.ca/data/en/organization/tc)
- [Bulk Download host](https://opendatatc.tc.canada.ca/)
- [License — Open Government Licence Canada](https://open.canada.ca/en/open-government-licence-canada)
- [Terms of Service](https://www.canada.ca/en/transparency/terms.html)
- [GitHub Organization](https://github.com/tc-ca)
- [Canadian Civil Aircraft Register (CCARCS)](https://wwwapps.tc.gc.ca/saf-sec-sur/2/ccarcs-riacc/RchSimp.aspx) — web search only, no API, no bulk download, 1000-record cap
- [Civil Aviation Daily Occurrence Reporting System (CADORS)](https://wwwapps.tc.gc.ca/saf-sec-sur/2/cadors-screaq/)
- [Dataset — CADORS](https://open.canada.ca/data/en/dataset/a348c1d1-2392-4595-b5e2-c6a244a7e87f)
- [Dataset — Air Cargo Security (ACS) Program Members List](https://open.canada.ca/data/en/dataset/d9391250-c2fa-47ed-9216-aa38eb449aaf)
- [Dataset — Drone Flight School](https://open.canada.ca/data/en/dataset/de913542-af6f-418c-b63f-77bcf2c72393)
- [Open Government CKAN Action API](https://open.canada.ca/en/access-our-application-programming-interface-api) — operated by Treasury Board Secretariat, not Transport Canada

## Switching Cost

Recorded in full in [`review.yml`](review.yml).

| Dimension | Finding |
| --- | --- |
| Interface shape | `standard-plus-proprietary` — OGC WMS 1.3.0 and CKAN Action API 2.8 alongside a bespoke `.NET`-flavoured recalls API with no OpenAPI |
| Second source | `no-alternative` — Transport Canada is the statutory source of record for Canadian aviation registries and occurrences |
| Exit path | `bulk-export-documented` — full CSV/XML dumps for every published dataset, except CCARCS which has none |
| Identifier portability | IATA and ICAO codes, aircraft registration marks, ICAO flight numbers, TSB occurrence numbers — portable throughout |
| Contractual lock-in | Open Government Licence – Canada: worldwide, royalty-free, perpetual, non-exclusive; terminates automatically on breach |
| Access gate | `self-serve` — genuinely unauthenticated, no key, no registration, nothing to sign |
| Distribution model | `not-applicable` — a safety regulator, not a participant in airline distribution |
| NDC posture | Not applicable. IATA authors NDC from Montreal, inside Transport Canada's jurisdiction, and Transport Canada has no role in it |

## Maintainers

- Kin Lane — kin@apievangelist.com
