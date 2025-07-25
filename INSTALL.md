# Installation

## Requirements
Follow the installation in this order to make sure the package versions are compatible with each other.

## Python Poetry
- Python >= 3.10 
- Poetry >= 2.0.0

## Main Dependencies
The main dependencies have been taken care for you with `poetry` (thanks Facebook) to make reproducability and installation easier. Here is how to set up your environment:
```bash
pip install poetry
poetry config virtualenvs.in-project true
poetry install
source .venv/bin/activate
```

## Extra
For now, this repo possesses Facebook's `Detectron2` repo for object detection and tracking. This may be updated with more SOTA tools out there, but for now, this is what will be used. It requires and additional step:
```bash
git clone https://github.com/facebookresearch/detectron2 detectron2_repo
poetry run pip install --no-build-isolation -e ./detectron2_repo
```
That should be it. 


Now the installation is finished, run the pipeline with:
```bash
python tools/run_net.py --cfg configs/Kinetics/C2D_8x8_R50.yaml NUM_GPUS 1 TRAIN.BATCH_SIZE 8 SOLVER.BASE_LR 0.0125 DATA.PATH_TO_DATA_DIR path_to_your_data_folder
```
