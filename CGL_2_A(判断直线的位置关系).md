### 判断直线的位置关系

```js
/**
 * create by dslming 2020/9/4
 * 依赖 three.js, sylvester.js
 * @note 所有输入输出的向量均使用THREE.Vector3, sylvester只是中间计算
 */

// 计算时判定的误差
const EP = 0.00001
const SylLine = Line
const SylVector = Vector


export function isZero(val, ep) {
    ep = ep || EP;
    return Math.abs(val) < ep;
}

export function isZeroVector(vector={x:0, y:0, z:0}) {
    // 将对象转为数组
    const vectorArr = Object.values(vector)
    for (var i = 0; i < vectorArr.length; i++) {
        if (!isZero(vectorArr[i]))
            return false;
    }
    return true;
}

/**
 * 判断两条线是否垂直
 * @param {*} v1
 * @param {*} v2
 * @note 向量内积：a*b=|a||b|*cos(Y) 当cos为0时正交(90,-90垂直)
 */
export function isOrthogonal(v1, v2) {
 if(isZeroVector(v1) || isZeroVector(v2)) return false

 const ret = v1.clone().dot(v2)
 if(Math.abs(ret-0)<EP) return true
 else return false
}

/**
 * 判断两条线是否平行
 * @param {*} v1
 * @param {*} v2
 */
export function isParallel(v1, v2) {
    if(isZeroVector(v1) || isZeroVector(v2)) return false

    let v = v1.clone().cross(v2)
    return isZeroVector(v);
}
```
