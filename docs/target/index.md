---
title: "Target"
order: 40
ekos_generated: true
---

# Target

The target is a medallion lakehouse of Apache Iceberg tables.

| Layer | Objects | Page |
|---|---|---|
| Bronze | 16 tables | [Bronze](../target/bronze.md) |
| Silver | 16 models, 0 snapshots | [Silver](../target/silver/index.md) |
| Gold | 0 marts | [Gold](../target/gold/index.md) |

```mermaid
flowchart LR
  bronze_bronze_public["bronze: bronze_public<br/>16 object(s)"]
  silver_public["silver: public<br/>16 object(s)"]
  source_public["source: public<br/>16 object(s)"]
  bronze_bronze_public --> silver_public
  source_public --> bronze_bronze_public
```
