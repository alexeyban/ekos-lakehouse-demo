---
title: "Business description"
order: 10
ekos_generated: true
---

# Business description

## Purpose

<!-- ekos:manual id="business-purpose" -->
_Why this data product exists: the decisions it supports and for whom._
<!-- /ekos:manual -->

## Scope

<!-- ekos:manual id="business-scope" -->
_What is in scope._

**Out of scope:** _What is deliberately not covered._
<!-- /ekos:manual -->

## Source system

<!-- ekos:manual id="business-source" -->
Pagila, the DVD-rental sample database for PostgreSQL, loaded into the sandbox's lh-postgres by deploy/fixtures/pagila.sh (pinned to commit 9baf49c, checked by SHA-256). Used here as the demo source; it is not a production system.
<!-- /ekos:manual -->

The pipeline reads **16 tables** from PostgreSQL 18 (Pagila) (Trino catalog `pagila`).

## Owners and stakeholders

<!-- ekos:manual id="business-raci" -->
_Data owner, data steward, technical owner, approvers of gold marts (stakeholder + data engineer, RFC 0195)._
<!-- /ekos:manual -->

## Consumers

<!-- ekos:manual id="business-consumers" -->
_Reports, dashboards, applications and teams that read the gold marts._
<!-- /ekos:manual -->

## Business questions answered (gold marts)

_No gold mart descriptions yet. A stakeholder writes one in `marts/<name>.md`; `lakehouse gold draft` turns it into a proposal._
