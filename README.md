# YOLO Dataset for Students' Behavior Detection

## Steps
- Data collection and recording
- Convert videos into frames
- Data Labelling & Annotation 
- Convert Json format into txt format
- Splitting images and labels into train, val and test folders
- Model Training
- Detection Results

## Implementation
- Create & Activate Conda Environment

```
conda create –n yolov5 python=3.8
conda activate yolov5
```
- Clone YOLOv5 & Install Requirments
```
git clone https://github.com/ultralytics/yolov5.git
pip install -r requirements.txt
```
### Training Custom Model (Students' Behaviour Detection )
- Model training using pre-trained model (yolov5s.pt) model on GPU (device 0)
```
python train.py --img 640 --batch 16 --epochs 100 --data data.yaml --weights yolov5s.pt --device 0
```
### Exporting Model into ONNX
```
python export.py --weights runs/train/exp/weights/best.pt --include onnx
```

### Inference
```
python detect.py --weights runs/train/exp/weights/best.pt --source demo.mp4 --conf 0.25
```

### References

- https://docs.ultralytics.com/
- https://docs.ultralytics.com/yolov5/quickstart_tutorial/
- https://github.com/ultralytics/yolov5
