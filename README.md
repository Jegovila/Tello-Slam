# tello_slam ROS Noetic Ubuntu 20.04

Paquete de ROS para lanzar diferentes nodos de DJI Tello y ORB SLAM3 (Monocular). 

# Instalación

# 1. Tello Driver

Seguir las instrucciones de https://github.com/Jegovila/tello_driver, este repositorio cuenta ya con un script (tello_init.py) para controlar el dron tomando en cuenta la pose obtenida con ORB SLAM3. Se requiere un workspace creado con catkin build

# 2. ORB SLAM3

Seguir las instrucciones de https://github.com/Jegovila/ORB_SLAM3, de momento solo lo he probado con la versión Monocular, la cual se ha modificado a MonoPubPose, Para poder pubicar la pose de la cámara (tello) y poder controlar con ella. 

# 3. rqt_ez_publisher
```
ros-noetic-rqt-ez-publisher
```
# 4. Tello Slam

Ir a la misma ruta donde se encuentre Tello Driver

* `$ cd <CATKIN_WS/SRC>`
* `$ git clone https://github.com/Jegovila/tello_slam.git`
* `$ cd ..`
* `$ catkin build tello_slam`

