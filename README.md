# IMDb Movies Analysis

Exploratory data analysis of the IMDb movies dataset (`ggplot2movies`) in Python: how the film industry evolved, whether budget predicts quality, which genres rate highest, and which films divide audiences most.

This was a course project for *Python for Data Analysis* at the Faculty of Information Technology, Polytechnic University of Tirana. **The notebook is written in Albanian**; this README summarizes it in English. Authors are listed in the notebook.

## Dataset

- Source: `ggplot2movies` (Wickham, 2008), aggregated from IMDb.com
- 58,788 films, 24 columns, release years 1893 to 2005
- File: `movies_imdb.csv`
- Missing data: about 91% of films have no budget and about 92% have no MPAA rating. These were handled with selective filtering rather than imputation, since the gaps are systematic (older films, documentaries, independent and non-US productions) and imputing would distort the economic analysis.

## Questions

1. How did the film industry change from the 1920s to the 2000s (volume, length, average rating, budget)?
2. Does a bigger budget mean a better rating?
3. Which genres are rated highest and lowest?
4. Which films split audiences into extreme camps (custom polarization index)?

## Key findings

- **Budget and quality:** the Pearson correlation between log(budget) and rating is r = -0.079, practically zero. Higher budgets do not translate into higher ratings in this dataset.
- **Genres:** Short, Animation and Documentary have the highest average ratings (above 6.9). Action has the lowest (5.42).
- **Polarization:** the most polarizing films tend to have low average ratings but a passionate fan base (for example Troll 2 and Manos: The Hands of Fate).
- **Industry evolution:** production grew sharply after 1980, and budgets grew about 25 times from the 1920s to the 1990s.

Limitations: the dataset ends in 2005, budget and MPAA data are largely missing, and IMDb voters are not a representative audience.

## Repository contents

| File | Description |
|---|---|
| `Analiza_Filmave_IMDb.ipynb` | Executed notebook: cleaning, analysis and charts (in Albanian) |
| `movies_imdb.csv` | The dataset |
| `requirements.txt` | Python dependencies |

## Run it

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook Analiza_Filmave_IMDb.ipynb
```

The notebook reads `movies_imdb.csv` from the same folder, so start Jupyter from the repository root.

## Tools

Python 3, pandas, numpy, matplotlib, Jupyter Notebook.