# Installing Prerequisites

### Conda or Mamba Environment
```sh
conda create -n <name> python=3.9

or

mamba create -n <name> python=3.9
```

### Activate Environment
```sh
mamba activate <name>

or

conda activate <name>
```

### Install Packages
```sh
pip install numpy opencv-python

CMAKE_ARGS="-DOPENCV_ENABLE_NONFREE=ON" pip install -v --no-binary=opencv-contrib-python opencv-contrib-python
```

### Running the app (current Version)
```
cd src/v1
python featmatch.py --data_dir ../../data/fountain-P11/images/ --out_dir ../../data/fountain-P11/ --features SURF
python sfm.py --dataset fountain-P11 --features SURF --pnp_method SOLVEPNP_DLS
```
