# Stats Counters Draft Guide

This draft folder includes ready-to-test variables for dynamic stats counters.

## Files

- `variables.json`: Active draft payload used by the local draft flow.
- `variables.stats-counters.example.json`: Minimal isolated example for stats-only payload authoring.

## Variable paths consumed by valueInstructions

- `statsCounters.visits.target`
- `statsCounters.visits.durationMs`
- `statsCounters.visits.formatMode`
- `statsCounters.visits.formatPrefix`
- `statsCounters.visits.formatSuffix`
- `statsCounters.cta.target`
- `statsCounters.cta.durationMs`
- `statsCounters.cta.formatMode`
- `statsCounters.cta.formatPrefix`
- `statsCounters.cta.formatSuffix`
- `statsCounters.avgTime.target`
- `statsCounters.avgTime.durationMs`
- `statsCounters.avgTime.min`
- `statsCounters.avgTime.max`
- `statsCounters.avgTime.formatMode`
- `statsCounters.avgTime.formatPrefix`
- `statsCounters.avgTime.formatSuffix`

## Supported format modes

- `number`: Locale-formatted integer, appending `formatSuffix` when provided.
- `suffix`: Integer + suffix (for example `s`).
- `percent`: Integer + `%`.
- `prefix`: Prefix + locale-formatted integer (for example `+1,240`).
- `prefixSuffix`: Prefix + locale-formatted integer + suffix (for example `+1,240%`).

## Fallback chain at runtime

1. `variables.statsCounters.*`
2. QuickStats host fallback signals
3. Analytics/local fallback

Average time can be clamped with optional `statsCounters.avgTime.min` and `statsCounters.avgTime.max`.
If omitted, defaults are `0..999999`.
