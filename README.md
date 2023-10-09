# MISAHUB Challenge



## Installation

First two cells in the ipynb file are for downloading the dataset.

## How Yolov5 is run:
1. Installation of Yolov5
```
!git clone https://github.com/ultralytics/yolov5  # clone
%cd yolov5
!pip install -r requirements.txt  # install
```
2. Create a data.yaml file in the yolov5 directory:
```
!touch data.yaml
```
paste the data_yolo.yaml provided in the data.yaml created.

3. Come out of the yolov5 directory:

```
%cd ..
```
4. move the train, val and test set generated from the bleeding data provided.
```
!mv train_data yolov5
!mv val_data yolov5
!mv test_dir yolov5
```

5. To train the yolo model:
```
%cd /content/yolov5
!python train.py --epochs 50 --data data.yaml --weights ../yolov5s.pt --cache
```

6. to detect values on the test dataset:
```
!python detect.py --source test_dir/images --weights /content/yolov5/runs/train/exp4/weights/best.pt --save-txt
```
the path after the weights argument is the path to the pt file generated after training.



