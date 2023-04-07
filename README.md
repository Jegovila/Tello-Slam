# Tello Slam ROS Noetic Ubuntu 20.04

Paquete de ROS para lanzar diferentes nodos de DJI Tello y ORB SLAM3 (Monocular). 

# Instalación

## 1. Tello Driver

Seguir las instrucciones de [Tello driver](https://github.com/Jegovila/tello_driver), este repositorio cuenta ya con un script (tello_init.py) para controlar el dron tomando en cuenta la pose obtenida con ORB SLAM3. Se requiere un workspace creado con catkin build

## 2. ORB SLAM3

Seguir las instrucciones de [ORB_SLAM3](https://github.com/Jegovila/ORB_SLAM3), de momento solo lo he probado con la versión Monocular, la cual se ha modificado a `MonoPubPose`, Para poder pubicar la pose de la cámara (tello) y poder controlar con ella. 

## 3. rqt_ez_publisher

Necesario para mandar posiciones deseadas con la interfaz gráfica. 
```
ros-noetic-rqt-ez-publisher
```

Con los sliders se manda la posición deseada en x,y,z. Para más información sobre cómo modificar la configuración de la interfaz, la página de [rqt_ez_publisher](http://wiki.ros.org/rqt_ez_publisher) 

## 4. Tello Slam

Ir a la misma ruta donde se encuentre Tello Driver

* `$ cd <CATKIN_WS/SRC>`
* `$ git clone https://github.com/Jegovila/Tello-Slam.git`
* `$ cd ..`
* `$ catkin build tello_slam`

## 5. Uso

Asegurarse de hacer source al `CATKIN_WS`. Después:

* `$ roslaunch tello_slam startNodes.launch`

La interfaz gráfica `rqt_ez_publisher` se puede modificar (tópicos, valores mínimos y máximos) y guardar el archivo de configuración .yaml, el archivo `tello_slam/launch/startNodes.launch` esta importando el archivo de configuración `tello_slam/config/rqt_pub.yaml`
