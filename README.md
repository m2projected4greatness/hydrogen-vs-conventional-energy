# hydrogen-vs-conventional-energy
Status: in progress (Nov 2026)  
How efficient is hydrogen energy compared with conventional energy? This project traces useful energy out per unit of energy in, stage by stage, for three use cases:
Home heating: Hydrogen boiler, gas boiler, heat pump
Data centres: Grid power, on-site hydrogen fuel cells, on-site gas turbines (with a weather-driven PUE model)
Making ammonia:	Hydrogen from electrolysis vs from natural gas (SMR)
Two measures are used: **chain efficiency** (first stage to useful output) and **primary-energy efficiency** on the real grid, using a year of hourly EIA-930 data for four US regions and UK data from the NESO Carbon Intensity API.
Setup
```bash
pip install -r requirements.txt
cp .env.example .env        # then paste your EIA API key into .env
python src/fetch_eia930.py  # hourly US grid data, 4 regions
python src/fetch_weather.py # hourly temperature, Open-Meteo
python src/fetch_uk_grid.py # UK generation mix, NESO
```
Layout
`data/assumptions.csv`: every efficiency figure with value, range, unit and source. 
`verified=no` means the source has not been checked yet.
`data/raw/`: downloaded data (not committed)
`data/clean/`: cleaned hourly data
`src/`: download, cleaning and model code
`charts/`: output charts
Note
The code in this repo is AI-assisted. All figures and modelling choices were checked by the author.
