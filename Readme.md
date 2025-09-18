This repository contains benchmark results of recent object detection models on industrial surface defects datasets.

## 🗂️ Datasets

| Dataset | #Defects | Classes| Image Size | Train/Test Split | #Train Images | #Test Images |
| -------------------- | -------- | ------------------------------------------------------------------------------------------------------------------- | ---------- | ---------------- | ------------- | ------------ |
| **GC10-DET** Steel Surface Defects [Dataset](https://datasetninja.com/gc10-det) | 10       | **Punching**, **Welding line**, **Crescent gap**, **Water spot**, **Oil spot**, **Silk spot**, **Inclusion**, **Rolled pit**, **Crease**, **Waist folding** | 2048×1000  | 9:1              | 2063          | 229          |
| **NEU-DET** Steel Surface Defects [Dataset](https://www.kaggle.com/datasets/kaustubhdikshit/neu-surface-defect-database)  | 6        | **Crazing**, **Inclusion**, **Patches**, **Pitted surface**, **Rolled-in scale**, **Scratches**                                             | 200×200    | 4:1              | 1439          | 360          |
| **Wood Defect Detection** [Dataset](https://datasetninja.com/wood-defect-detection)     | 4        | **Crack**, **Knot with crack**, **Dead knot**, **Live knot**                                                                        | 2800×1024  | 4:1              | 1712          | 407          |

*Note: A subset of the Wood Defects dataset was used for this study.*

## ⚙️ Experimental Setup

**Hardware**: NVIDIA GeForce RTX 4090 (24GB VRAM)  
**Training**: 100 epochs, 320px (batch=64) / 640px (batch=32)  
**Metrics**: mAP@50 (Mean Average Precision at IoU 0.50), FPS (Frames per second - higher = faster inference)

### 🔩 **NEU-DET** Steel Surface Defects

<div align="center">

| Model | 320px (batch=64) |  | 640px (batch=32) |  |
| :---: | :---: | :---: | :---: | :---: |
|  | **mAP@50** | **FPS** | **mAP@50** | **FPS** |
| YOLOv5l | 0.723 | 370 | 0.742 | 188 |
| YOLOv6v3l | **0.770** | 436 | **0.770** | 168 |
| YOLOv7 | 0.744 | 500 | 0.682 | 256 |
| YOLOv8l | 0.726 | 357 | 0.734 | 161 |
| RT-DETR-l | 0.698 | 333 | 0.686 | 158 |
| YOLOv9e | 0.759 | 227 | 0.758 | 75 |
| YOLOv10l | 0.731 | 588 | 0.745 | 294 |
| YOLOv11n | 0.738 | 1009 | 0.753 | **840** |
| YOLOv11s | 0.721 | **1096** | 0.743 | 490 |
| YOLOv11m | 0.717 | 819 | 0.734 | 284 |
| YOLOv11l | 0.734 | 800 | 0.730 | 229 |


</div>

### ⚙️ **GC10-DET** Steel Surface Defects

<div align="center">

| Model | 320px (batch=64) |  | 640px (batch=32) |  |
| :---: | :---: | :---: | :---: | :---: |
|  | **mAP@50** | **FPS** | **mAP@50** | **FPS** |
| YOLOv5l | 0.685 | 344 | 0.691 | 238 |
| YOLOv6v3l | 0.676 | 431 | 0.700 | 221 |
| YOLOv7 | 0.704 | 454 | **0.726** | 344 |
| YOLOv8l | 0.613 | 322 | 0.680 | 238 |
| RT-DETR-l | 0.682 | 277 | 0.702 | 156 |
| YOLOv9e | **0.710** | 285 | 0.713 | 129 |
| YOLOv10l | 0.666 | 370 | 0.673 | 322 |
| YOLOv11n | 0.668 | **2364** | 0.716 | **1550** |
| YOLOv11s | 0.638 | 2252 | 0.697 | 1103 |
| YOLOv11m | 0.635 | 1543 | 0.691 | 555 |
| YOLOv11l | 0.657 | 1317 | 0.675 | 467 |

</div>

### 🌲 **Wood Defect Detection Dataset** 

<div align="center">

| Model | 320px (batch=64) |  | 640px (batch=32) |  |
| :---: | :---: | :---: | :---: | :---: |
|  | **mAP@50** | **FPS** | **mAP@50** | **FPS** |
| YOLOv5l | 0.757 | 666 | 0.823 | 370 |
| YOLOv6v3l | 0.762 | 507 | 0.827 | 359 |
| YOLOv7 | 0.767 | 625 | 0.623 | 476 |
| YOLOv8l | 0.754 | 500 | 0.833 | 303 |
| RT-DETR-l | 0.794 | 285 | 0.805 | 175 |
| YOLOv9e | **0.799** | 416 | 0.838 | 188 |
| YOLOv10l | 0.752 | 625 | 0.822 | 434 |
| YOLOv11n | 0.723 | **3021** | **0.857** | **2277** |
| YOLOv11s | 0.752 | 2695 | 0.843 | 1517 |
| YOLOv11m | 0.776 | 1858 | 0.839 | 751 |
| YOLOv11l | 0.774 | 1650 | 0.842 | 621 |

</div>

## 📄 Citation

```bibtex
@INPROCEEDINGS{10667164,
  author={Ghali, Rayen and Benhafid, Zhor and Selouani, Sid Ahmed},
  booktitle={2024 IEEE Canadian Conference on Electrical and Computer Engineering (CCECE)}, 
  title={Real-time defect detection systems for steel and wood inspection}, 
  year={2024},
  volume={},
  number={},
  pages={577-582},
  keywords={YOLO;Accuracy;Inspection;Feature extraction;Transformers;Real-time systems;Raw materials;Object detection;Surface defects;YOLO;DETR},
  doi={10.1109/CCECE59415.2024.10667164}}
```
