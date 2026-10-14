# Country-name matching: Niger and Nigeria

The sentences below are **synthetic examples**, written to explain a rule in the archived R code. They are not research records or an accuracy evaluation.

| Input text | Naive `Niger` match | Archived `Niger(?!ia)` rule |
|---|---:|---:|
| Officials discussed Nigeria. | 1 | 0 |
| Officials discussed Niger. | 1 | 1 |
| Niger and Nigeria were discussed. | 2 | 1 |

The negative lookahead `(?!ia)` prevents a match when “Niger” is immediately followed by “ia”. The rule appears in [the v4 working draft](country-labeling/Labeling%20country%20names%20v4.qmd).

```r
texts <- c("Officials discussed Nigeria.",
           "Officials discussed Niger.",
           "Niger and Nigeria were discussed.")
vapply(gregexpr("Niger(?!ia)", texts, perl = TRUE),
       function(matches) sum(matches > 0), integer(1))
# 0 1 1
```

The full draft counts matches across the country dictionary and chooses the country with the highest count. A tie produces `0`. This example isolates one matching rule; it does not reproduce the full labeling pipeline. Country mentions alone do not necessarily identify a document's main subject, and this rule is not a general solution to ambiguous names.
