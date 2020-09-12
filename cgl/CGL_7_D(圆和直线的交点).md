###  CGL_7_D(求圆和直线的交点)
![alt](./img/005.png)

**思路:**
- 求圆心在线段的投影点`pr`
- 根据勾股求出`base` 的长度
- 可以求出`p1,p2`向量的方向
- 最后,以`pr`为起点,向正负两个方向增加`base`长度

```js
/**
 * 计算线和圆的交点
 * @param c: 圆心坐标
 * @param r: 圆的半径
 * @param p1: 线段的第一个点
 * @param p2: 线段的第二个点
 * 
 */
export function lineAndCircleIntersec(c,r,p1,p2) {
    let pr = projection(c, p1, p2)
    let cprLength = c.distanceTo(pr)
    if(cprLength == r) {
        return pr
    } else if(cprLength > r) {
        return null
    }
    let baseLength = Math.sqrt(r*r-cprLength*cprLength)
    let dir = p2.clone().sub(p1).normalize()
    let ret = []
   
    ret[0] = pr.clone().add(dir.clone().multiplyScalar(baseLength))
    ret[1] = pr.clone().add(dir.clone().negate().multiplyScalar(baseLength))
    return ret
}
```