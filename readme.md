[题目目录](https://vjudge.net/article/753)
[python实现参考](https://github.com/koba925/PCAD)
说明: 代码使用js语言

[题型](https://www.cometoj.com/problems?source_id=11&tag_ids=226,239,240,227,228,241,242,243,244,245,229,246,247,248,249,250,330,230,251,252,253,254,231,232,233,234,235,236,237,238,344&page=1)

[图片出处](https://www.cnblogs.com/bztMinamoto/category/1345570.html)
![alt](./img/001.png)


[题汇总](https://www.cnblogs.com/bztMinamoto/category/1413022.html)

[计算几何资源汇总 oi-wiki](https://oi-wiki.org/geometry/2d/)

[acm入门](https://blog.csdn.net/cfreezhan/article/details/8189226)

### todo:
- [ ] 旋转卡壳
- [ ] LOJ_6544
- [ ] 最小圆覆盖 [参考](https://zhuanlan.zhihu.com/p/83611398)
- [ ] BZOJ3775(拉格朗日乘数法)

#### 初级
 (1)几何公式.
     (2)叉积和点积的运用(如线段相交的判定,点到线段的距离等). (poj2031,poj1039)
     (3)多边型的简单算法(求面积)和相关判定(点在多边型内,多边型是否相交)
         (poj1408,poj1584)
     (4)凸包. (poj2187,poj1113)
#### 中级
  (1)坐标离散化.
        (2)扫描线算法(例如求矩形的面积和周长并,常和线段树或堆一起使用).
            (poj1765,poj1177,poj1151,poj3277,poj2280,poj3004)
        (3)多边形的内核(半平面交)(poj3130,poj3335)
        (4)几何工具的综合应用.(poj1819,poj1066,poj2043,poj3227,poj2165,poj3429)

#### 高阶：
      (1)半平面求交(poj3384,poj2540)
      (2)可视图的建立(poj2966)
      (3)点集最小圆覆盖.
      (4)对踵点(poj2079)
      八.综合题.
      (poj3109,poj1478,poj1462,poj2729,poj2048,poj3336,poj3315,poj2148,poj1263)

思想:
- 极限: 当可行解可以取连续一段值时，很多时候只要考虑边界的极限情况。
- 平面扫描：扫描线在平面上按既定轨迹移动时，不断根据扫描线扫过的部分更新，从而得到整体所求结果。扫描的方法，可以从左向右平移与y轴平行的直线，也可以固定射线的端点逆时针旋转。
