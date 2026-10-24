# calwright

CSV to RFC 5545 iCalendar converter and validator.

## Language

**Event**:
A scheduled calendar occurrence or recurring series converted from a CSV row.
_Avoid_: Entry, record, appointment

**Recurrence Rule**:
The RFC 5545 specification defining how an event repeats over time.
_Avoid_: Repeat rule, recurrence pattern

**Exception Date**:
A specific date or datetime explicitly excluded from a recurring event series.
_Avoid_: Excluded date, skipped date, cancellation
