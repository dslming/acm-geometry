#### CGL_1_A(点在直线的投影)
<img src="./img/001.png" >

投影的长度:
```math
|AN| = |AM|cos(\theta)
```

根据点积公式:
$$
\begin{aligned}
AM \cdot AB &= |AM|\cdot|AB| cos(\theta) \\
|AN| &= (AM \cdot AB) / |AB|
\end{aligned}
$$

投影向量:
$$
\begin{aligned}
AN &= |AN|* AB/|AB|          \\
   &= (AM \cdot AB)AB / |AB|^2
\end{aligned}
$$

至此，就结束了。我们还可以用另一种思路：
- 先求点N占AB的比例

代码实现(摘自three.js/math/Line3):
```js
/**
 * 计算|AN|在|AB|长度的比例
 * point 是点 M
 */
function closestPointToPointParameter(point) {
  // 向量 AM
  _startP.subVectors(point, this.start);
  // 向量 AB
  _startEnd.subVectors(this.end, this.start)
  // 向量 AB 模长的平方
  const startEnd2 = _startEnd.dot(_startEnd)
  // 向量 AM和AB点积
  const startEnd_startP = _startEnd.dot(_startP);

  let t = startEnd_startP / startEnd2;
  return t;
}

// 向量AN
let t = closestPointToPointParameter(M)
let AN = _startEnd.multiplyScalar(t).add( this.start);
```
