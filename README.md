# FE8K-eval

An installable library for the AiCityChallenge2024 Track4 evaluation.

Based on [FishEye8K](https://github.com/MoyoG/FishEye8K) and [pycocotools](https://github.com/cocodataset/cocoapi)

## Installation
```
pip install git+https://github.com/deepdrivepl/FE8K-eval.git
```

## Example
```python
from pycocotools.coco import COCO
from pycocotools.cocoeval_modified import COCOeval

GT_PATH = "path/to/your/labels.json"
RES_PATH = "path/to/your/predictions.json"

coco_gt = COCO(GT_PATH)
coco_dt = coco_gt.loadRes(RES_PATH)

coco_eval = COCOeval(coco_gt, coco_dt, 'bbox')
coco_eval.evaluate()
coco_eval.accumulate()
coco_eval.summarize()
```
