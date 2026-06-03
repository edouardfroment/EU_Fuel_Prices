# EU Fuel Prices Analysis Dashboard

*A Power BI dashboard analyzing fuel prices (SP95 and Diesel) across European Union countries, with tax breakdowns, historical trends since 2005, and geopolitical impact visualization. Built with Microsoft Fabric for automated weekly data updates from the European Commission.*

---

## 📌 Project Overview

This project provides a **comprehensive analysis** of fuel prices across the European Union, focusing on:
- **Price comparisons** between EU countries for SP95 and Diesel
- **Tax breakdowns** (VAT, excise duties, other taxes)
- **Historical trends** since 2005
- **Geopolitical impact** visualization (Ukraine war, Hormuz Strait blockade)
- **Weekly automated data updates**

The solution leverages **Microsoft Fabric** for data ingestion, transformation, and storage, with **Power BI** for visualization and dashboard creation.

---

## 📊 Power BI Dashboard Pages

### **Page 1: EU Petrol Prices - SP95**
- **Filled Map** showing SP95 price differences across EU countries
- **Top 5 most expensive** and **top 5 cheapest** countries (price in €/liter)
- **Historical trend** of average SP95 price in EU since 2005 (with historical context tooltips)
- **Current average SP95 price** in EU (price in €/liter)
- **1-year evolution** of SP95 prices (price in €/liter)

![SP95 Prices Screenshot](https://via.placeholder.com/600x300?text=SP95+Prices+Dashboard+View)
*Example screenshot of SP95 prices page*

---

### **Page 2: EU Diesel Prices**
- **Filled Map** showing Diesel price differences across EU countries (price in €/liter)
- **Top 5 most expensive** and **top 5 cheapest** countries (price in €/liter)
- **Historical trend** of average Diesel price in EU since 2005 (with historical context tooltips)
- **Current average Diesel price** in EU (price in €/liter)
- **1-year evolution** of Diesel prices (price in €/liter)

![Diesel Prices Screenshot](https://via.placeholder.com/600x300?text=Diesel+Prices+Dashboard+View)
*Example screenshot of Diesel prices page*

---
### **Page 3: EU Fuel Taxes**
- **Filled Map** showing VAT differences across EU countries
- **Top 5 highest VAT** and **top 5 lowest VAT** countries
- **Table** displaying excise duties and other taxes for SP95 and Diesel (price in €/liter)

![Fuel Taxes Screenshot](https://via.placeholder.com/600x300?text=Fuel+Taxes+Dashboard+View)
*Example screenshot of fuel taxes page*

---
### **Page 4: Country View**
- **Dropdown menu** to select any EU country
- **Card** showing the selected country's VAT rate
- **Azure Map** of the selected country
- **Data cards** showing SP95 and Diesel prices for the selected country

![Country View Screenshot](https://via.placeholder.com/600x300?text=Country+View+Dashboard+View)
*Example screenshot of country view page*

---
### **Page 5: Overall Ranking**
- **Complete ranking** of EU countries by SP95 price (€/liter)
- **Complete ranking** of EU countries by Diesel price (€/liter)
- **Complete ranking** of EU countries by fuel VAT rate

![Overall Ranking Screenshot](https://via.placeholder.com/600x300?text=Overall+Ranking+Dashboard+View)
*Example screenshot of overall ranking page*

---

## ⚙️ Technical Implementation

The project was developed entirely in **Microsoft Fabric** and **Power BI** (no VS Code used). Here's the technical architecture:

### **Data Pipeline**
1. **Python Notebooks** in Microsoft Fabric:
   - `notebooks/extract_sp95_data.py` - Extracts and cleans SP95 price data
   - `notebooks/extract_diesel_data.py` - Extracts and cleans Diesel price data

2. **Data Processing**:
   - Both scripts clean and transform the data
   - Data is loaded into **LakeHouse tables** in Microsoft Fabric

3. **Automation**:
   - **Weekly pipeline** that automatically runs both Python scripts
   - **Email notifications** sent upon successful completion

4. **Visualization**:
   - Power BI dashboard connected directly to Lakehouse tables
   - Published to **Power BI Service** (visible in Microsoft Fabric workspace)

![Fabric Pipeline Screenshot](https://via.placeholder.com/600x300?text=Fabric+Pipeline+Screenshot)
*Example screenshot of the automated pipeline in Microsoft Fabric*

### **Data Source**
- Weekly updates from the [European Commission's Weekly Oil Bulletin](https://energy.ec.europa.eu/data-and-analysis/weekly-oil-bulletin_en)

---

## 🔍 Key Insights (as of June 1, 2026)

### 💰 Fuel Price Composition in the EU

Understanding the price composition is essential to interpret the data correctly. In the European Union, fuel prices are composed of four main elements:

1. **Product Cost** (crude oil price, refining, transport)
2. **Distribution Margins** (storage, logistics, service station operations)
3. **Excise Duties and Other Taxes** (specific taxes per liter, sometimes including environmental taxes)
4. **VAT** (applied to the tax-exclusive price, often including excise duties)

### **Main Insights**

#### **1. Geopolitical Impact**
The dashboard clearly visualizes the impact of:
- **Ukraine war** (since 2022) on fuel prices across the EU
- **Hormuz Strait blockade** (since March 2026) on recent price increases

#### **2. Price Disparities Between EU Countries**

**SP95 Prices (€/liter):**
| Rank | Country | Price |
|------|---------|-------|
| **Most Expensive** | Denmark | €2.50 |
| | Netherlands | €2.39 |
| | Finland | €2.19 |
| | Greece | €2.14 |
| | France | €2.11 |
| **Cheapest** | Malta | €1.34 |
| | Poland | €1.51 |
| | Bulgaria | €1.53 |
| | Spain | €1.57 |
| | Cyprus | €1.59 |

**Diesel Prices (€/liter):**
| Rank | Country | Price |
|------|---------|-------|
| **Most Expensive** | Finland | €2.32 |
| | Netherlands | €2.26 |
| | Denmark | €2.22 |
| | Belgium | €2.13 |
| | France | €2.12 |
| **Cheapest** | Malta | €1.21 |
| | Poland | €1.59 |
| | Czech Republic | €1.68 |
| | Spain | €1.69 |
| | Bulgaria | €1.71 |

**Key Observations:**
- **Malta** has the cheapest fuel prices in the EU
- **Average EU SP95 price**: €1.90/liter (up €0.30 from 1 year ago)
- **Average EU Diesel price**: €1.90/liter (up €0.41 from 1 year ago)
- **Denmark** saw the largest SP95 price increase over the past year (+€0.56/liter)
- **Finland** saw the largest Diesel price increase over the past year (+€0.77/liter)

#### **3. VAT and Tax Disparities**

**VAT Rates:**
| Rank | Country | VAT Rate |
|------|---------|----------|
| **Highest VAT** | Hungary | 27% |
| | Finland | 25.5% |
| | Croatia, Denmark, Sweden | 25% |
| **Lowest VAT** | Poland | 8% |
| | Spain | 10% |
| | Luxembourg | 17% |
| | Malta | 18% |
| | Cyprus, Germany | 19% |

**Interesting Case - Hungary:**
Despite having the **highest VAT (27%)**, Hungary shows relatively **reasonable fuel prices** (SP95: €1.68/liter, Diesel: €1.75/liter) compared to other EU countries. **The reasons for this particular case need to be investigated.**

---

## 📁 Project Structure

```bash
EU_Fuel_Prices/
├── notebooks/             # Python notebooks for data extraction
│   ├── EU_Fuel_Price_ETL
│   └── Taxes
├── screenshots/
│   └── powerbi/           # Power BI dashboard screenshots
│   └── fabric/            # Microsoft Fabric screenshots
└── README.md

```

---

## 🏆 Overall Ranking - June 1st, 2026

### ⛽ EU Petrol SP95 Prices (€/L)

| Rank | Country | Price |
|------|-------------|-------|
| 1 | Denmark | 2.50 € |
| 2 | Netherlands | 2.39 € |
| 3 | Finland | 2.19 € |
| 4 | Greece | 2.14 € |
| 5 | France | 2.11 € |
| 6 | Germany | 2.03 € |
| 7 | Portugal | 2.02 € |
| 8 | Italy | 1.96 € |
| 9 | Belgium | 1.94 € |
| 10 | Latvia | 1.88 € |
| 11 | Ireland | 1.83 € |
| 12 | Lithuania | 1.82 € |
| 13 | Luxembourg | 1.81 € |
| 14 | Estonia | 1.81 € |
| 15 | Austria | 1.81 € |
| 16 | Slovakia | 1.80 € |
| 17 | Romania | 1.78 € |
| 18 | Czech Republic | 1.78 € |
| 19 | Sweden | 1.74 € |
| 20 | Croatia | 1.70 € |
| 21 | Slovenia | 1.70 € |
| 22 | Hungary | 1.68 € |
| 23 | Cyprus | 1.59 € |
| 24 | Spain | 1.57 € |
| 25 | Bulgaria | 1.53 € |
| 26 | Poland | 1.51 € |
| 27 | Malta | 1.34 € |

---

### 🚗 EU Diesel Prices (€/L)

| Rank | Country | Price |
|------|-------------|-------|
| 1 | Finland | 2.32 € |
| 2 | Netherlands | 2.26 € |
| 3 | Denmark | 2.22 € |
| 4 | Belgium | 2.13 € |
| 5 | France | 2.12 € |
| 6 | Italy | 1.99 € |
| 7 | Portugal | 1.96 € |
| 8 | Sweden | 1.94 € |
| 9 | Germany | 1.94 € |
| 10 | Ireland | 1.93 € |
| 11 | Lithuania | 1.93 € |
| 12 | Austria | 1.91 € |
| 13 | Latvia | 1.89 € |
| 14 | Luxembourg | 1.84 € |
| 15 | Romania | 1.82 € |
| 16 | Greece | 1.82 € |
| 17 | Cyprus | 1.80 € |
| 18 | Estonia | 1.80 € |
| 19 | Croatia | 1.79 € |
| 20 | Hungary | 1.75 € |
| 21 | Slovenia | 1.75 € |
| 22 | Slovakia | 1.72 € |
| 23 | Bulgaria | 1.71 € |
| 24 | Spain | 1.69 € |
| 25 | Czech Republic | 1.68 € |
| 26 | Poland | 1.59 € |
| 27 | Malta | 1.21 € |

---

### 🧾 EU VAT Rates

| Rank | Country | VAT Rate |
|------|-------------|----------|
| 1 | Hungary | 27.0% |
| 2 | Finland | 25.5% |
| 3 | Croatia | 25.0% |
| 4 | Denmark | 25.0% |
| 5 | Sweden | 25.0% |
| 6 | Greece | 24.0% |
| 7 | Ireland | 23.0% |
| 8 | Portugal | 23.0% |
| 9 | Slovakia | 23.0% |
| 10 | Estonia | 22.0% |
| 11 | Italy | 22.0% |
| 12 | Slovenia | 22.0% |
| 13 | Belgium | 21.0% |
| 14 | Czech Republic | 21.0% |
| 15 | Latvia | 21.0% |
| 16 | Lithuania | 21.0% |
| 17 | Netherlands | 21.0% |
| 18 | Romania | 21.0% |
| 19 | Austria | 20.0% |
| 20 | Bulgaria | 20.0% |
| 21 | France | 20.0% |
| 22 | Cyprus | 19.0% |
| 23 | Germany | 19.0% |
| 24 | Malta | 18.0% |
| 25 | Luxembourg | 17.0% |
| 26 | Spain | 10.0% |
| 27 | Poland | 8.0% |
