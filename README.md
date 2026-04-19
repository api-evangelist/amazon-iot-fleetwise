# Amazon IoT FleetWise (amazon-iot-fleetwise)
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
