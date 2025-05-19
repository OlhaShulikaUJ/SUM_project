## 🚀 How to Use It

**SimFLEX** (Simulation Framework for Feeder Location Evaluation) is an open-source simulation-optimization tool developed in Python to support data-driven decisions on deploying on-demand feeder bus services. This subsection outlines how to install, configure, and use SimFLEX for urban transport scenario evaluation.

---

### 🛠️ Getting Started

1. Ensure you have **Python 3.8+** installed.
2. Clone the repository:
   ```bash
   git clone https://github.com/anniutina/SimFLEX/simulations???.git
   cd simulations
   ```
3. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

   **Dependencies include:**
   - `pandas`, `numpy`, `matplotlib`, `geopandas`, `seaborn`, `shapely`
   - Modules: `ExMAS`, `SUM-main`, and a custom `src/functions.py`
   - A working instance of OpenTripPlanner (OTP) at `http://localhost:8080/otp/routers/default/plan`
  
Start the OpenTripPlanner server before running the framework.

---

### 🧭 Defining a Use Case

Each use case must include the following datasets (in the `data/` directory):

- **Zoning data:** city zones in `.geojson` format (e.g., `krk_zones.geojson`), centroids of the zones (e.g., `krk_centroid.geojson`)
- **Urban area boundaries** for analysis (e.g., `sum_areas_B+S.shp`)
- **Demographics**: CSV with address and population (e.g., `krk_demographic.csv`)
- **Origin–Destination Matrix**: OD demand (e.g., `krk_ODM.xlsx`), defining travel demands between zones
- **Feeder hub coordinates**: a dictionary with `(lat, lon)` tuples for each area

---

### ▶️ Running Simulations

Once the files are ready and OTP is running, use the following steps in a Python environment:

1. Load the street network and config:
   ```python
   from ExMAS.utils import inData
   import ExMAS.utils
   params = ExMAS.utils.get_config('data/configs/default_SUM.json')
   inData = ExMAS.utils.load_G(inData, params, stats=True)
   ```

2. Prepare input data:
   - Load and clean city zones, centroids, areas
   - Process demographic CSV and assign zone numbers
   - Load OD matrix and compute trip probabilities

3. Define simulation parameters:
   ```python
   degree = 6
   N = 100
   max_iter = 30
   ASC = 2.91
   ```

4. Run the main simulation:
   ```python
   results = fncs.simulate_MSA(gdf_areas, df_demo, gdf_centroid,
                                od, od_probs, hubs, inData, params,
                                "http://localhost:8080/otp/routers/default/plan",
                                degree, N, max_iter, ASC, results_period)
   ```

5. Save output:
   ```python
   results['Bronowice']['avg_sim_res'].to_csv('results/main_results/avg_sim_res_b.csv')
   ```

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
- **KPIs**: passenger hours, vehicle hours, occupancy (via `ExMAS`)
- **ASC sensitivity** over multiple simulation batches
- **Travel time convergence** and variance of MSA iterations

---

### 📂 Output Files

- `results/main_results/*.csv`: average results, KPIs, ASC batch runs
- `results/images/*.png`: visualizations
- `results/df_sum_*.csv`: per-trip detailed outputs

---

### 📈 Visualizations

SimFLEX includes scripts to produce:
- Modal share triangle plots
- ASC sensitivity scatter plots
- KPI histograms by area
- MSA convergence plots over 30 iterations

Based on obtained results compare feeder service performance for each preselected and conduct sensitivity analysis to interpret which areas benefit most from feeder deployment and under what utility assumptions.

---

If you're running new cities or want OpenTripPlanner integration, contact the core developers or open an issue!
