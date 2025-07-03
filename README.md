Project Overview:
This project demonstrates real-time object detection using the YOLOv7 model in Google Colab. A pre-trained YOLOv7 model (yolov7.pt) is used to detect and classify multiple objects (like person, backpack, potted plant, tie) from video frames, processed with GPU acceleration (e.g., Tesla T4).

Setup Instructions:

Mount Google Drive:
from google.colab import drive
drive.mount('/content/gdrive')
%cd /content/gdrive/My\ Drive/

Create project folder:
import os
if not os.path.isdir('TheCodinBug'):
os.mkdir('TheCodinBug')
%cd TheCodinBug

Clone the YOLOv7 GitHub repo:
!git clone https://github.com/WongKinYiu/yolov7.git
%cd yolov7

Download YOLOv7 pretrained weights:
!wget https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7.pt

Confirm you're in the correct directory:
!pwd

Should show: /content/gdrive/MyDrive/TheCodinBug/yolov7
Running Object Detection on Video:

Replace pes2.mp4 with your own video file name:

!python detect.py --weights yolov7.pt --conf 0.5 --img-size 640 --source pes2.mp4

Options:
--conf: confidence threshold
--img-size: input image size (default 640)
--source: video/image path or camera input (e.g., 0)

Output:
Results are saved in: runs/detect/exp/

How It Works:

Loads YOLOv7 model with PyTorch

Converts model to optimized inference mode

Processes video frames and applies:

Bounding box detection

Class predictions

Non-Maximum Suppression

Annotated frame output

Dependencies:

Python 3.10+

PyTorch 2.5.1 with CUDA (e.g., cu121)

OpenCV

NumPy

TorchVision

Install all dependencies:
pip install -r requirements.txt

Optional Features:

Use webcam: --source 0

Display frame during inference: --view-img

Save predictions to text: --save-txt --save-conf

Detect only specific classes: --classes

Adjust IoU threshold: --iou-thres

Train model on custom dataset (advanced)

Sample Folder Structure:

TheCodinBug/
├── yolov7/
│ ├── detect.py
│ ├── models/
│ ├── runs/
│ │ └── detect/exp/
│ ├── yolov7.pt
│ └── ...
└── pes2.mp4

Checklist:

[x] Mount Drive
[x] Clone repo
[x] Download weights
[x] Upload video
[x] Run detection
[x] Check runs/detect/exp/ for results

Author / Contact:

Name: Syeda Shamama Afeef

