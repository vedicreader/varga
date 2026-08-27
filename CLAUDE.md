# Working in this repo

nbdev. The notebooks under `nbs/` are the source; `varga/*.py` is generated. Edit the notebook,
run `nbdev_export`, never edit the `.py`. CI runs `nbdev_export` and fails on a diff.

## The two halves

`varga.core` answers "what kind of document is this" from cue phrases and countable evidence.
It needs `fastcore` and `rahasya` and nothing else, and it must stay that way: the point of
`decisive` is that a caller can skip the model.

`varga.schema` answers "what fields does it hold". `structured` needs `rishi`. Import it inside
the function, not at module scope: there are no extras here, so an optional package is one that
is imported when it is used and raises saying what to install.

## Dependencies point one way

`varga` depends on `rahasya`, never the reverse. The honorific regex (`PERSON_HON`) has one
definition, in rahasya, because a name means the same thing to the doctype scorer and to the
privacy gate. `litesearch` is optional and display-only: no doctype score may ever read a
keyphrase.

## The cue table is measured

`DOCTYPES`, `MIN_SCORE`, `MIN_MARGIN` and `KIND_BONUS` are tuned against the documents in the
test cells. Adding a label means adding its own text to `WORK` and proving it wins decisively,
and proving the neutral paragraph still scores under 0.2 against it.

Never reflow `TYPE_SP`. It is a prompt with line continuations; rewrapping it edits what a model
is told.

## Prose in notebooks

Short. Lead with the decision. Numbers instead of adjectives. No em dashes, no bold inside a
paragraph, no rhetorical questions. A rationale longer than three sentences belongs in a
docstring.

## Docstrings and comments

One line. A second sentence only for a measured number or a footgun. Inline comments in a `def`
signature are nbdev docments and become the API parameter table.
