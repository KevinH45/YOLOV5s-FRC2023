# YOLOV5s-FRC2023
An object detecting system powered by YOLOV5 small for use in FRC'S Charge Up Game.

## Implementation Details
- Download the dataset here: https://universe.roboflow.com/michael-jansen/frc-charged-up-game-pieces/model/7
- Get YOLOV5

## To Run on Team Computer (Windows 10):
1) Move Cone Data Folder into yolov5-master folder (rename to customdata)
```
In data.yaml:
train: ../customdata/train/images
val: ../customdata/valid/images
test: ../customdata/test/images
[KEEP THE REST THE SAME]
```
2) Run the following commands
```
cd yolov5-master
py -m pipenv shell
pip install -r requirements.txt
pip uninstall torch torchvision pillow
pip install torch --index-url https://download.pytorch.org/whl/cu117
pip install torchvision --index-url https://download.pytorch.org/whl/cu117
pip install Pillow==9.5.0
pip freeze
set GIT_PYTHON_REFRESH=quiet
py train.py --img 640 --epochs 3 --data customdata/data.yaml --weights yolov5s.pt --batch 8
```
3) Find the results in runs/train/exp[EXP NUM]/best.pt
