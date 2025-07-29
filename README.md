代码仓中，如果使用 miniconda 或者 anaconda，那么可以直接从 `environment.yml` 导入项目的虚拟环境。

## 运行环境参考（Excution Environment）：

> 1.python 3.7.1  
> 2.pytorch 1.0.1  
> 3.python-opencv  

## 说明（Notions）

预训练的权重文件[vgg_16]

1、具体的配置文件请看 Config.py 文件--file that save the configuration    
2、训练运行 python Train.py        --file that start the training and control the loops  
3、单张测试 python test.py         --file that test ssd with one image  
4、测试网络性能 python eval.py     --file that evaluate the performance  
5、测试视频 python camera_detection.py --file that test the cnn with a video sequence  

## 目前进度（Process: All Done）：

| 内容             | 进度 |
| ---------------- | ---- |
| PERCLOS 计算     | DONE |
| 眨眼频率计算     | DONE |
| 打哈欠检测及计算 | DONE |
| 疲劳检测         | DONE |

## 主要文件说明（File in the repo）：

ssd_net_vgg.py 定义 class SSD 的文件（define the ssd cnn）  
Train.py 训练代码  (training)  
voc0712.py 数据集处理代码（没有改文件名，改的话还要改其他代码，麻烦）  (processing the dataset)  
loss_function.py 损失函数  (loss function)  
detection.py 检测结果的处理代码，将 SSD 返回结果处理为 opencv 可以处理的形式   
eval.py 评估网络性能代码    
test.py 单张图片测试代码 Ps:没写参数接口，所以要改测试的图片就要手动改代码内部文件名了    
l2norm.py l2 正则化    
Config.py 配置参数     
utils.py 工具类  
camera.py opencv 调用摄像头测试  
camera_detection.py 摄像头检测代码 V1,V2  
video_detection.py 视频检测，V3

## 数据集结构：

> /dataset:
>
> > /Annotations 存放含有目标信息的 xml 文件  
> > /ImageSets/Main 存放图片名的文件  
> > /JPEGImages 存放图片  
> > /gray2rgb.m 灰度图转三通道  
> > /txt.py 生成 ImageSets 文件的代码

## 权重文件存放路径：

weights
测试后的图片存放位置：
tested

## 数据集和权重文件：
（针对部分代码中涉及的文件（指ssd_voc_5000_plus.pth），翻了翻旧U盘，算是找到了。）
百度云：
[数据集和权重文件](https://pan.baidu.com/s/1cgl94gxSNEW0ZI-wYcZtpQ)
提取码：hwsi  
Onedrive：
[数据集](https://mailustceducn-my.sharepoint.com/:u:/g/personal/mpf916_mail_ustc_edu_cn/ER0UB-cAe1VDp9hJZ7e5Ef4B7kGvVX4PePSj7WRtb9VrLQ?e=lbDnjV)
[权重文件](https://mailustceducn-my.sharepoint.com/:f:/g/personal/mpf916_mail_ustc_edu_cn/EqGCPA3SGz5Mp-RMHJSoSSwBg-KG09qwgSAPiOjMOcVVtQ?e=v5yhQz)

## 测试

1、运行 Train.py 训练
2、eval 可以用于测试整个测试集，test 用于单张图片测试。

## 运行
更改test.py中图片路径就可对单张图片进行检测
直接运行camera_detection.py可以进行实时检测
