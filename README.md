# WLF7 Hands-on Workshop: Multi-Model Pore-Water Pressure Forecasting

Workshop code for forecasting downslope (PP1) and upslope (PP2) pore-water pressure using USGS BALT2 hillslope monitoring data.

**Presenter:** Amos Silungwe  
**Event:** 7th World Landslide Forum (WLF7)



## Repository contents

|File|Description|
|-|-|
|`wlf7\_xgboost\_handson\_workshop.py`|Python export of the workshop workflow.|
|`WLF7\_XGBoost\_HandsOn\_Workshop.ipynb`|Jupyter notebook with section headings, code, and practical workflow.|
|`requirements.txt`|Python package dependencies.|

## Workflow overview

The supplied notebook/script includes:

1. Library imports and reproducibility setup.
2. Loading and preparing the USGS BALT2 monitoring dataset.
3. Soil-moisture and pore-water-pressure preprocessing.
4. Time-series diagnostics and visualisations.
5. Sliding-window construction using a 48-step input window and 12-step output window.
6. Chronological train/validation/test partitioning.
7. LSTM model training and evaluation.
8. XGBoost regression for PP1 and PP2 at selected lead indices.

## Dataset

The workflow expects `USGS\_BALT2\_csv.csv`. The dataset is **not included** in this repository. Obtain it from the workshop organizer. 

The notebook and script currently refer to:

```python
df1 = pd.read\_csv("/content/USGS\_BALT2\_csv.csv")
```

For local execution, change this to the location of your authorized CSV, for example:

```python
df1 = pd.read\_csv("USGS\_BALT2\_csv.csv")
```

## Installation

Python 3.10 or later is recommended.

Create a virtual environment:

**Windows**

```bash
python -m venv .venv
.venv\\Scripts\\activate
```

**macOS / Linux**

```bash
python -m venv .venv
source .venv/bin/activate
```

Install dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Run the notebook

```bash
jupyter notebook
```

Open `WLF7\_XGBoost\_HandsOn\_Workshop.ipynb`, make the dataset available at the path expected by the notebook, and execute the cells in order.

## Run the Python script

After updating the CSV path in `wlf7\_xgboost\_handson\_workshop.py`, run:

```bash
python wlf7\_xgboost\_handson\_workshop.py
```

For an interactive workshop, the notebook is generally easier to follow cell by cell.

## Data-use and research integrity

* Do not publish private or restricted monitoring data.
* Do not commit credentials, access tokens, or other secrets.
* Confirm permissions before sharing derived datasets or figures.
* Report model metrics with the correct target units and forecast lead-time definitions.

## Citation

Please acknowledge the WLF7 hands-on workshop materials by Amos Silungwe when reusing or adapting this code. Add the final bibliographic details of the associated research manuscript when available.

