# labelImg_auto_annotation
This aims to leverage existing object detectors to ease data annotation process by automatically detecting the objects in the image. You can correct the bounding boxes that are detected by the object detector. The project is based on the [LabelImg](https://github.com/tzutalin/labelImg.git). For the auto-annotation, [mmdetection](https://github.com/open-mmlab/mmdetection) library is used.

![Alt Text](demo_annotation.gif)

## Auto-annotation Model (mmdetection model)
You need to have config file from openmmlab detection and model checkpoint to be able to run auto annotation model. The predicted classes by the model should be added to the data folder as a txt file. (Please check predefined_model_classes.txt for the format). Classes should be in the same order with the model predictions.

## Installation
To install LabelImg please follow the instructions on the official [labelImg](https://github.com/tzutalin/labelImg/blob/master/README.rst) repository. To install object detector related installation, please follow the instructions of the [mmdetection](https://github.com/open-mmlab/mmdetection) library.

## How to run the project?

```
python3 labelImg.py [IMAGE_PATH] [PRE-DEFINED CLASS FILE]  --config [MODEL CONFIG FILE PATH] --checkpoint [MODEL FILE PATH]

Example:
python labelImg.py  --model_class_file data/predefined_model_classes.txt --config configs/swin_backbone_pretrained_coco_on_COMICS.py --checkpoint models/swin_backbone_pretrained_coco_on_COMICS_epoch_9.pth
```

