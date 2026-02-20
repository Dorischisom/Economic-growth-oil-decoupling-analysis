# Are Countries Decoupling Economic Growth from Oil Consumption? (2000–2024)

## 📌 Business Problem

Economic growth has historically been closely tied to fossil fuel consumption. However, as countries pursue energy efficiency, structural transformation, and climate goals, an important question emerges:

**Are countries growing their economies while reducing their dependence on oil?**

This project investigates whether countries are achieving economic decoupling the ability to grow GDP without proportionally increasing oil consumption.

## 🎯 Objective

**To evaluate whether countries between 2000 and 2024 are:**

- Growing economically
- Reducing oil consumption
- Improving oil intensity (oil per unit of GDP)

**The analysis classifies countries into:**
- Absolute Decoupling
- Relative Decoupling
- No Decoupling
- Other / GDP contraction

## 📂 Data Sources
1. Oil Consumption (TWh)
- Source: Our World in Data (OWID)

2. GDP (current US$)
- Source: World Bank API
`Indicator: NY.GDP.MKTP.CD`

**Time period analyzed:**
**2000–2024**

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- World Bank API
- Our World in Data


## 🧹 Data Cleaning & Preparation (Python)

##### The following steps were performed:
- Removed regional aggregates (World, EU, income groups)
- Kept only valid ISO country codes
- Filtered data between 2000–2024
- Merged oil consumption and GDP datasets
- Calculated key indicators:
  - GDP growth (%)
  - Oil consumption growth (%)
  - Oil intensity (TWh per billion USD GDP)
  - Oil intensity change (%)

## 📊 Key Metrics Calculated
##### Oil Intensity

```Oil Intensity = Oil Consumption (TWh) / GDP (billion USD)```

This measures how much oil is used per unit of economic output. 

##### Growth Calculations

```wide["gdp_change_%"] = (gdp_2024 / gdp_2000 - 1) * 100```
```wide["oil_change_%"] = (oil_2024 / oil_2000 - 1) * 100```
```wide["intensity_change_%"] = (intensity_2024 / intensity_2000 - 1) * 100```

## Decoupling Classification Logic

#### Countries were classified as follows:

🟢 Absolute Decoupling
- GDP increased
- Oil consumption decreased

🟡 Relative Decoupling
- GDP increased
- Oil consumption increased
- Oil intensity decreased (GDP grew faster than oil use)

🔴 No Decoupling
- GDP increased
- Oil consumption increased faster than GDP

⚫ Other / GDP Fell
- GDP declined over the period

## 📈 Analysis & Visualizations

##### 1️⃣ Scatter Plot: GDP Growth vs Oil Consumption Change

![GDP Growth vs Oil Consumption Change](Scatter_Plot/Scatter_Plot.png)

**This visualization plots:**
X-axis → GDP growth (%)
Y-axis → Oil consumption change (%)


**Key Observations**

Most countries fall in the top-right quadrant:
- GDP increased
- Oil consumption also increased


Several countries appear in the bottom-right quadrant:
- GDP increased
Oil consumption declined
→ Evidence of absolute decoupling


High-growth economies often show oil demand increases, but many exhibit relative decoupling


##### 2️⃣ Decoupling Classification Distribution

![Decoupling Classification Distribution](Decoupling1/Decoupling1.png)

***The classification breakdown shows:**

- Majority of countries achieved relative decoupling
- A significant group achieved absolute decoupling
- Very few countries showed GDP contraction over the full period

This suggests gradual structural improvement in oil efficiency globally.

##### 3️⃣ Oil Intensity Trends

![Oil Intensity Trends](Oil_Intensity/Oil_Intensity.png)

**Time-series analysis indicates:**

- Broad decline in oil intensity across many economies
  
- Improvements likely driven by:
  - Technological efficiency
  - Structural economic shifts (services > heavy industry)
  - Energy diversification
 
## Overall Findings

1. Most countries are not fully separating growth from oil use, but many are improving efficiency.
2. Absolute decoupling remains concentrated in advanced economies.
3. Relative decoupling is widespread — GDP is growing faster than oil consumption.
4. Oil intensity has declined in many economies over the past two decades.
5. Emerging economies still show stronger oil-demand growth relative to GDP.


## Limitations

1. GDP measured in current USD may be influenced by inflation and exchange rates.

2. The analysis does not control for:
- Population growth
- Structural industrial changes
- Energy mix transitions (renewables)

3. Oil consumption measured in TWh does not capture total energy dependency.

4. The period includes structural shocks (2008 crisis, COVID-19) that may distort long-run trends.

5. Data availability varies across countries.

## Conclusion

Between 2000 and 2024, global evidence suggests a gradual shift toward oil-use efficiency.

While complete decoupling remains limited, many economies are achieving relative decoupling, meaning economic growth is outpacing oil demand growth.

Absolute decoupling is more visible in advanced economies, while developing nations continue to experience oil demand expansion alongside growth.

The findings indicate progress toward efficiency but highlight ongoing structural reliance on oil in many regions.

Understanding decoupling patterns is essential for:

- Climate transition policy
- Energy market forecasting
- Long-term demand projections
- Sustainable growth strategy
