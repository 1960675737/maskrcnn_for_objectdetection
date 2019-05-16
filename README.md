# Mask R-CNN for Object Detection

## install

Check [INSTALL.md](INSTALL.md) for installation instructions.

"configs" Folder for parameter files.We use Faster R-CNN with ResNet-101-FPN network  for target detection,and the corresponding parameter file is "e2e_faster_rcnn_R_101_FPN_1x.yaml".

"last_checkpoint" ducument stores the pre-trained model.the pre-trained model of Faster R-CNN with ResNet-101-FPN network:https://download.pytorch.org/models/maskrcnn/e2e_faster_rcnn_R_101_FPN_1x.pth

"tools" folder contains model training function and test function.

For training the model,here is an example for Faster R-CNN R-101 FPN with the 1x schedule:
```bash
python tools/train_net.py --config-file "configs/e2e_faster_rcnn_R_101_FPN_1x.yaml" SOLVER.IMS_PER_BATCH 2 SOLVER.BASE_LR 0.0025 SOLVER.MAX_ITER 720000 SOLVER.STEPS "(480000, 640000)" TEST.IMS_PER_BATCH 1
```
cfg parameters can be modified according to the actual situation.

More details about maskrcnn can be found at https://github.com/facebookresearch/maskrcnn-benchmark.
