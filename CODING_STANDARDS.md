# Coding Standards

Judgement calls and repo conventions consulted during code review.

## Architecture & Dependencies

- **Standard library only**: calwright must have zero runtime dependencies beyond Python's standard library.
- **Python 3.9+ compatibility**: All code must run on Python 3.9 through 3.12 without version-specific syntax breaks.

## Date & Time Handling

- **Centralized property formatting**: When emitting date or datetime lines in RFC 5545 (`DTSTART`, `DTEND`, `EXDATE`, etc.), use or extend unified formatting helpers (`_format_prop_datetime`) instead of repeating property-specific type cascades (`if all_day ... elif tzid ... else`).
- **Delimiter-aware list parsing**: When parsing comma-separated fields containing dates, use helper functions that preserve date formats with internal commas (e.g. `Nov 02, 2026`) rather than naive splitting.

## Errors & Validation

- **Row-tagged errors**: Collect errors on `Event.errors` with clear, human-readable explanations including the row number for `--check`.
- **Fail fast**: Never return synthetic or silently corrupted calendar data when an input date fails to parse.
