# R2-GVIO
A Robust, Real-Time GNSS-Visual-Inertial State Estimator in Urban Challenging Environments

Visual-Inertial Odometry (VIO) often suffers from drifting, particularly in large-scale environments. Concurrently, the Global Navigation Satellite System (GNSS) signals will be intermittent or even inaccessible in obstructed environments. In this work, we present a robust, real-time GNSS-visual-inertial state estimator, abbreviated as R$^2$-GVIO, that achieves drift-free six-degree-of-freedom accurate global positioning in urban challenging environments. Specifically, we integrate GNSS into the optimization-based monocular and stereo VIO, enabling the fusion of GNSS Real-time Kinematic (RTK), reprojection error, and IMU pre-integration within a factor graph framework. In addition, to enhance the R$^2$-GVIO’s robustness in GNSS-unfriendly environments, we propose an online GNSS measurement outlier detection and culling algorithm based on velocity constraints and a time synchronization mechanism. Furthermore, we propose a GNSS-aided initialization method that provides accurate gravity direction, IMU zero bias, and local-global external parameters. Experiments on public datasets and real-world experiments verify that in challenging environments, including urban canyons, complex indoor-outdoor, and large-scale environments, the positioning accuracy and robustness of the proposed R$^2$-GVIO algorithm are superior to the state-of-the-art algorithms VINS-Fusion, ORB-SLAM3, and IC-GVINS.


# SYSU-Campus-GVI-Dataset

### A campus scene GNSS-visual-inertial dataset collected at Sun Yat-sen University Shenzhen Campus.

We collected data from six representative scenes on the SYSU campus. The "\textit{Dormitory Building}" and "\textit{Engineering Building}" scenes, which have urban canyon characteristics, are affected by surrounding high-rise buildings or mountainous trees throughout. In the "\textit{Gymnasium Building}" and "\textit{Medical Building}" scenes, the data collection device goes from the open outdoors indoors and then back outdoors again. The "\textit{SYSU Campus}" and "\textit{Athletic Field}" scenes were collected in large-scale and repeated environments, respectively. The total duration of the SYSU-Campus-GVI datasets is about 3611 $s$, and the total driving distance is about 16456 $m$.

![github](https://github.com/SYSU-CPNTLab/SYSU-Campus-GVI-Dataset/assets/74598384/d519bd1b-2a92-45b6-902a-621812ab74e7)

### Data collection system
The data collection system is equipped with a RealSense D455 camera, which is used to collect visual data (including monocular and binocular, 30Hz) and IMU data (200Hz). In addition, the VI data synchronizes the GNSS measurements (5Hz) provided by VRTK2. The GNSS results are provided by the GNSS device equipped with two u-blox ZED-F9P modules and two antennas (AH 3232). 
![equip3](https://github.com/SYSU-CPNTLab/SYSU-Campus-GVI-Dataset/assets/74598384/ac345e7b-3440-4011-b9b0-56d08d7c445f)


### Details of the real-world dataset and technical details of the acquisition system

| SYSU-Campus-GVI Dataset | Description |
| --- | --- |
| Dormitory Building | Urban Canyon |
| | Duration: 523.833 s |
| | Distance: 2705.868 m |
| Engineering Building | Urban Canyon |
| | Duration: 620.109 s |
| | Distance: 2885.359 m |
| Gymnasium Building | Outdoor-Indoor-Outdoor |
| | Duration: 806.222 s |
| | Distance: 3455.805 m |
| Medical Building | Outdoor-Indoor-Outdoor |
| | Duration: 630.626 s |
| | Distance: 2932.079 m |
| Athletic Field | Repeating Textures |
| | Duration: 304.259 s |
| | Distance: 879.583 m |
| SYSU Campus | Large Scale |
| | Duration: 725.800 s |
| | Distance: 3597.251 m |

| Camera sensor | OmniVision Technologies OV9782 |
| --- | --- |
| Resolution | Up to 1280 × 800 px |
| Shutter Type | Global Shutter |
| FOV (H × V) | 90 × 65° |
| Frame Rate | 30 fps |

| Inertial Measurement Unit | Bosch BMI055 |
| --- | --- |
| Degrees of Freedom | 6 |
| Gyroscope frequency | 200 Hz |
| Accelerometer frequency | 200 Hz |
| Sample Timestamp Accuracy | 50 μs |

| GNSS | VRTK2 |
| --- | --- |
| Receiver | U-blox ZED-F9P × 2 |
| Antenna | AH 3232 × 2 |
| RTK Solution Frequency | 5 Hz |



### The data items within the rosbag are listed below:
| topic | type | frequency | description |
| :---: | :--: | :-------: | :---------: |
| /camera/imu | sensor_msgs/Imu | 200Hz | IMU measurments from D455|
| /camera/infra1/image_rect_raw | sensor_msgs/Image | 30Hz | left camera |
| /camera/infra2/image_rect_raw | sensor_msgs/Image | 30Hz | right camera |
| /fixposition/corrimu | sensor_msgs/Imu | 200Hz | IMU measurments from VRTK2| 
| /fixposition/gnss1 | sensor_msgs/NavSatFix | 5Hz | GNSS1 RTK position from VRTK2| 
| /fixposition/gnss2| sensor_msgs/NavSatFix | 5Hz | GNSS2 RTK position from VRTK2| 

### Data set download：
LINK: https://pan.baidu.com/s/1SiHDs3xduDLrfQUzlAEYEQ 

PASSWORD: CPNT 

### Related paper

  When using this SYSU-Campus-GVI-Dataset in academic work, please consider citing:

    @ARTICLE{10477234,
      author={Song, Jiangbo and Li, Wanqing and Duan, Chufeng and Zhu, Xiangwei},
      journal={IEEE Internet of Things Journal}, 
      title={R2-GVIO: A Robust, Real-Time GNSS-Visual-Inertial State Estimator in Urban Challenging Environments}, 
      year={2024},
      volume={},
      number={},
      pages={1-1},
      keywords={Global navigation satellite system;Cameras;Navigation;Visualization;Robustness;Real-time systems;Odometry;Visual-Inertial Odometry;GNSS;Sensor Fusion;Localization},
      doi={10.1109/JIOT.2024.3379755}}

    @ARTICLE{10384447,
      author={Song, Jiangbo and Li, Wanqing and Duan, Chufeng and Wang, Lei and Fan, Yiheng and Zhu, Xiangwei},
      journal={IEEE Transactions on Circuits and Systems II: Express Briefs}, 
      title={An Optimization-Based Indoor-Outdoor Seamless Positioning Method Integrating GNSS RTK, PS, and VIO}, 
      year={2024},
      volume={},
      number={},
      pages={1-1},
      doi={10.1109/TCSII.2024.3351172}}

Related paper:

[1]	J. Song, W. Li, C. Duan and X. Zhu, "R2-GVIO: A Robust, Real-Time GNSS-Visual-Inertial State Estimator in Urban Challenging Environments," in IEEE Internet of Things Journal, doi: 10.1109/JIOT.2024.3379755.

[2]	J. Song, W. Li, C. Duan, L. Wang, Y. Fan and X. Zhu, "An Optimization-Based Indoor-Outdoor Seamless Positioning Method Integrating GNSS RTK, PS, and VIO," in IEEE Transactions on Circuits and Systems II: Express Briefs, doi: 10.1109/TCSII.2024.3351172.





