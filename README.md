# Open Education Data Dashboard

Public-facing Open Education impact dashboard for Midlands Technical College, hosted at [mtc-open.github.io/oer-dashboard](https://mtc-open.github.io/oer-dashboard/) and suitable for embedding in LibGuides.

## Public repository files

- `index.html`: dashboard page and display logic.
- `data/dashboard-data.json`: aggregate dashboard data.
- `README.md`: public documentation.

Keep source workbooks, survey exports, student records, updater scripts, local instructions, archives, backups, and build receipts out of this public repository.

## Private preparation and publishing

The local `update_dashboard_data.py` reads **Master Data for Dashboard.xlsx directly**. The old dashboard workbook and Power Query intermediary are no longer required.

Additional private inputs are the Summer 2026 survey response export and the institutional course-success report containing final registration records.

1. Save the current master workbook in Excel so calculated values are up to date, then close it.
2. In the private **For Publishing** folder, run `python update_dashboard_data.py`. The updater locates the master and supporting reports in the established program folders.
3. Review the generated `release` folder through a local web server. Check totals, survey periods, response-rate notes, and all four Student Success Case Studies.
4. Publish `release/index.html` as repository-root `index.html` and `release/data/dashboard-data.json` as `data/dashboard-data.json`. Publish both together when page behavior or the data format changes.
5. Update this README when the workflow changes.
6. Check the GitHub Pages deployment and the live dashboard and LibGuide embed.

Only the contents of `release` belong in the public dashboard package. Do not upload the whole private publishing folder.

The updater validates course rosters, implementation status, section keys, enrollment reconciliation, and savings arithmetic. It checks source hashes before and after reading and prepares aggregate public data without modifying the original workbooks. Preparation alone does not publish anything.

## Impact and projected growth

Actual savings, enrollment, and section counts include eligible fully deployed courses beginning with their recorded full-rollout term. Enrollments are course registrations, not unique students.

The implementation pipeline includes fully deployed, pilot, and development courses. Projected growth includes **both pilot and development courses**, multiplied by the existing average savings per fully deployed course with recorded impact. This is a projection separate from actual savings and does not estimate future section-level enrollment.

Savings are estimates based on recorded textbook-cost baselines, including default baselines where used. They are gross avoided textbook costs; printing and ancillary costs are not deducted.

The academic-year impact view combines Fall, Spring, and Summer. The Course-Level Impact page shows verified impact for the selected term or academic year.

## OER Student Perceptions

Survey results are separate from actual savings calculations. The survey impact-period control offers Spring 2026, Summer 2026, and all survey periods, with department, discipline, and course filters.

- Spring contains 1,171 response records.
- Summer contains 753 valid response records after four explicit test submissions are excluded.
- Combined results contain 1,924 response records; these are not unique students.
- Positive agreement percentages use valid item responses, not a mean score divided by five.
- Small filtered groups with fewer than ten responses are suppressed.
- Summer quality questions concern usefulness, clarity, and relevance; Spring questions concern overall textbook quality. The dashboard identifies this wording difference.
- “Experienced barriers due to textbook costs” reflects reporting cost-related consequences.
- The executive overview's cost-barrier figures combine both survey periods.

### Estimated response rates

Survey enrollment matching uses final institutional registration records for **all surveyed sections, including pilots**, rather than the savings-eligible footprint.

The estimated rate divides matched response records by enrollment records in those same sections. Each matched section enters the denominator once; this is not an average of section rates.

| Period | Matched responses | Enrollment records | Matched sections | Estimated rate | Unmatched responses |
| --- | ---: | ---: | ---: | ---: | ---: |
| Spring 2026 | 1,168 | 3,772 | 175 | 31.0% | 3 |
| Summer 2026 | 739 | 2,237 | 107 | 33.0% | 14 |
| All survey periods | 1,907 | 6,009 | 282 | 31.7% | 17 |

Unmatched responses remain in survey findings and are excluded only from response-rate calculations. Final registration records do not establish invitation coverage, and repeat submissions may occur. One Summer section has more response records than enrollment records. These rates are estimates, and the dashboard shows the matching basis. Department and course filters do not recalculate the overall period response rate.

## Student Success Case Studies

Preserve the original language and reported results for all four case studies: **AHS 102, PSY 201, SOC 101, and MAT 120**. The case-study results are retained as originally published rather than recalculated by the current-data updater.

## Troubleshooting

If charts or figures are blank, confirm that both public dashboard files are present at the correct paths, open the [public JSON](https://mtc-open.github.io/oer-dashboard/data/dashboard-data.json), and hard-refresh the [dashboard](https://mtc-open.github.io/oer-dashboard/).

If numbers differ from a workbook total, check the source date, current implementation status, rollout eligibility, enrollment scope, and textbook-cost assumptions. Survey enrollment denominators deliberately include pilot sections; actual savings do not.

