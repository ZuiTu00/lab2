# lab2
# The Illusion of Growth & The Composition Effect
## Deflating History with FRED API

### 📊 Project Overview
This project demonstrates advanced econometric analysis using Federal Reserve Economic Data (FRED) API to expose statistical biases in wage measurement and reveal the "money illusion" that masks 50 years of wage stagnation.

### 🎯 Objective
Build a Python pipeline to ingest live economic data from the Federal Reserve API to analyze wage stagnation and correct for statistical biases, particularly the 2020 "Pandemic Composition Effect."

### 🛠️ Tech Stack
- **Python 3.x**
- **fredapi** - Federal Reserve Economic Data API
- **pandas** - Data manipulation and time series analysis
- **matplotlib** - Data visualization
- **numpy** - Numerical computations

### 📈 Methodology

#### 1. Data Acquisition & Real Wage Calculation
```python
# Fetched nominal wage data (AHETPI) and CPI data
wages = fred.get_series('AHETPI', start='1964-01-01')
cpi = fred.get_series('CPIAUCSL', start='1964-01-01')

# Calculate real wages (inflation-adjusted)
real_wages = (wages / cpi) * base_cpi
```

#### 2. Detecting the 2020 Statistical Anomaly
Identified an artificial spike in average wages during the pandemic—not from actual wage growth, but from compositional changes in the workforce:
- Low-wage service workers were disproportionately laid off
- High-wage remote workers retained employment
- The remaining sample showed higher average wages (statistical artifact)

#### 3. Bias Correction Using ECI
```python
# Employment Cost Index (ECI) controls for composition changes
eciwag = fred.get_series('ECIWAG', start='2015-01-01')

# ECI maintains fixed job composition, revealing true wage trends
```

### 🔍 Key Findings

#### The "Pandemic Paradox"
![Wage Comparison](charts/composition_effect.png)

1. **The Money Illusion (1964-2024)**
   - Nominal wages appear to rise steadily (red dashed line)
   - Real wages remain essentially flat for 50+ years (blue solid line)
   - Workers experience no genuine improvement in purchasing power

2. **2020 Composition Effect**
   - Standard average wages showed an "artificial spike" during COVID-19
   - ECI data (fixed composition) revealed stable, modest growth
   - The spike was a statistical mirage, not a true wage increase

3. **Policy Implications**
   - Labor market statistics can be misleading without proper controls
   - Composition effects must be considered in economic policy decisions
   - Real wage stagnation remains a critical economic challenge

### 📊 Visualizations

#### Chart 1: The Illusion of Growth (1964-Present)
Shows the divergence between nominal and real wages over 60 years, highlighting how inflation erodes purchasing power despite apparent wage growth.
<img width="1352" height="673" alt="image" src="https://github.com/user-attachments/assets/870548c0-b295-456e-9a82-256613dcbc3c" />


#### Chart 2: Composition Effect Analysis (2015-Present)
Compares biased average wages (AHETPI) with composition-controlled wages (ECI), exposing the 2020 statistical artifact.
<img width="1384" height="684" alt="image" src="https://github.com/user-attachments/assets/132f35c6-9846-4f1e-8c73-b8c2be27242d" />

### 🚀 How to Run

1. **Install Dependencies**
```bash
pip install fredapi pandas matplotlib numpy
```

2. **Set Up FRED API Key**
```python
from fredapi import Fred
fred = Fred(api_key='YOUR_API_KEY')
```

3. **Run the Analysis**
```bash
python wage_analysis.py
```

### 📝 Economic Insights

**The Balassa-Samuelson Effect**: Real wages should grow with productivity, but U.S. data shows decoupling since the 1970s.

**Phillips Curve Implications**: The 2020 anomaly disrupted traditional unemployment-wage relationships, requiring new analytical frameworks.

**Measurement Challenges**: This project underscores the importance of:
- Using appropriate deflators (CPI vs PCE)
- Controlling for workforce composition
- Distinguishing statistical artifacts from economic reality

### 🔗 Data Sources
- [FRED Economic Data](https://fred.stlouisfed.org/)
- AHETPI: Average Hourly Earnings of All Employees
- CPIAUCSL: Consumer Price Index for All Urban Consumers
- ECIWAG: Employment Cost Index - Wages and Salaries

### 📚 References
- Acemoglu, D., & Restrepo, P. (2022). "Tasks, Automation, and the Rise in U.S. Wage Inequality"
- Autor, D. (2019). "Work of the Past, Work of the Future"
- Card, D., & DiNardo, J. (2002). "Skill-Biased Technological Change and Rising Wage Inequality"

### 🏆 Skills Demonstrated
- **Economic Analysis**: Time series analysis, inflation adjustment, index construction
- **Statistical Methods**: Bias detection, composition effect correction, data rebasing
- **Data Engineering**: API integration, data pipeline construction, ETL processes
- **Visualization**: Multi-series plotting, annotation, professional chart design
- **Domain Knowledge**: Labor economics, monetary policy, statistical measurement

### 📧 Contact
[Zui Tu] | [tu.zu@northeastern.edu]  

---
*This project was completed as part of Advanced Econometrics coursework, demonstrating the critical importance of understanding statistical biases in economic data.*
