# Release notes

<!-- do not remove -->

## 0.0.8

- A boolean field reads `True`/`False`, the integers 1 and 0, and the strings `fastcore.str2bool` accepts (y/yes/t/true/on/1 and n/no/f/false/off/0, any case). `None` and blank strings are missing values with no error. Any other value becomes blank with an error that keeps the original value. Before, the value was kept as it came.
- The schema table documents that `None` in a string field stays `None` as a missing value.
- Money parsing validates grouping, including lakh grouping. Non-finite and excessively large numbers are rejected.
- String fields stringify numbers. Dicts and sets become blank with an error.
- Unreadable line-item money and quantity values become blank with an error.

## 0.0.7
- `structured`'s JSON fallback works without urai, which varga does not depend on: it reads the reply text, strips `<think>` reasoning and takes the last ```json fence itself. CI failed on this.

## 0.0.6
- Document types `id_card`, `passport`, `bank_statement`, `payslip` and `tax_return`, with `sensitive=True`. `clinical_record` is sensitive too.
- `SENSITIVE` and `guess_type(...).sensitive`.
- `IdentityDoc` and `Statement` schemas, in `SCHEMAS` for the five new document types.
- `structured(..., cite=True)` returns `{field: {value, quote}}`. `cite_schema` builds the schema for it.
- `locate(fields, pages)` finds the page and block of each field by string match.
- README: there is no `varga[llm]` extra. Install `rishi` separately.

## 0.0.5
`check_fields`, `iso_date`, `money` and `date_order` are public. The keyphrase part of the scorer is removed, because its vruksha import was dead.
`_split_reasoning` is `split_think` of urai.

## 0.0.4
release

## 0.0.3
Use urai instead of rishi.

## 0.0.2
Add the extract template for categorisation.

## 0.0.1
varga classifies documents.
