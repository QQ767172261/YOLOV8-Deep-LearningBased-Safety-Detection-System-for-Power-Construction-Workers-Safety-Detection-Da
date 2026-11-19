基于深度学习YOLOV8电力施工人员安全检测系统![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f9096980c8804038b37952056200264c.png)
  电力施工人员安全检测数据集，9438张，提供yolo和voc两种标注方式![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/cbd0f5f1f9ca41fe956bdb3882bfab92.png)

图像尺寸:612*459（图像尺寸不一）
类别数量:20类![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/faebc1e756c74c7099d27f9c619b33df.png)

训练集图像数量:8695; 验证集图像数量:494； 测试集图像数量:249
类别名称: 每一类图像数 ，每一类标注数
Helmet-头盔：7808,11282![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/dfc9ca792c4144b5b459fc340e500aa8.png)

Powerlines_cover-电线保护套：1013,3230
On_bucket-在桶上：1380,2144
Glasses-眼镜：4521,4961
Gloves-手套：6469,11759
Worker-工人：6021,8469
Multimeter-万用表：1875,1880
On_pole-在杆上：1949,2337
Cone-锥形物：2163,5570
No_gloves-没有手套：292,431
Stick-棍子：2767,2935
Voltage_detector-电压检测器：658,673
Ground_conductor-接地导体：1022,3523
On_ladder-在梯子上：1667,1937
Lifeline-生命线：1470,1476
No_helmet-没有头盔：35,40
Ground-地面：343,363
Bucket_lanyard-桶绳：166,207
Person-人：544,673
Stay-固定装置：26,26
image num: 9438![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/37df0cedb5334594a5f5ffa62f85632d.png)


.模型代码：模型训练使用yolov11n训练，30个epoch训练结果，map如描述图所示。![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/b203d52c0e3647fa9fa24573a951e58a.png)

.qt界面：运行界面采用pyqt编写，本项目已经训练好模型，配置好环境后可直接使用，运行效果见描述图像


# 电力施工人员安全检测数据集![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/838726efd79b41c2bac6fd5afc1f3805.png)


| 项目 | 详情 |
| --- | --- |
| 数据集名称 | 电力施工人员安全检测数据集 |
| 任务类型 | 目标检测 |
| 总图片数量 | 9438张 |
| 图像尺寸 | 612*459，图像尺寸不统一 |
| 标注格式 | YOLO、VOC两种标注格式 |
| 数据集划分 | 训练集：8695张   验证集：494张   测试集：249张 |
| 类别（共20类） | Helmet-头盔：7808张，11282个标注   Powerlines_cover-电线保护套：1013张，3230个标注   On_bucket-在桶上：1380张，2144个标注   Glasses-眼镜：4521张，4961个标注   Gloves-手套：6469张，11759个标注   Worker-工人：6021张，8469个标注   Multimeter-万用表：1875张，1880个标注   On_pole-在杆上：1949张，2337个标注   Cone-锥形物：2163张，5570个标注   No_gloves-没有手套：292张，431个标注   Stick-棍子：2767张，2935个标注   Voltage_detector-电压检测器：658张，673个标注   Ground_conductor-接地导体：1022张，3523个标注   On_ladder-在梯子上：1667张，1937个标注   Lifeline-生命线：1470张，1476个标注   No_helmet-没有头盔：35张，40个标注   Ground-地面：343张，363个标注   Bucket_lanyard-桶绳：166张，207个标注   Person-人：544张，673个标注   Stay-固定装置：26张，26个标注 |
| 配套项目 | YOLOv11n训练代码，30epoch训练权重；PyQt可视化检测界面完整源码，配套数据集标签文件，环境配置完成即可直接运行推理 |

## 数据集摘要![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/78512f035ea244548be15a96770401d9.png)


本数据集为电力施工现场安全目标检测数据集，总计9438张实拍图片，分为20个类别，覆盖施工人员、安全帽、手套、护目镜、各类电力工具、登高设施、安全防护用品以及违规状态（未戴头盔、未戴手套）。数据集已经预先划分训练/验证/测试集，提供YOLO、VOC双格式标注。配套YOLOv11n训练代码、训练完成权重、PyQt可视化界面源码，开箱即可训练、推理演示。

## 应用价值

1. 电力施工现场AI安全监管，安全帽、手套等防护用品佩戴合规检测，违规行为识别告警
2. 电力施工工具、登高设施、线路配件自动识别统计
3. YOLOv11系列目标检测算法训练、对比实验、毕业设计、科研论文
4. 电网智慧工地、电力巡检安全监控系统开发落地

## YOLOv11训练yaml标签配置

```
path: ./
train: images/train
val: images/val
test: images/test

names:
  0: Helmet
  1: Powerlines_cover
  2: On_bucket
  3: Glasses
  4: Gloves
  5: Worker
  6: Multimeter
  7: On_pole
  8: Cone
  9: No_gloves
  10: Stick
  11: Voltage_detector
  12: Ground_conductor
  13: On_ladder
  14: Lifeline
  15: No_helmet
  16: Ground
  17: Bucket_lanyard
  18: Person
  19: Stay
```

## 极简PyQt推理主程序（配套）

```
from PyQt5.QtWidgets import *
from PyQt5.QtGui import *
from PyQt5.QtCore import *
from ultralytics import YOLO
import cv2
import os

class MainWindow(QWidget):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("电力施工安全检测系统")
        self.resize(1100,700)
        self.model = YOLO("yolov11n_best.pt")
        self.init_ui()

    def init_ui(self):
        layout = QVBoxLayout()
        self.img_label = QLabel()
        self.img_label.setAlignment(Qt.AlignCenter)
        self.btn_open = QPushButton("选择图片检测")
        self.btn_open.clicked.connect(self.detect_img)
        layout.addWidget(self.img_label)
        layout.addWidget(self.btn_open)
        self.setLayout(layout)

    def detect_img(self):
        file,_ = QFileDialog.getOpenFileName()
        if not file:return
        res = self.model(file)[0]
        img = res.plot()
        img = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
        h,w = img.shape[:2]
        qimg = QImage(img.data,w,h,w*3,QImage.Format_RGB888)
        self.img_label.setPixmap(QPixmap.fromImage(qimg).scaled(900,600,Qt.KeepAspectRatio))

if __name__ == "__main__":
    app = QApplication([])
    win = MainWindow()
    win.show()
    app.exec()
```


