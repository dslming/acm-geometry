### CGL_1_C(判断三个点的位置关系)
![alt](./img/003.png)

[参考1](https://www.codenong.com/cs105260489/)
[参考2](https://www.cnblogs.com/wind-chaser/p/10889537.html)
```js
/**
 * 判断三个点的位置关系
 *                p2
 *
 * p0      p1
 *
 *                p2
 * @param {*} p0
 * @param {*} p1
 * @param {*} p2
 */
export function pointPositionRelation(p0, p1, p2) {
    // p0,p1,p2 逆时针方向
    const COUNTER_CLOCKWISE = 1
    // p0,p1,p2 顺时针
    const CLOCKWISE = 2
    // 完全相反, p1,p2在p0的两侧
    const ONLINE_BACK = 3
    // 方向相同（p1较远）
    const ONLINE_FRONT = 4
    // 方向相同（p2较远）
    const ON_SEGMENT = 5

    let dir = isLeft(p0, p1, p2)
    if (dir > 0) {
        return COUNTER_CLOCKWISE
    } else if (dir < 0) {
        return CLOCKWISE
    } else if (dir == 0) {
        let u = p1.clone().sub(p0)
        let v = p2.clone().sub(p0)
        let w = u.dot(v)
        if (w < 0) {
            return ONLINE_BACK
        } else {
            if (u.length() > v.length()) {
                return ONLINE_FRONT
            } else {
                return ON_SEGMENT
            }

        }
    }
}
```
