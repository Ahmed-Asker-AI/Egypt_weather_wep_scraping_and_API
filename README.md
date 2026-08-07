# Egypt Weather & Demographics - ETL Pipeline (API & Web Scraping) 🌍📊

An end-to-end Python data collection pipeline (ETL) designed to harvest real-time meteorological metrics and regional demographics for major Egyptian cities. This project integrates asynchronous web scraping and live API ingestion, consolidating diverse structures into a clean analytical dataset.

---

## 🛠️ Technology Stack & Environment
- **Environment**: Jupyter Notebook (VS Code)
- **Core Libraries**: 
  - `Requests`: For live REST API orchestration.
  - `Pandas`: For matrix transformations, missing value testing, and table merging (`pd.merge`).
  - `BeautifulSoup` / `lxml`: For scraping raw structural text elements from Wikipedia.

---

## 💡 Automated Pipeline Architecture (How it Works)

As documented in the project lifecycle, the data engine processes through 5 clean stages:

1. **Live API Ingestion**: Dispatched localized requests to the **Open-Meteo API** passing precise coordinates (`latitude`, `longitude`) for 6 major Egyptian hubs (**Cairo, Alexandria, Giza, Luxor, Aswan, Port Said**) to extract real-time `temperature_c` and `windspeed_kmh`.
2. **Wikipedia Web Scraping**: Scraped live demographic facts from Wikipedia to dynamically map cities to their respective `governorate` and official `population` figures.
3. **Data Merging & Refactoring**: Combined both data entities using specialized Pandas keys on the common `city` field to unify geography, weather, and populations.
4. **Data Exporting**: Serialized the unified DataFrame into a clean local storage backup file: `egypt_weather_collected.csv`.
5. **Statistical Verification**: Reloaded the data block (`reloaded_df`) to evaluate schemas using `.head()`, `.info()`, and `.describe()`, validating zero null values (`.isnull().sum()`) across all 6 target attributes.

---

## 📊 Sample Insights & Data Profile

The final generated pipeline outputs clean, analytical frames containing structured observations like:

- **Row Count**: 6 Primary Economic Cities.
- **Features Captured**: `city`, `temperature_c`, `windspeed_kmh`, `observed_at`, `governorate`, `population`.
- **Metrics Profile**: Clean data ranges verifying accurate float/integer conversions, perfectly isolated for logistics or consumer heatmaps.

---
**📬 Developed by Data Analyst: Ahmed Asker** 🧑‍💻
