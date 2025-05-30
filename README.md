# README
## 要将VOC数据集转换为coco数据，使用voctococo.py
## 模型训练、测试、可视化、对新数据应用模型的一些细节
将data文件放入mmdetection中
为了用tensorboard可视化训练过程将在configs文件夹下的default_runtime中的hooks中的 dict(type='TensorboardLoggerHook')取消注释
要在mmdetection框架中训练mask_rcnn模型在mmdection终端中输入
!python tools/train.py configs/mask_rcnn/mask_rcnn_r50_fpn_1x_coco.py
训练sparse_rcnn输入的是
!python tools/train.py configs/sparse_rcnn/sparse_rcnn_r50_fpn_1x_coco.py
在work_dirs目录下会生成日志文件、权重文件、对应的配置文件、tensorboard记录文件
终端输入tensorboard --logdir=#tensorboard文件的目录可以进行tensorboard可视化
测试输入：
python tools/test.py configs/mask_rcnn/mask_rcnn_r50_fpn_1x_coco.py work_dirs/mask_rcnn_r50_fpn_1x_coco/epoch_12.pth --out ./test_result/mask_rcnn_r50_fpn_1x/latest.pkl --eval bbox segm --show-dir vis_results --eval bbox segm

python tools/test.py configs/sparse_rcnn/sparse_rcnn_r50_fpn_1x_coco.py work_dirs/sparse_rcnn_r50_fpn_1x_coco/epoch_12.pth --out ./test_result/sparse_rcnn_r50_fpn_1x/latest.pkl --eval bbox segm --show-dir vis_results --eval bbox segm
会输出test_result以及vis_results

在new.ipynb中进行模型在data中new文件夹下的新图片应用
 
