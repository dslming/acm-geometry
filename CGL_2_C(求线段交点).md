> 参考: https://blog.csdn.net/Dog_dream/article/details/83097078
### CGL_2_C(求线段交点)
![alt](./img/004.png)

**思路:**
- 根据点到直线的距离,求出: `d1`和`d2`
- 根据三角的相似性, $d1:d2=|cK|:|dK|$
- 设: $t=|ck|/|cd|, => K=a+cd*t$
