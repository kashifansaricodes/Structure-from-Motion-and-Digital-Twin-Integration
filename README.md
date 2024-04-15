# Installing Prerequisites

## Importing the python environment
> Note: Replace ENV_NAME with any relevant name of your choice
```
# Can replace conda with mamba
conda create -n ENV_NAME python=3.9
conda activate ENV_NAME
pip install -r requirements.txt
```

## Running the app (current Version)
```
cd src/v1
python featmatch.py --data_dir ../../data/fountain-P11/images/ --out_dir ../../data/fountain-P11/ --features SURF
python sfm.py --dataset fountain-P11 --features SURF --pnp_method SOLVEPNP_DLS
```
