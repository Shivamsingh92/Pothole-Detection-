
🚀 YOLOv5 Custom Object Detection - Summary

✅ Framework: Used Ultralytics YOLOv5 (yolov5s.pt pre-trained model)


📁 Dataset Structure:
data/
├── images/
│   ├── train/
│   └── val/
├── labels/
│   ├── train/
│   └── val/
data.yaml

✏️ data.yaml:
- train: Path to training images
- val: Path to validation images
- nc: Number of classes
- names: Class names (e.g., ['pothole'])

🏋️ Training Command:
from ultralytics import YOLO
model = YOLO('yolov5s.pt')
model.train(data='data.yaml', epochs=30, imgsz=640, batch=16)

📈 Important Metrics:
- box_loss: Bounding box error
- obj_loss: Confidence (objectness) loss
- cls_loss: Class prediction loss
- mAP@0.5: Accuracy at IoU 0.5
- mAP@0.5:0.95: Real-world accuracy (stricter)

📂 Training Output Folder:
runs/train/exp/
- best.pt: Best weights
- results.png: Graph of losses & mAP
- results.csv: Epoch-wise metrics

🔍 Inference:
model = YOLO('runs/train/exp/weights/best.pt')
results = model('path/to/image.jpg')
results.show(), results.save()


