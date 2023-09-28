# R2-GVIO
A Robust, Real-Time GNSS-Visual-Inertial State Estimator in Urban Challenging Environments

Visual-Inertial Odometry (VIO) often suffers from drifting, particularly in large-scale environments. Concurrently, the Global Navigation Satellite System (GNSS) signals will be intermittent or even inaccessible in obstructed environments. In this work, we present a robust, real-time GNSS-visual-inertial state estimator, abbreviated as R$^2$-GVIO, that achieves drift-free six-degree-of-freedom accurate global positioning in urban challenging environments. Specifically, we integrate GNSS into the optimization-based monocular and stereo VIO, enabling the fusion of GNSS Real-time Kinematic (RTK), reprojection error, and IMU pre-integration within a factor graph framework. In addition, to enhance the R$^2$-GVIO’s robustness in GNSS-unfriendly environments, we propose an online GNSS measurement outlier detection and culling algorithm based on velocity constraints and a time synchronization mechanism. Furthermore, we propose a GNSS-aided initialization method that provides accurate gravity direction, IMU zero bias, and local-global external parameters. Experiments on public datasets and real-world experiments verify that in challenging environments, including urban canyons, complex indoor-outdoor, and large-scale environments, the positioning accuracy and robustness of the proposed R$^2$-GVIO algorithm are superior to the state-of-the-art algorithms VINS-Fusion, ORB-SLAM3, and IC-GVINS.
![equip3](https://github.com/JiangboSong251/R2-GVIO/assets/74598384/52560996-3777-4c0c-8038-ff918e2ee60a)

![map](https://github.com/JiangboSong251/R2-GVIO/assets/74598384/90385d4f-f2f4-4966-856d-53532c67a668)
