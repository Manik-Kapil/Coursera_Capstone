# Predictive Measures for Mitigation of COVID-19 Community Transmission

> **Status:** Archived (Project completed April 2020)  
> **Author:** Manik Kapil

## 📌 Project Overview
This data science project, developed during the critical early phase of the COVID-19 pandemic (April 2020), aims to mitigate community transmission through predictive modelling and geospatial analysis. The system analyzes infection hotspots across India to scientifically recommend optimal locations for **quarantine facilities**, **isolation wards**, and **community kitchens**.

By leveraging K-Means clustering on district-level data and integrating Foursquare API location intelligence, the project provides a strategic framework for resource allocation in worst-hit regions.

## 🔍 Exploratory Data Analysis (EDA) & Inferences
Extensive analysis was conducted on daily patient databases, time-series case data, and testing metrics to derive the following critical inferences:

### 1. Severity & Regional Hotspots
* [cite_start]**High-Load States:** Maharashtra emerged as the epicenter with **8,068 confirmed cases**, followed significantly by Gujarat and Delhi [cite: 74, 78-82].
* [cite_start]**Active Case Load:** Analysis of active cases revealed that while Maharashtra had the highest volume (6,538), states like Delhi (1,702 active cases) showed promising recovery trends, potentially attributed to specific interventions like Plasma Therapy [cite: 172-177, 186-192].
* [cite_start]**Mortality Analysis:** Maharashtra recorded the highest fatalities (342), followed by Gujarat (151) and Madhya Pradesh (103), highlighting the urgent need for critical care infrastructure in these specific zones [cite: 234-250].

### 2. The "Lockdown Effect" Analysis
A core objective was to determine if India's pre-emptive lockdowns successfully delayed "Stage III" (Community Transmission).
* [cite_start]**Linear vs. Exponential Growth:** Post-lockdown analysis indicated that while daily confirmed cases rose (partially attributed to specific congregation events like Nizamuddin), the growth trajectory remained **linear rather than exponential** [cite: 373-375, 408-410].
* [cite_start]**Stage II Containment:** The data suggested that India successfully restrained the spread within "Stage II" during the analysis period, with daily new cases capped around ~1,800[cite: 304, 377].

### 3. Testing Efficacy & Positivity Rates
* [cite_start]**Testing Surge:** There was a drastic improvement in daily testing numbers immediately following the imposition of the first lockdown[cite: 408].
* **Positivity Correlation:** Despite increased testing, the **test positivity rate** increased linearly. [cite_start]This metric was crucial in validating that the rise in cases was captured by improved surveillance rather than purely unchecked community spread [cite: 409-410].

## ⚙️ Methodology & Predictive Modelling

### 1. Data Pre-processing & Feature Engineering
* [cite_start]**Data Cleaning:** Handled missing values in 'Daily Confirmed' and 'Daily Recovered' datasets; standardized inconsistent timestamp formats across multiple sources [cite: 32, 40-41, 44].
* [cite_start]**Geospatial Integration:** Appended precise Latitude/Longitude coordinates to state and district-level data to enable spatial analysis [cite: 36-37, 503].
* [cite_start]**Normalization:** Applied `StandardScaler` to 'Confirmed Cases' to remove bias before clustering[cite: 504, 507].

### 2. K-Means Clustering for Hotspot Detection
* [cite_start]**Algorithm:** Implemented **K-Means Clustering** with `k=100` to categorize districts into clusters based on infection severity and geographic proximity[cite: 67, 506].
* [cite_start]**Centroid Calculation:** Calculated the geometric centroids of these clusters to identify optimal central locations for relief facilities [cite: 68, 592-593].
* [cite_start]**Visual Output:** Generated interactive maps using Folium to visualize clusters (e.g., **Cluster 26: South Delhi**) and their respective severity radii [cite: 509-511].

### 3. Venue Recommendation Engine
* [cite_start]**API Integration:** Interfaced with the **Foursquare API** to query the calculated cluster centroids[cite: 597].
* [cite_start]**Resource Allocation:** Successfully identified and recommended specific venues (Hotels, Schools, Hostels) within the vicinity of hotspots to be repurposed as **Quarantine Centres** or **Community Kitchens** [cite: 59, 594-596].

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (K-Means, StandardScaler)
* **Visualization:** Matplotlib, Seaborn, Folium (Geospatial Mapping)
* **External APIs:** Foursquare Developer API

## 🚀 Impact & Conclusion
The model demonstrated that data-driven clustering can effectively guide government resource allocation. By identifying the mean location of infection clusters, authorities can strategically position isolation centers to minimize travel for patients and maximize coverage. [cite_start]The analysis further validated the effectiveness of early lockdowns in preventing exponential viral spread during the study period [cite: 409-410, 600].

## 💻 How to Run
1.  Clone the repository:
    ```bash
    git clone [https://github.com/yourusername/covid19-predictive-measures.git](https://github.com/yourusername/covid19-predictive-measures.git)
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy scikit-learn folium matplotlib seaborn
    ```
3.  Add your API Keys:
    * Create a `.env` file for your Foursquare API credentials.
4.  Run the notebook:
    ```bash
    jupyter notebook mitigation_analysis.ipynb
    ```

---
*Disclaimer: This project uses historical data from April 2020. Predictions and recommendations are relevant to the epidemiological situation of that specific period.*
