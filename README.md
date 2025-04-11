# Feature-Engineering & Delhivery Data Analysis

## 📦 Project Overview

This project performs a comprehensive analysis of the Delhivery logistics dataset to uncover insights related to trip data, including routes, time, and distance. The project includes data cleaning, feature engineering, visualization, and statistical testing to identify patterns and inconsistencies.

---

## 🛠️ Libraries Used

- `pandas`
- `numpy`
- `matplotlib.pyplot`
- `seaborn`
- `scipy.stats`
- `sklearn.preprocessing`
- `statsmodels.graphics.gofplots`
- `re`
- `os`
- `warnings`

---

## 🔍 Data Cleaning & Exploration

- Dropped irrelevant columns: `is_cutoff`, `cutoff_factor`, `cutoff_timestamp`, `factor`, `segment_factor`
- Converted data types:
  - Categorical: `data`, `route_type`
  - Datetime: `od_start_time`, `od_end_time`, `trip_creation_time`
- Removed rows with missing `source_name` (293) and `destination_name` (261)

---

## 🧠 Feature Engineering

- Aggregation on `trip_uuid`, `source_center`, and `destination_center`
- Derived `od_total_time` from `od_start_time` and `od_end_time`
- Extracted hierarchical geographic info:
  - `source_state`, `source_city`, `source_place`, `source_code`
  - `destination_state`, `destination_city`, `destination_place`, `destination_code`
- Time-based features:
  - `year`, `month`, `week`, `day`, `created_hour`

---

## 🧪 Hypothesis Testing

Conducted t-tests and statistical comparisons:
- `od_total_time` vs. `start_scan_to_end_scan`: Not significantly different
- `actual_time` vs. `osrm_time`: Significantly different
- `actual_time` vs. `segment_actual_time`: Not similar
- `osrm_distance` vs. `segment_osrm_distance`: Not similar
- `osrm_time` vs. `segment_osrm_time`: Not similar

---

## 📊 Visualizations & Analysis

- Distributions of key trip metrics
- Correlation heatmaps
- Trends in trip creation over time
- Top destination codes and patterns

---

## 📌 Key Findings

- OSRM (Open Source Routing Machine) predictions differ significantly from actual trip data
- Certain states (e.g., Maharashtra, Karnataka) have high trip volumes
- Distance and time metrics show systematic discrepancies

---

## ✅ Recommendations

- Refine OSRM route prediction logic
- Reduce predicted vs. actual delivery time gaps
- Enhance infrastructure in high-volume regions
- Investigate source of distance mismatches
- Profile high-volume customers for optimization

---
