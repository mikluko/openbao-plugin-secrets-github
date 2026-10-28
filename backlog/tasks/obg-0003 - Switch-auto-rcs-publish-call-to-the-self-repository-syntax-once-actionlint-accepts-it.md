---
id: OBG-0003
title: >-
  Switch auto-rc's publish call to the $/ self-repository syntax once actionlint
  accepts it
status: To Do
assignee: []
created_date: '2026-10-28T17:16:00Z'
labels:
  - ci
dependencies: []
priority: low
ordinal: 3000
---

## Description

<!-- SECTION:DESCRIPTION:BEGIN -->
auto-rc.yml calls publish.yml as uses: ./.github/workflows/publish.yml with a zizmor ignore[self-repository]. GitHub's $/ form (GA July 2026) is what zizmor prefers, but actionlint 1.7.12, pinned in the shared rknightion/.github actionlint reusable, rejects it as an invalid reusable workflow call. Once the shared reusable pins an actionlint release that parses $/, switch the call and drop the ignore.
<!-- SECTION:DESCRIPTION:END -->

## Acceptance Criteria
<!-- AC:BEGIN -->
- [ ] #1 auto-rc.yml uses $/.github/workflows/publish.yml with no zizmor ignore[self-repository]
- [ ] #2 actionlint and zizmor CI checks both pass on the change
<!-- AC:END -->

## Definition of Done
<!-- DOD:BEGIN -->
- [ ] #1 just check passes (fmt-check, lint including go vet -tags integration, verify-no-vault-sdk, audit, test)
- [ ] #2 a red `just audit` may be a newly published stdlib CVE, not this change -- check before assuming a regression
- [ ] #3 just fmt-check passes, including just --fmt --check
<!-- DOD:END -->
