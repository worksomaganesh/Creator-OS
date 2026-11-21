# Contributing to Creator OS

## Before adding a capability

1. Identify the repeated problem it solves.
2. Check whether the capability belongs in the shared engine or a brand-specific repository.
3. Define inputs, outputs, failure cases, and review requirements.
4. Prefer a documented workflow before adding automation.
5. Include tests or a manual verification procedure.
6. Record dependencies, licences, and security implications.

## Shared vs brand-specific

Put reusable, brand-neutral tooling here. Put editorial decisions, scripts, brand voice, brand assets, and audience-specific strategy in the corresponding brand repository.

A shared skill may accept a brand configuration, but must not silently impose one brand's voice on another.

## Quality expectations

- No fabricated sources, metrics, or claims.
- No secrets or private user/customer data.
- Document external dependencies and licences.
- Keep automation deterministic where possible.
- Log failures and preserve useful diagnostics.
- Require human approval for final publication.

## Change documentation

Update relevant docs and schemas when behaviour or contracts change. Use clear commit messages and keep changes focused.
