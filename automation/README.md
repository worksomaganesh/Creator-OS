# Automation

Automate only after a workflow is understood and its outputs can be checked.

Candidate utilities: content ID generator, content package validator, source-register validator, asset-manifest validator, subtitle/transcript QA, export metadata checker, publishing-package generator, analytics report builder.

Engineering requirements: document setup and usage; validate inputs; produce actionable errors; log without leaking secrets; provide dry-run modes for file operations; never delete source media by default; include tests and safe fixtures; do not automate publishing without explicit human approval.
