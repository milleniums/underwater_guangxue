1. 数据转换为coco格式(code/data2coco)：`xml2csv.py`将训练数据的xml形式转换为csv，`create_train.py`和`data2coco_unerwater.py`将csv转换为COCO形式，`create_test.py`将测试数据转换为COCO形式.

2. 使用mmdetection框架对数据集进行训练：`./dist_train.sh ../configs/atss50_600-1000.py 1`

3、利用训练好的模型进行前传：`./dist_test.sh  ../configs/atss50_600-1000.py work_dirs/atss50_640.pth 1 --json_out results/atss50_640`

4、将不同尺度的结果融合并进行后处理（code/ensemble）：`ensemble.py`融合`atss_r50`和`atss_r101`各个尺度的答案，`transform.py`矫正越界的bbox位置

本次光学比赛B榜成绩0.48211259，使用了6个模型，模型的网盘地址为：
链接: https://pan.baidu.com/s/1fEweftyL62xl0O1BqJDDnQ 提取码: tw4g
