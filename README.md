QSS Final Project

Project Summary: I am pursuing a final project analyzing the impact of whether a country has a state-sponsored religion on intrastate violence. I may also extend my project to divide the world’s main five religions into different metrics based on literature in the field, and see if any of those specific metrics are tied to conflict within a state. I am curious about the overlap between ideology, government control, and violent protests and other forms of conflict in response. My project revolves around three main questions. The first question is whether there is a correlation between whether a country has a state-sponsored religion and how much internal conflict that country experiences. The second question considers the metrics that make up the dominant world religions and considers whether certain metrics are more heavily tied to conflict. The third question that I may want to look at is in countries with state-sponsored religions, comparing governments who are more and less tolerant of other religious groups, is there a significant difference in internal conflict. Providing answers to these questions would act as a strong first step to evaluating the influence of government support of religion on stability and conflict within countries’ borders.

Code:

I have two scripts in my code file. I have a "data_pull_and_clean" script and a "data_analyze" script. The first one imports my code, cleans it, and then merges my datasets together to represent the information I need to make my analyses and draw conclusions. The second script analyzes this data and creates visualizations, which are then stored in my output folder.

Script #1
[00_data_pull_and_clean.ipynb](code/00_data_pull_and_clean.ipynb)
**Input:**
- `data/Violence Data.xlsx` — Uppsala Conflict Data Program intrastate conflict dataset
- `data/state_religions.xlsx` — QoG State Religion Dataset
- `data/religious_data.csv` — Pew Research Center Global Religious Composition Dataset

**What it does:**
- Cleans each dataset independently, filtering and renaming relevant columns
- Merges all three datasets using fuzzy string matching (80% similarity threshold) to reduce missingness from country name inconsistencies
- Constructs a religion trait scores table ranking major religions on five dimensions (hierarchy, exclusivity, collectivism, political theology, pluralism tolerance) on a 1-5 scale based on the literature
- Merges trait scores onto the final dataset

**Output:** `data/final.csv`

---

Script #2
[01_data_analyze.ipynb](code/01_data_analyze.ipynb)
**Input:** `data/final.csv`

**What it does:**
- Produces a regional bar chart comparing median intrastate conflict deaths by state religion status across four regions
- Computes Pearson correlations between religion trait scores and log-transformed intrastate conflict deaths among state-religion countries
- Produces a correlation bar chart visualizing the trait findings

**Output:**
- `output/final_regions.png` — Regional conflict deaths by state religion type
- `output/final_traits.png` — Religion trait correlations with intrastate violence

## Data Sources
- **Uppsala Conflict Data Program (UCDP):** [ucdp.uu.se](https://ucdp.uu.se/downloads/) — intrastate conflict data 1989-2024
- **Quality of Government (QoG) State Religion Dataset:** [gu.se/en/quality-government](https://www.gu.se/en/quality-government) — country-level state religion classifications
- **Pew Research Center Global Religious Composition:** [pewresearch.org](https://www.pewresearch.org/religion/interactives/religious-composition-by-country-2010-2050/) — country-level religious demographics (2020)

## AI Transcripts
- ChatGPT: https://chatgpt.com/share/6a238c6d-76c4-83ea-8239-d45458a07e44
- Claude: https://claude.ai/share/96ecd601-3d4b-4a87-9ad4-71f54159defe
