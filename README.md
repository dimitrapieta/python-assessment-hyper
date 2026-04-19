# 25 Years of Pop: Billboard Hot 100 Analysis (2000–2024)

An exploratory data analysis of 25 years of Billboard Hot 100 chart data combined with Spotify audio features, written from the perspective of a data journalist for the fictional *Rolling Beats Magazine*.

**Assessment project for Hyper Island's Data Analyst program — Python module.**

## About the Project

Rolling Beats Magazine is preparing their "25 Years of Pop" retrospective issue. As the data journalist on the team, I explored how popular music has evolved since 2000 by analysing chart performance data alongside Spotify's audio analysis for each track.

The analysis investigates four main questions:

1. **What makes a viral hit?** — Comparing the audio profile of the 10 most dominant #1 songs against the broader chart population using z-scores.
2. **How has the "sound" of the charts changed?** — Tracking trends in danceability, energy, valence, acousticness, and other audio features year by year.
3. **Are songs getting shorter?** — Examining the steady decline in average track duration on the charts and its possible link to streaming and short-form video.
4. **Has explicit content taken over?** — Measuring the rise of explicit tracks from ~15 % of the charts in 2000 to nearly 50 % by the streaming era, and whether explicit songs actually perform better.

## Data

The dataset was provided by Hyper Island via Google BigQuery and consists of five tables:

| Table | Description |
|---|---|
| `tracks` | Track metadata — name, duration, release date, album type, explicit flag |
| `artists` | Artist names and IDs |
| `audio_features` | Spotify audio analysis — danceability, energy, tempo, valence, etc. |
| `chart_positions` | Weekly Billboard Hot 100 positions (2000–2024) |
| `tracks_artists_mapping` | Many-to-many mapping between tracks and artists |

## Key Findings

- **Viral hits have a signature sound** — faster tempo, higher valence (happier), major key, and elevated danceability compared to the average chart entry.
- **The charts have gotten calmer** — energy, loudness, and valence have all declined since the early 2010s, while acousticness has risen.
- **Songs are ~50 seconds shorter** — average duration dropped from 4 min 15 s (2000) to 3 min 27 s (2024), accelerating after the rise of streaming and TikTok.
- **Explicit content surged but doesn't guarantee better chart performance** — after an initial disadvantage, explicit and non-explicit tracks perform roughly the same from 2010 onward.

## Tools & Libraries

- **Python 3** with Jupyter Notebook
- **pandas** & **NumPy** — data wrangling and analysis
- **Matplotlib** & **Seaborn** — visualisation
- **Google BigQuery** — data source

## Project Structure

```
├── Dimitra_Pieta_-_Assessment.ipynb   # Full notebook (cleaning, analysis, presentation)
└── README.md
```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/billboard-hot100-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy seaborn matplotlib google-cloud-bigquery google-auth db-dtypes
   ```
3. The notebook pulls data from a BigQuery dataset that requires Hyper Island credentials (`bigquery-access-key.json`). Without access, you can still read through the full analysis and outputs in the rendered notebook on GitHub.
