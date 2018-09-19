# PyCINRAD
A python package which handles CINRAD radar data reading and plotting.

读取CINRAD雷达数据，进行相关计算并可视化的模块。

## 安装

```
python setup.py
```

## 模块介绍

### cinrad.datastruct

构建本模块所使用的数据类型

基本类型: `cinrad.datastruct.Raw`

反射率数据类型: `cinrad.datastruct.R` (base: `cinrad.datastruct.Raw`)

速度数据类型: `cinrad.datastruct.V` (base: `cinrad.datastruct.Raw`)

该基本类型包含该要素数据，经纬度数据和雷达其他信息（雷达站名，扫描时间等）

### cinrad.io

读取CINRAD雷达数据。

例子：

```python
from cinrad.io import CinradReader
f = CinradReader(your_radar_file)
f.reflectivity(elevation_angle_level, data_range) #获取反射率数据（为cinrad.datastruct.R类型）
f.velocity(elevation_angle_level, data_range) #获取速度数据（为cinrad.datastruct.V类型）
```

### cinrad.utils

提供雷达衍生产品的计算（接受`numpy.ndarray`）

### cinrad.easycalc

提供雷达衍生产品的计算（接受`cinrad.datastruct.Raw`）

### cinrad.visualize

雷达数据可视化，目前包括`cinrad.visualize.ppi`

例子：

```python
from cinrad.visualize.ppi import base_reflectivity
base_reflectivity(R) #绘制基本反射率图片

from cinrad.visualize.ppi import base_velocity
base_velocity(V) #绘制基本速度图片
```


未完待续

回波顶高及垂直积分液态含水量算法来源：肖艳姣, 马中元, 李中华. 改进的雷达回波顶高、垂直积分液态水含量及其密度算法[J]. 暴雨灾害, 2009, 28(3):20-24.

PS:如在使用该脚本中有任何问题和建议，可以发邮件给我 274555447@qq.com
