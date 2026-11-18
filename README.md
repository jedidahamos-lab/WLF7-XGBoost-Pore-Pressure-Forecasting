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

## Dataset

The workflow uses the USGS BALT2 monitoring dataset (`USGS_BALT2_csv.csv`).

**The dataset is not included in this repository.** Participants must obtain the authorised dataset from the workshop organiser.

### Uploading the dataset in Google Colab

1. Open the Jupyter notebook in Google Colab.
2. Run the first data-loading cell under **Upload and inspect the source data**.
3. Click **Choose Files** when the upload prompt appears.
4. Select `USGS_BALT2_csv.csv` from your computer.
5. The notebook automatically captures the uploaded filename and loads the dataset.

The notebook uses:

```python
from google.colab import files

uploaded = files.upload()
csv_path = next(iter(uploaded))

raw = pd.read_csv(csv_path)
```

**For local execution:** Replace the Google Colab upload lines with the path to your authorised local dataset:

```python
csv_path = "USGS_BALT2_csv.csv"
raw = pd.read_csv(csv_path)
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

