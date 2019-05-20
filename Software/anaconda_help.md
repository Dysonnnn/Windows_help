配置过程：
```cmd
(C:\ProgramData\Anaconda3) C:\Users\DDDDy>activate tensorflow  //启动tensorflow环境

(tensorflow) C:\Users\DDDDy>C:\Users\DDDDy\Documents\GitHub\
(tensorflow) C:\Users\DDDDy\Documents\GitHub\keras-yolo3>python
Python 3.5.6 |Anaconda, Inc.| (default, Aug 26 2018, 16:05:27) [MSC v.1900 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()

(tensorflow) C:\Users\DDDDy\Documents\GitHub\keras-yolo3>conda install keras
Fetching package metadata .............
Solving package specifications: .

Package plan for installation in environment C:\Users\DDDDy\AppData\Local\conda\conda\envs\tensorflow:

The following NEW packages will be INSTALLED:

    h5py:                2.8.0-py35h3bdd7fb_2
    hdf5:                1.10.2-hac2f561_1
    keras:               2.2.2-0
    keras-applications:  1.0.4-py35_1
    keras-base:          2.2.2-py35_0
    keras-preprocessing: 1.0.2-py35_1
    pyyaml:              3.13-py35hfa6e2cd_0
    scipy:               1.1.0-py35h4f6bf74_1
    yaml:                0.1.7-hc54c509_2

Proceed ([y]/n)? y

yaml-0.1.7-hc5 100% |###############################| Time: 0:00:00 485.32 kB/s
hdf5-1.10.2-ha 100% |###############################| Time: 0:01:17 470.86 kB/s
pyyaml-3.13-py 100% |###############################| Time: 0:00:00 300.06 kB/s
h5py-2.8.0-py3 100% |###############################| Time: 0:00:01 421.45 kB/s
keras-applicat 100% |###############################| Time: 0:00:00 199.94 kB/s
scipy-1.1.0-py 100% |###############################| Time: 0:30:51   7.64 kB/s
scipy-1.1.0-py 100% |###############################| Time: 0:00:29 481.96 kB/s
keras-preproce 100% |###############################| Time: 0:00:00 538.28 kB/s
keras-base-2.2 100% |###############################| Time: 0:00:00 490.82 kB/s
keras-2.2.2-0. 100% |###############################| Time: 0:00:00   3.03 MB/s

(tensorflow) C:\Users\DDDDy\Documents\GitHub\keras-yolo3>

(tensorflow) C:\Users\DDDDy\Documents\GitHub\keras-yolo3>python yolo3_one_file_to_detect_them_all.py -w yolo3.weights -i dog.jpg
Using TensorFlow backend.
Traceback (most recent call last):
  File "yolo3_one_file_to_detect_them_all.py", line 8, in <module>
    import cv2
ImportError: No module named 'cv2'


```


安装了 一些库。
```
    h5py:                2.8.0-py35h3bdd7fb_2
    hdf5:                1.10.2-hac2f561_1
    keras:               2.2.2-0
    keras-applications:  1.0.4-py35_1
    keras-base:          2.2.2-py35_0
    keras-preprocessing: 1.0.2-py35_1
    pyyaml:              3.13-py35hfa6e2cd_0
    scipy:               1.1.0-py35h4f6bf74_1
    yaml:                0.1.7-hc54c509_2
```



## [重磅！YOLOv3 的 TensorFlow 实现，GitHub 完整源码解析](https://zhuanlan.zhihu.com/p/56070368)



```

(C:\ProgramData\Anaconda3) C:\Users\DDDDy>
(C:\ProgramData\Anaconda3) C:\Users\DDDDy>
(C:\ProgramData\Anaconda3) C:\Users\DDDDy>
(C:\ProgramData\Anaconda3) C:\Users\DDDDy>activate tensorflow

(tensorflow) C:\Users\DDDDy>pip list
Package             Version
------------------- ---------
absl-py             0.4.1
astor               0.7.1
certifi             2018.8.24
gast                0.2.0
grpcio              1.12.1
h5py                2.8.0
Keras               2.2.2
Keras-Applications  1.0.4
Keras-Preprocessing 1.0.2
Markdown            2.6.11
mkl-fft             1.0.6
mkl-random          1.0.1
numpy               1.15.2
pip                 10.0.1
protobuf            3.6.0
PyYAML              3.13
scipy               1.1.0
setuptools          40.2.0
six                 1.11.0
tensorboard         1.10.0
tensorflow          1.10.0
termcolor           1.1.0
Werkzeug            0.15.2
wheel               0.31.1
wincertstore        0.2

(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>python convert_weight.py
python: can't open file 'convert_weight.py': [Errno 2] No such file or directory

(tensorflow) C:\Users\DDDDy>
(tensorflow) C:\Users\DDDDy>cd D:\Documents\GitHub\YOLOv3_TensorFlow

(tensorflow) C:\Users\DDDDy>d:

(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>python convert_weight.py
2019-05-07 01:06:45.778066: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX AVX2
2019-05-07 01:06:45.798983: I tensorflow/core/common_runtime/process_util.cc:69] Creating new thread pool with default inter op setting: 4. Tune using inter_op_parallelism_threads for best performance.
TensorFlow model checkpoint has been saved to ./data/darknet_weights/yolov3.ckpt

(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>python test_single_image.py ./data/demo_data/messi.jpg
2019-05-07 01:15:06.518843: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX AVX2
2019-05-07 01:15:06.534489: I tensorflow/core/common_runtime/process_util.cc:69] Creating new thread pool with default inter op setting: 4. Tune using inter_op_parallelism_threads for best performance.
Traceback (most recent call last):
  File "test_single_image.py", line 51, in <module>
    boxes, scores, labels = gpu_nms(pred_boxes, pred_scores, args.num_class, max_boxes=30, score_thresh=0.4, iou_thresh=0.5)
TypeError: gpu_nms() got an unexpected keyword argument 'iou_thresh'

(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>python video_test.py ./data/demo_data/video.mp4
warning: Error opening file (/build/opencv/modules/videoio/src/cap_ffmpeg_impl.hpp:856)
warning: ./data/demo_data/video.mp4 (/build/opencv/modules/videoio/src/cap_ffmpeg_impl.hpp:857)
2019-05-07 01:16:36.836474: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX AVX2
2019-05-07 01:16:36.849596: I tensorflow/core/common_runtime/process_util.cc:69] Creating new thread pool with default inter op setting: 4. Tune using inter_op_parallelism_threads for best performance.
Traceback (most recent call last):
  File "video_test.py", line 57, in <module>
    boxes, scores, labels = gpu_nms(pred_boxes, pred_scores, args.num_class, max_boxes=30, score_thresh=0.5, iou_thresh=0.5)
TypeError: gpu_nms() got an unexpected keyword argument 'iou_thresh'

(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
(tensorflow) D:\Documents\GitHub\YOLOv3_TensorFlow>
```