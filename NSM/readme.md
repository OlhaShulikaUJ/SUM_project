## 🚀 How to Use It

**SimFLEX** (Simulation Framework for Feeder Location Evaluation) is an open-source simulation-optimization tool developed in Python to support data-driven decisions on deploying on-demand feeder bus services. This subsection outlines how to use SimFLEX for urban transport scenario evaluation.

---

### 🛠️ Getting Started

1. Prepare the data (see datasets in  **Defining a Use Case**)
2. Start the `OpenTripPlanner` server before running the framework
3. Define initial experiment configurations (`data/configs/default_SUM.json`)

---

### 🧭 Defining a Use Case

Each use case must include the following datasets (in the `data/` directory):

- **Road network graph:** graphml file (e.g.,`Krakow.graphml`)
- **Zoning data:** city zones in `.geojson` format (e.g., `krk_zones.geojson`), centroids of the zones (e.g., `krk_centroid.geojson`)
- **Urban area boundaries** for analysis (e.g., `sum_areas_B+S.shp`)
- **Demographics**: CSV with address and population (e.g., `krk_demographic.csv`)
- **Origin–Destination Matrix**: OD demand (e.g., `krk_ODM.xlsx`), defining travel demands between zones
- **Feeder hub coordinates**: a dictionary with `(lat, lon)` tuples for each area
- **Public transport schedules**:in General Transit Feed Specification (GTFS) format (e.g., `gtfs.zip`)

---

### ▶️ Running Simulations

Once the files are ready and OTP is running, use the following steps in `simulations.ipynb`:

1. Load the street network and the configuration file:
2. Load and preprocess input data:
   - city zones, centroids, areas
   - demographics
   - OD matrices

3. Run the main simulation:
   ```python
   results = fncs.simulate_MSA(gdf_areas, df_demo, gdf_centroid,
                                od, od_probs, hubs, inData, params,
                                "http://localhost:8080/otp/routers/default/plan",
                                degree, N, max_iter, ASC, results_period)

---

### 📊 Interpreting Results

Each simulation outputs key travel and behavioral indicators:

| Field | Description |
|-------|-------------|
| `tw_PT_OD`, `tw_PT_HD` | Waiting times for PT from O to D, from H to D |
| `u_PT_OD`, `u_SUM_OD` | Utilities of PT-only and feeder alternatives |
| `p_SUM` | Probability of choosing the feeder option |
| `ΔA` | Feeder attractiveness |
| `ΔV` | Added value |
| `avg_ts_pt`, `avg_ts_sh` | Average travel times by mode across iterations |
| `converged_is` | Convergence iteration index per run |
| `kpis_res` | ExMAS-based KPIs such as occupancy and vehicle hours |



You can compute per-area:
- **Averages and variances** of indicators
- **KPIs**: passenger hours, vehicle hours, occupancy (via `ExMAS`), feeder attractiveness, reduction in waiting time for public transport, added value
- **ASC sensitivity** over multiple replications
- **Travel time stabilization** using the method of successive averages (MSA)

---

### 📂 Output Files

- `results/main_results/*.csv`: average results, KPIs, ASC batch runs
- `results/images/*.png`: visualizations

---

### 📈 Visualizations


- KPI histograms by area
- Probability distribution of feeder choice
- ASC sensitivity scatter plots
- MSA convergence plots

Based on obtained results compare feeder service performance for each preselected area to interpret which areas benefit most from feeder deployment.

---

