# total_control

## Paso 1: Correr tópicos de la zed
New terminal
```
roslaunch zed_wrapper zed2.launch
```
New terminal
```
rosrun zed_depth_sub_tutorial zed_depth_sub
```
    _Si se desea revisar la zed correr en otra terminal rqt Iage View
    ```
    $rosrun rqt_image_view rqt_image_view
    ``` 
## Paso 2: Correr paquete total_control
New Terminal
```
$roslaunch total_control total_control.launch
```
New Terminal
```
$rostopic echo flag/nav_auto
```
New Terminal (Para Introducir los comandos)
```
$#Para deshabilitar la navegación autónoma
$rostopic pub /total_control/nav_auto std_msgs/String "'0'"
$#Para habilitar la navegación autónoma
$rostopic pub /total_control/nav_auto std_msgs/String "'1'"
```
## Paso 3: Correr paquete decisión_auto
New terminal
```
$roslaunch decision_auto decision_auto.launch
```
New terminal
```
$rostopic echo nav/obstacle
```
## Paso 4: Correr paquete nav_dif
New terminal
```
$roslaunch nav_dif nav_dif.launch
```
New terminal
```
$rostopic echo cmd_vel
```
