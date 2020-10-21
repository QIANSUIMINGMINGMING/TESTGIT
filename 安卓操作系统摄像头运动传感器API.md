# 安卓操作系统摄像头/运动传感器API

### 相机

显然，在室内导航的过程中，必须持续访问手机摄像头，以下是实现必要功能的安卓系统下用框架API直接控制相机硬件的方法。（JAVA语言）

#### 涉及的包：android.hardware.camera2, android. view

##### andriod.hardware.camera2

+ CameraDevice:
+ CameraManager:
+ 

##### android. view

+ SurfaceView
+ SurfaceHolder

### 运动传感器

坐标系问题，安卓系统下运动传感器使用的是以手机左上角为原点，x、y、z轴方向大致如图所示的坐标系。

![Sensors coordinate-system diagram.](https://developer.android.google.cn/images/axis_device.png?hl=zh-cn)

世界坐标系：

- z轴正方向 垂直于地面向上
- y轴正方向与z轴垂直，指向北。
- x轴垂直于z轴与y轴确定的平面，指向东

对手机坐标转换为世界坐标可以：将得到的原始传感器值（即设备坐标下的值）和坐标轴的旋转矩阵相乘即可。

安卓提供方法得到旋转矩阵，位于android.hardware包的SensorManager类中。

`SensorManager.getRotationMatrix(R,I,gravityRawValues,magFieldRawValue);`

陀螺仪：检测设备在三个坐标轴上的旋转，单位（rad/s），逆时针旋转为正，安卓中的**TYPE_GYROSCOPE**表示使用该设备

`public static final int TYPE_GYROSCOPE`

获取值的方式，SensorEvent.values[],这是浮点数组，第0，1，2位分别表示关于x，y，z轴的旋转速率。（其他运动传感器也相同，0，1，2分别表示关于x、y、z轴的数据）

#### 涉及的包：android.hardware

几个最重要的class：

+ Sensor：
+ SensorManager：
+ SensorEvent:

+ SensorEventListener：

#### 使用方法：

陀螺仪的初始化：

```java
private SensorManager sensorManager;
private Sensor sensor;
...
sensorManager =(SensorManager)getSystemService(Context.SENSOR_SERVICE);
sensor = sensorManager.getDefaultSensor(Sensor.TYPE_GYROSCOPE);
```

