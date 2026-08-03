# Amazon IoT FleetWise (amazon-iot-fleetwise)

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

AWS IoT FleetWise is a managed service that makes it easy for automotive manufacturers to collect, transform, and transfer vehicle data to the cloud in near-real time. It provides tools for vehicle data modeling, intelligent data collection, and cloud-based analytics.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/amazon-iot-fleetwise/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Automotive, AWS, Connected Vehicles, IoT, Telematics, Vehicle Data

## Timestamps

- **Created:** 2026-03-16
- **Modified:** 2026-04-19

## APIs

### AWS IoT FleetWise API
The AWS IoT FleetWise API provides access to vehicle data modeling, fleet management, signal catalogs, campaigns, and data collection for connected vehicle platforms.

**Human URL:** [https://aws.amazon.com/iot-fleetwise/](https://aws.amazon.com/iot-fleetwise/)

#### Tags:

 - Automotive, IoT, Vehicle Data

#### Properties

- [Documentation](https://docs.aws.amazon.com/iot-fleetwise/latest/APIReference/)
- [OpenAPI](openapi/amazon-iot-fleetwise-openapi-original.yml)
- [GettingStarted](https://docs.aws.amazon.com/iot-fleetwise/latest/developerguide/getting-started.html)
- [Pricing](https://aws.amazon.com/iot-fleetwise/pricing/)
- [FAQ](https://aws.amazon.com/iot-fleetwise/faqs/)

## Common Properties

- [Portal](https://aws.amazon.com/iot-fleetwise/)
- [Website](https://aws.amazon.com/iot-fleetwise/)
- [Documentation](https://docs.aws.amazon.com/iot-fleetwise/)
- [TermsOfService](https://aws.amazon.com/service-terms/)
- [PrivacyPolicy](https://aws.amazon.com/privacy/)
- [Support](https://aws.amazon.com/premiumsupport/)
- [Blog](https://aws.amazon.com/blogs/iot/tag/aws-iot-fleetwise/)
- [GitHubOrganization](https://github.com/aws)
- [Console](https://console.aws.amazon.com/iotfleetwise/)
- [SignUp](https://portal.aws.amazon.com/billing/signup)
- [Login](https://signin.aws.amazon.com/)
- [StatusPage](https://health.aws.amazon.com/health/status)
- [Contact](https://aws.amazon.com/contact-us/)

## Features

| Name | Description |
|------|-------------|
| Vehicle Signal Catalog | Model vehicle signals using VSS and OEM-specific data dictionaries. |
| Intelligent Data Collection | Collect vehicle data conditionally based on events, time windows, or triggers. |
| Fleet-Wide Campaigns | Deploy data collection campaigns across thousands of vehicles simultaneously. |
| Cloud Analytics | Analyze collected vehicle data using Amazon Timestream and QuickSight. |

## Use Cases

| Name | Description |
|------|-------------|
| OBD Data Collection | Collect and analyze vehicle diagnostic data from CAN bus. |
| Driver Behavior Analysis | Analyze driving patterns for safety scoring and insurance. |
| Predictive Maintenance | Monitor vehicle health and predict maintenance needs. |

## Integrations

| Name | Description |
|------|-------------|
| Amazon Timestream | Stores vehicle time-series telemetry data for analysis. |
| Amazon S3 | Stores raw vehicle data files for batch analytics. |
| AWS IoT Core | Provides connectivity for vehicle data transmission. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [AWS IoT FleetWise API](openapi/amazon-iot-fleetwise-openapi-original.yml)

### JSON Schema

189 schema files covering key resources and operations.

### JSON Structure

189 JSON Structure files converted from JSON Schema.

### JSON-LD

- [Amazon IoT FleetWise Context](json-ld/amazon-iot-fleetwise-context.jsonld)

### Examples

189 example JSON files generated from schemas.

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [AWS IoT FleetWise API](capabilities/shared/iot-fleetwise.yaml) — operations for amazon iot fleetwise management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Vehicle Fleet Management](capabilities/vehicle-fleet-management.yaml) | Amazon IoT FleetWise | 8 | Automotive Engineer, IoT Developer |

## Vocabulary

- [Amazon IoT FleetWise Vocabulary](vocabulary/amazon-iot-fleetwise-vocabulary.yaml) — Unified taxonomy mapping resources, actions, workflows, and personas

## Rules

- [Amazon IoT FleetWise Spectral Rules](rules/amazon-iot-fleetwise-spectral-rules.yml) — 14 rules across 6 categories enforcing Amazon IoT FleetWise API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
