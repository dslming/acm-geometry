[题目目录](https://vjudge.net/article/753)
[python实现参考](https://github.com/koba925/PCAD)
说明: 代码使用js语言

[题型](https://www.cometoj.com/problems?source_id=11&tag_ids=226,239,240,227,228,241,242,243,244,245,229,246,247,248,249,250,330,230,251,252,253,254,231,232,233,234,235,236,237,238,344&page=1)

[图片出处](https://www.cnblogs.com/bztMinamoto/category/1345570.html)
![alt](./img/001.png)


[题汇总](https://www.cnblogs.com/bztMinamoto/category/1413022.html)

[计算几何资源汇总 oi-wiki](https://oi-wiki.org/geometry/2d/)
### todo:
- [ ] 旋转卡壳
- [ ] LOJ_6544
- [ ] 最小圆覆盖 [参考](https://zhuanlan.zhihu.com/p/83611398)
- [ ] BZOJ3775(拉格朗日乘数法)

思想:
- 极限: 当可行解可以取连续一段值时，很多时候只要考虑边界的极限情况。
- 平面扫描：扫描线在平面上按既定轨迹移动时，不断根据扫描线扫过的部分更新，从而得到整体所求结果。扫描的方法，可以从左向右平移与y轴平行的直线，也可以固定射线的端点逆时针旋转。