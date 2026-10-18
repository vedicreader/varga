# Release notes

<!-- do not remove -->

## 0.0.6
- Doctypes `id_card`, `passport`, `bank_statement`, `payslip`, `tax_return`, with `sensitive=True`; `clinical_record` is sensitive too
- `SENSITIVE`, and `guess_type(...).sensitive`
- `IdentityDoc` and `Statement` schemas, in `SCHEMAS` for the five new doctypes
- `structured(..., cite=True)` returns `{field: {value, quote}}`; `cite_schema` builds the shape
- `locate(fields, pages)` finds each field's page and block by string match
- README: no `varga[llm]` extra; `rishi` is installed alongside

## 0.0.5
check_fields, iso_date, money, date_order public. keyphrase leg removed, its vruksha import was dead
_split_reasoning is urai's split_think

## 0.0.4
release

## 0.0.3
use urai instead of rishi. lean pass

## 0.0.2
adding the extract template for categorisation

## 0.0.1
varga to classify docs
