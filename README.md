# Angani Air Loyalty Analytics

A business intelligence project developed during the **Moringa / Angani BI Hackathon (September 2026)**. The project investigates customer engagement and retention in an airline loyalty programme, evaluates a 2018 promotion, and turns the analysis into recommendations through an interactive Power BI decision brief.

## Project objective

The central business question is: **Did the 2018 loyalty promotion generate valuable customer behaviour, and how can the airline improve loyalty and retention?**

The analysis compares members who joined through the 2018 promotion with standard members who joined in the same year, alongside members who joined before 2018. This like-for-like comparison helps separate promotion-cohort behaviour from patterns in the existing member base.

## Key findings

The analysis of the historical hackathon dataset highlighted these patterns:

- The 2018 promotion cohort included **971 members**.
- Promotion members generated more flights per member than standard members who joined in 2018, while cancellation patterns also indicated that early engagement did not guarantee long-term retention.
- Activity among 2018 joiners declined in the months after enrolment, suggesting that the airline should examine what happens when introductory incentives end.
- Members who had redeemed points showed lower churn than members who had never redeemed. This is an observed association, not proof that redemption alone causes retention.
- Behavioural indicators such as engagement and redemption were more useful for exploring retention than broad demographic groupings alone.

These findings describe a historical dataset supplied for the hackathon; they should not be interpreted as current airline performance or causal evidence.

## Business recommendations

1. **Improve the transition after promotional offers.** Test a gradual change in incentives and measure whether engagement is sustained.
2. **Encourage a first redemption.** Make reward eligibility, points balances, and redemption steps clear and achievable.
3. **Monitor early engagement.** Track activity and cancellation patterns in the first months after enrolment to identify when members disengage.
4. **Use behaviour to guide retention activity.** Design and test interventions around engagement and redemption patterns rather than relying only on demographic segments.
5. **Measure impact before scaling.** Use controlled experiments or appropriate comparison groups to evaluate whether an intervention improves retention.

## Power BI dashboard

The final interactive report is included here:

`dashboards/Angani Air Loyalty Decision Brief.pbix`

Open the `.pbix` file with Microsoft Power BI Desktop to explore the report. The dashboard brings the analysis into a decision-focused format, allowing the project findings and recommendations to be reviewed interactively.

## Tools and methods

- **Power BI** — interactive dashboard and business-focused reporting.
- **Python** — reproducible data preparation, cohort analysis, and validation.
- **pandas** — data cleaning, joins, grouping, aggregation, and summaries.
- **NumPy** — derived cohort and analytical fields.
- **openpyxl** — export of Power BI-ready tables to Excel.

The Python workflow builds customer, activity, and calendar tables; standardises records; derives cohort and tenure fields; and checks key totals and data grain before analysis.

## Repository structure

```text
Angani_Air_Loyalty_Analytics/
├── dashboards/
│   └── Angani Air Loyalty Decision Brief.pbix
├── scripts/
│   ├── clean_data.py
│   ├── analyze.py
│   └── validate.py
├── data/
│   └── raw/
│       └── README.md
├── requirements.txt
├── .gitignore
└── README.md
```

## Run the Python workflow

Python 3.10 or later is recommended. Install the dependencies from the repository root:

```bash
pip install -r requirements.txt
```

The source dataset is not included in this repository. Place the authorised source files in `data/raw/` using these filenames:

- `Customer Loyalty History.csv`
- `Customer Flight Activity.csv`
- `Calendar.csv`

Then run the workflow from the repository root:

```bash
python scripts/clean_data.py
python scripts/validate.py
python scripts/analyze.py
```

The cleaning script creates the cleaned tables under `data/cleaned/`. Run validation after cleaning to check the key totals and ensure that the activity table has one record per member per month. Generated data files are excluded from Git by default.

## Limitations

- The dataset is historical and provided for hackathon analysis; it does not represent current airline performance.
- Observed relationships do not establish causation. Recommendations should be tested before implementation.
- The dashboard and scripts are intended to support analysis and decision-making, not to identify individual customers.

## Acknowledgement

Created collaboratively as a team project for the Moringa / Angani BI Hackathon. The project combines data preparation, cohort analysis, validation, Power BI reporting, and business recommendations.
