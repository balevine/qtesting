# Similarity calculations: run 1 vs. run 2

Both runs score the same 250 Q-DO support tickets. Each figure below is the **mean per-ticket Jaccard similarity** between the human label set and Jev's label set. Urgency and Sentiment are not included.

## Method

For each ticket, take the human's set of labels (H) and Jev's (J):

**Jaccard = |H ∩ J| / |H ∪ J|**

That is the number of labels both chose, divided by the number of distinct labels either chose. It is 1.0 for a perfect match and 0 when they share nothing. The reported figure is the plain average of the 250 per-ticket scores.

What goes into each set:

- **Run 1:** the answer to run 1's single multi-select question. Each label combines a product area and an issue type (e.g. `SYNC_BUG`), or is a standalone label (`NOT_SUPPORT`, `NO_ISSUE`, `UNCLEAR`).
- **Run 2, three separate labels:** the answers to Issue, Product-Area and Platform, with NONE left out. Each answer is tagged with its question, so Product-Area's NONE can't match Platform's NONE.
- **Run 2, combined the run-1 way:** Product-Area and Issue joined into one label like `SYNC_BUG` (just the Issue when it's NOT_SUPPORT, NO_ISSUE, UNCLEAR or SPAM, or when Product-Area is NONE). Platform is left out. This is the like-for-like comparison with run 1.

## Run 1: 0.692

| Per-ticket Jaccard | Tickets | Contribution | Example (human → Jev) |
|---|---|---|---|
| 1 | 126 | 126.000 | #2: {TASKS_LISTS_FEATURE_REQUEST} → same |
| 1/2 | 87 | 43.500 | #1: {TASKS_LISTS_BUG} → {TASKS_LISTS_BUG, APP_PLATFORM_BUG} |
| 1/3 | 8 | 2.667 | #47: {SYNC_FR} → {TASKS_LISTS_FR, SYNC_FR, APP_PLATFORM_FR} |
| 1/4 | 3 | 0.750 | #24: {ARCHIVE_SEARCH_EXPORT_BUG} → 4 labels including it |
| 0 | 26 | 0.000 | no labels in common |
| **Total** | **250** | **172.917** | |

**172.917 ÷ 250 = 0.6917**

In run 1, 98 tickets got partial credit (1/2, 1/3 or 1/4). Each of the examples above is Jev adding extra labels next to the right one.

## Run 2, three separate labels: 0.896

| Per-ticket Jaccard | Tickets | Contribution |
|---|---|---|
| 1 | 200 | 200.000 |
| 2/3 | 20 | 13.333 |
| 1/2 | 10 | 5.000 |
| 1/3 | 14 | 4.667 |
| 1/4 | 4 | 1.000 |
| 0 | 2 | 0.000 |
| **Total** | **250** | **224.000** |

**224 ÷ 250 = 0.896**

Example of one step: the human chooses BUG / SYNC / NONE and Jev chooses BUG / TASKS_LISTS / NONE. That gives {issue:BUG, productArea:SYNC} ∩ {issue:BUG, productArea:TASKS_LISTS} = 1 shared label out of 3 distinct, so **1/3**.

## Run 2, labels combined the run-1 way: 0.848

Each ticket has exactly one combined label on each side, so every ticket scores either 1 or 0:

**212 matches × 1 + 38 mismatches × 0 = 212; 212 ÷ 250 = 0.848**

So here the Jaccard score is the same as exact-match accuracy on area + issue.

## Notes

- **The two run-2 figures differ because of the metric.** Three separate labels give partial credit (a wrong Product-Area still leaves Issue matching) and add Platform, which run 1 never asked. Use 0.848 when comparing with run 1's 0.692.
- **Empty sets never occur.** Issue is mandatory in run 2, and no ticket in either run has an empty label set on both sides. So the question of how to score two empty sets (1 in Qval, 0 in scikit-learn by default) never comes up.
- **Data files:** `run-1/qval-output/tickets-20261003-192529.qval.json` and `run-2/qval-output/tickets-20261003-192529.qval.json`. The per-ticket formula matches Qval's own `jaccard()` in `lib/aggregate.mjs`.

## References

- **[Jaccard index, Wikipedia](https://en.wikipedia.org/wiki/Jaccard_index)**: the definition (|A ∩ B| / |A ∪ B|), its history, and how it relates to other set-similarity measures. The best general introduction.
- **[`sklearn.metrics.jaccard_score`, scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.jaccard_score.html)**: the standard implementation for checking these numbers. This method is `average='samples'`, which the docs describe as "calculate metrics for each instance, and find their average." Same formula, but scikit-learn scores two empty sets as 0 by default rather than 1.
