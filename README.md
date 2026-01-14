# lab2
# Deflating History with FRED

## The Illusion of Growth & The Composition Effect

### Objective
I built a Python pipeline to ingest live economic data from the Federal Reserve API to analyze wage stagnation and correct for statistical biases.

### Tech Stack
- Python
- fredapi
- pandas
- matplotlib

### Methodology

1. I fetched nominal wage data (AHETPI) and CPI data to calculate 'Real Wages.'
2. I detected a statistical anomaly in 2020 (The Pandemic Spike).
3. I fetched the Employment Cost Index (ECI) to control for the 'Composition Effect' and prove the spike was artificial.

### Key Findings

I visualized the 'Money Illusion'—showing flat real wages over 50 years. I also demonstrated that the 2020 wage boom was a statistical artifact caused by low-wage workers exiting the labor force, not a true increase in labor demand (the "Pandemic Paradox").

### Visualizations

[Include your charts here - you can upload the chart images to your repo and reference them]

![Nominal vs Real Wages Chart](path/to/your/chart1.png)
![Composition Effect Chart](path/to/your/chart2.png)
