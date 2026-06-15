---
name: Teck.Cloud
description: .NET 10 microservices — business logic. Clean architecture with Basket, Catalog, Customer, Device, Location, Order, Product, Statistic services and YARP/Admin/Aggregate gateways.
slug: teck-cloud
owner: cto
homepage: https://github.com/Teck-Lab/Teck.Cloud
metadata:
  sources:
    - kind: github-dir
      repo: Teck-Lab/Teck.Cloud
      path: /
  stack:
    - .NET 10
    - Entity Framework Core
    - Clean Architecture
    - xUnit
    - PostgreSQL (CNPG)
    - Redis
    - RabbitMQ
---

# Teck.Cloud

Backend microservices for the Teck platform.

## Services

| Service | Image | Description |
|---------|-------|-------------|
| Basket API | `basket-api` | Shopping basket management |
| Catalog API | `catalog-api` | Product catalog and search |
| Customer API | `customer-api` | Customer profiles and management |
| Device API | `device-api` | Device tracking and management |
| Location API | `location-api` | Geolocation and address services |
| Order API | `order-api` | Order processing and fulfillment |
| Product API | `product-api` | Product management and inventory |
| Statistic API | `statistic-api` | Analytics and reporting |
| Image Generator | `image-generator` | Image processing and generation |

## Gateways

| Gateway | Image | Description |
|---------|-------|-------------|
| YARP Gateway | `yarp-gateway` | Public-facing API gateway |
| Admin Gateway | `admin-gateway` | Internal admin gateway |

## Conventions

- Clean architecture: Domain → Application → Infrastructure → API
- Capability-first folders: `{Capability}/Features/{UseCase}/V1`
- Migration projects for all three providers (MySql, PostgreSQL, SqlServer)
- Container image tags: `sha-{7-char-hash}` format
- Service names: `kebab-case`
