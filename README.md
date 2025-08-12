# Vehicle Detection using YOLOv8

This project implements vehicle detection using the YOLOv8 model. It includes a complete pipeline for converting XML annotations to YOLO format, visualizing the dataset, and training the model.

---

## Dataset

- **Classes:**  
  - Car  
  - Bus  
  - Motorbike  
  - Truck  

- **Dataset Structure:**  
vehicle/
├── train/
│ ├── images/
│ ├── Final Train Dataset/ # XML annotation files for training
│ └── labels/ # YOLO label files (generated)
├── val/
│ └── images/ # Validation images
└── data.yaml # Dataset config file for YOLO training

- **data.yaml content example:**  
```yaml
train: C:/Users/manus/Downloads/vehicle/train/images
val: C:/Users/manus/Downloads/vehicle/val/images
nc: 4
names: ['car', 'bus', 'motorbike', 'truck']
Code Overview
vehicle_detection.py
Convert XML to YOLO format:
Parses Pascal VOC XML annotations to YOLO format text files with normalized bounding boxes.

Visualize Dataset:
Generates bar plots and histograms showing object counts and bounding box size distributions per class.

Train YOLOv8:
Loads a pre-trained YOLOv8n model and trains it on the dataset using parameters defined in the script.
How to Use
Setup directory paths in vehicle.py for:

XML annotations (XML_DIR)

Output YOLO labels (YOLO_LABELS_DIR)

Dataset YAML file (DATA_YAML)

Install dependencies:

bash
Copy
Edit
pip install ultralytics matplotlib
Run the script:

bash
Copy
Edit
python vehicle.py
This will:

Convert all XML annotations to YOLO label format.

Visualize the distribution of objects and bounding box sizes.

Train the YOLOv8 model on your dataset. 
Notes
Ensure all XML files are correctly formatted and images have corresponding XML annotations.

The batch size, epochs, and image size can be adjusted in the train_model() function.

The YOLOv8 pretrained weights (yolov8n.pt) will be automatically downloaded by the ultralytics library if not present.
