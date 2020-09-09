### CGL_2_B(求交点)

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
export function ccw(p0, p1, p2) {
    // p0,p1,p2 逆时针方向
    const COUNTER_CLOCKWISE = -1
    // p0,p1,p2 顺时针
    const CLOCKWISE = 1
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

/**
 * 判断两条线段是否有交点
 * @param {*} p0
 * @param {*} p1
 * @param {*} p2
 * @param {*} p3
 */
export function intersect(p1, p2, p3, p4) {
    // p3,p4在p1,p2的两侧
    let t1 = ccw(p1, p2, p3)
    let t2 = ccw(p1, p2, p4)
    let t3 = ccw(p3, p4, p1)
    let t4 = ccw(p3, p4, p2)
    if (t1 * t2 < 0 && t3 * t4 < 0) {
        return true
    } else {
        return false
    }
}
```
