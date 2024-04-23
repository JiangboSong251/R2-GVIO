## R2-GVIO
A Robust, Real-Time GNSS-Visual-Inertial State Estimator in Urban Challenging Environments

Visual-Inertial Odometry (VIO) often suffers from drifting, particularly in large-scale environments. Concurrently, the Global Navigation Satellite System (GNSS) signals will be intermittent or even inaccessible in obstructed environments. In this work, we present a robust, real-time GNSS-visual-inertial state estimator, abbreviated as R$^2$-GVIO, that achieves drift-free six-degree-of-freedom accurate global positioning in urban challenging environments. Specifically, we integrate GNSS into the optimization-based monocular and stereo VIO, enabling the fusion of GNSS Real-time Kinematic (RTK), reprojection error, and IMU pre-integration within a factor graph framework. In addition, to enhance the R$^2$-GVIO’s robustness in GNSS-unfriendly environments, we propose an online GNSS measurement outlier detection and culling algorithm based on velocity constraints and a time synchronization mechanism. Furthermore, we propose a GNSS-aided initialization method that provides accurate gravity direction, IMU zero bias, and local-global external parameters. Experiments on public datasets and real-world experiments verify that in challenging environments, including urban canyons, complex indoor-outdoor, and large-scale environments, the positioning accuracy and robustness of the proposed R$^2$-GVIO algorithm are superior to the state-of-the-art algorithms VINS-Fusion, ORB-SLAM3, and IC-GVINS.
![equip3](https://github.com/JiangboSong251/R2-GVIO/assets/74598384/52560996-3777-4c0c-8038-ff918e2ee60a)

![map](https://github.com/JiangboSong251/R2-GVIO/assets/74598384/90385d4f-f2f4-4966-856d-53532c67a668)

## GVI_SYSU_Outdoor_Indoor_Dataset
This dataset contains complex indoor-outdoor converted GNSS-visual-inertial datasets collected in underground garages and buildings.


![data](https://github.com/SYSU-CPNTLab/GVI_SYSU_Outdoor_Indoor_Dataset/assets/74598384/2acb0519-cf70-4bb9-a803-9a535cc37263)


As depicted in Fig. \ref{equip}, our multi-sensor data acquisition device is versatile and can be utilized for both vehicle-mounted and handheld applications. The device integrates a variety of sensors, including a stereo camera and IMU from Realsense D455, two U-blox ZED-F9P modules from VRTK2 for RTK positioning information, and a smartphone for pressure sensor (barometer) measurements. All sensor data are synchronized using timestamps. We have collected five datasets in a variety of complex indoor-outdoor scenarios, encompassing outdoor environments, underground locations, and building interiors. 


##  Dataset Details
### The dataset is released in the form of rosbag and currently there are 6 rosbags available:

| name | duration | size |
| :--: | :------: | :--: |
| GVI_SYSU_UG1.bag | 413s | 9.47GB |
| GVI_SYSU_UG2.bag | 407s | 9.32GB |
| GVI_SYSU_CPNT.bag | 830s | 19.00GB |
| GVI_SYSU_Building_LC.bag | 606s | 13.87GB |
| GVI_SYSU_Building_L.bag | 511s | 11.71GB |
| GVI_SYSU_Building_C.bag | 591s | 13.54GB |



### The data items within the rosbag are listed below:
| topic | type | frequency | description |
| :---: | :--: | :-------: | :---------: |
| /camera/imu | sensor_msgs/Imu | 200Hz | IMU measurments from D455|
| /camera/infra1/image_rect_raw | sensor_msgs/Image | 30Hz | left camera |
| /camera/infra2/image_rect_raw | sensor_msgs/Image | 30Hz | right camera |
| /fixposition/corrimu | sensor_msgs/Imu | 200Hz | IMU measurments from VRTK2| 
| /fixposition/gnss1 | sensor_msgs/NavSatFix | 5Hz | GNSS1 RTK position from VRTK2| 
| /fixposition/gnss2| sensor_msgs/NavSatFix | 5Hz | GNSS2 RTK position from VRTK2| 


## Related paper
### When using this Dataset in academic work, please consider citing:

    @ARTICLE{10384447,
      author={Song, Jiangbo and Li, Wanqing and Duan, Chufeng and Wang, Lei and Fan, Yiheng and Zhu, Xiangwei},
      journal={IEEE Transactions on Circuits and Systems II: Express Briefs}, 
      title={An Optimization-Based Indoor-Outdoor Seamless Positioning Method Integrating GNSS RTK, PS, and VIO}, 
      year={2024},
      volume={},
      number={},
      pages={1-1},
      doi={10.1109/TCSII.2024.3351172}}


### Related paper:

[1]	J. Song, W. Li, C. Duan, L. Wang, Y. Fan and X. Zhu, "An Optimization-Based Indoor-Outdoor Seamless Positioning Method Integrating GNSS RTK, PS, and VIO," in IEEE Transactions on Circuits and Systems II: Express Briefs, doi: 10.1109/TCSII.2024.3351172.


##  Dwonload
Data set download link：https://pan.baidu.com/s/16r17_SFyLk3FEW6osD0UhA 
Password：cpnt 


