# lab2
# Fetched nominal wage data (AHETPI) and CPI data
wages = fred.get_series('AHETPI', start='1964-01-01')
cpi = fred.get_series('CPIAUCSL', start='1964-01-01')

# Calculate inflation-adjusted real wages
real_wages = (wages / cpi) * base_cpi
# Employment Cost Index maintains fixed job composition
eciwag = fred.get_series('ECIWAG', start='2015-01-01')

# Rebased both series for direct comparison
wages_rebased = (wages / wages.iloc[0]) * 100
eci_rebased = (eciwag / eciwag.iloc[0]) * 100
# Install dependencies
pip install fredapi pandas matplotlib numpy

# Set FRED API key
export FRED_API_KEY='your_key_here'

# Run analysis
python wage_analysis.py
