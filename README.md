# 🗺️ Food Access Mapping in Mecklenburg County using ArcGIS & Census Data

This project identifies and maps **food accessibility disparities** among low-income households in Mecklenburg County, NC. Using **ArcGIS Pro** and **ArcPy**, we analyze where residents lack access to grocery stores within a **10-minute walking distance**—highlighting areas classified as **food deserts**.

---

## 📌 Objective

To visualize neighborhoods in Mecklenburg County where **low-income households do not have walkable access to grocery stores**, supporting data-driven public policy and urban planning.

---

## 🛠️ Tools & Technologies

- ArcGIS Pro
- ArcPy (Python for ArcGIS)
- U.S. Census Bureau ACS Income Data
- TIGER/Line Shapefiles
- Local Mecklenburg County Land Use Data

---

## 📊 Data Sources

| Dataset | Description |
|--------|-------------|
| `grocery_stores.shp` | Shapefile of grocery store locations |
| `census_income.csv` | ACS income data at block group level |
| `block_groups.shp` | TIGER/Line geometries with GEOID |
| `land_use_filtered.shp` | Residential land use types (filtered) |

---

## 🧪 Methodology

### 1️⃣ Grocery Access Buffer
Created **10-minute walking buffers** around grocery stores using ArcPy and network analysis.

### 2️⃣ Income Normalization
Joined census income data with TIGER/Line geometries. Classified income into:
- Low Income: < $50,000  
- Middle Income: $50,000–$120,000  
- High Income: > $120,000  

### 3️⃣ Filtered Residential Parcels
Filtered only:
- Single-Family Homes  
- Multi-Family Residences  
- Townhomes  

Excluded commercial, industrial, and vacant parcels.

### 4️⃣ Low-Income Residential Zones
Intersected low-income block groups with residential land use parcels to identify **target populations**.

### 5️⃣ Grocery Access Overlay
Performed **Pairwise Intersect** to find low-income homes within walking distance of grocery stores.

### 6️⃣ Final Layer & Map Export
Created a final map overlay to highlight parcels that **do** and **do not** have grocery access.

---

## 🖼️ Visual Outputs

| Visualization | Description |
|---------------|-------------|
| ![Buffer](images/grocery_buffer_map.png) | Grocery store buffer zones (10-min walk) |
| ![Income](images/income_normalization_map.png) | Income-based block group classification |
| ![Overlay](images/final_overlay_accessibility.png) | Final overlay showing accessible parcels |
| ![Deserts](images/mecklenburg_food_desert_zones.png) | Identified food deserts in Mecklenburg |

---

## 📈 Key Findings

- Many **low-income single-family homes** are outside the service area of grocery stores.
- **Urban multi-family housing** tends to have better access due to clustering.
- Several underserved **pockets** are ideal for mobile grocery services or zoning intervention.

---

## 🧠 Conclusion

This GIS-based project offers a **granular, data-driven approach** to identifying food deserts. It can help guide:

- Urban development
- Public health initiatives
- Zoning reforms
- Mobile grocery outreach planning

---
