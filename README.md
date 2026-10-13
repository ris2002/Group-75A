# Breast Tumour Diagnosis: Statistical Analysis in R

Team research project for the MSc Advanced Computer Science at the University of Hertfordshire (module 7COM1079, Team Research and Development Project, Group 75A).

## Research question

Is there a significant difference in mean tumour radius (`radius_mean`) between malignant and benign breast tumours?

## Data

`Cancer_Data_11.csv`: a breast tumour diagnostic dataset with a diagnosis label (M = malignant, B = benign) and measured tumour features.

## Method

1. **Cleaning:** checked for missing values, dropped an empty index column, trimmed and factor-encoded the diagnosis label, converted `radius_mean` to numeric and removed invalid rows.
2. **Exploration:** computed mean, median and standard deviation of `radius_mean` and plotted its distribution as a histogram to check its shape.
3. **Testing:** compared the two groups with a Welch two-sample t-test (`t.test(radius_mean ~ diagnosis)`), which does not assume equal variances.
4. **Visualisation:** boxplot of `radius_mean` by diagnosis.

## Results

| Group | Mean radius_mean |
| --- | --- |
| Malignant | 17.46 |
| Benign | 12.16 |

The t-test gave a very small p-value, so the difference is statistically significant: malignant tumours had a substantially larger mean radius than benign ones.

## Limitations and future work

- Only one feature was tested; tumour size alone cannot replace full clinical diagnosis.
- The data comes from a single source, which limits how far the result generalises.
- Next step: multivariate analysis (for example logistic regression across several tumour features) to see how features combine to predict diagnosis.

## My contribution

<!-- Fill in honestly before publishing, e.g. "Wrote the R analysis script (cleaning, t-test, plots) and drafted the results section." -->

## Files

| File | Contents |
| --- | --- |
| `Script_Final.R` | Full analysis: cleaning, normality check, t-test, plots |
| `Cancer_Data_11.csv` | Dataset |
| `Conclusion.txt` | Written conclusions |
| `7COM1079_Final report Group 75A .docx` | Final group report |
| `Team_Research_Project.Rproj` | RStudio project file |

## How to run

Open `Team_Research_Project.Rproj` in RStudio, load `Cancer_Data_11.csv` as `Cancer_Data_11`, then run `Script_Final.R`. No extra packages are needed (base R only).
