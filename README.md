# Tello Slam ROS Noetic Ubuntu 20.04

Paquete de ROS para lanzar diferentes nodos de DJI Tello y ORB SLAM3 (Monocular). 

```youtube-embed
{
   "width": "560",
   "height": "315",
   "src": "https://www.youtube.com/embed/dQw4w9WgXcQ",
   "title": "YouTube video player",
   "frameborder": "0",
   "allow": "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture",
   "allowfullscreen": true
}
```

# Instalación

## 1. Tello Driver

Seguir las instrucciones de [Tello driver](https://github.com/Jegovila/tello_driver), este repositorio cuenta ya con un script (tello_control.py) para controlar el dron tomando en cuenta la pose obtenida con ORB SLAM3. Se requiere un workspace creado con catkin build

## 2. ORB SLAM3

Seguir las instrucciones de [ORB_SLAM3](https://github.com/Jegovila/ORB_SLAM3), de momento solo lo he probado con la versión Monocular, la cual se ha modificado para poder publicar la pose de la cámara (tello) y poder controlar con ella. 

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

* `$ roslaunch tello_slam tello_slam_control.launch`: Control de posición a través de la gui 
* `$ roslaunch tello_slam tello_slam_mapping.launch`: Movimiento predefinido solo para mapeo

La interfaz gráfica `rqt_ez_publisher` se puede modificar (tópicos, valores mínimos y máximos) y guardar el archivo de configuración .yaml, los archivos `tello_slam_control.launch` y `tello_slam_mapping.launch` están importando el archivo de configuración `tello_slam/config/rqt_pub.yaml`
