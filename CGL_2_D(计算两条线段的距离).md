
### CGL_2_D(计算两条线段的距离)
https://lianming.gitee.io/geometrytest/%E7%BA%BF%E6%AE%B5%E6%9C%80%E5%B0%8F%E8%B7%9D%E7%A6%BB/

```js
export function distanceBetweenLines2(segA, segB, lineA, lineB) {
    let lineBAAxis = lineB.clone().sub(lineA).normalize();
    let inPlaneA = segA.clone().sub(lineA).projectOnPlane(lineBAAxis).add(lineA);
    let inPlaneB = segB.clone().sub(lineA).projectOnPlane(lineBAAxis).add(lineA);
    let inPlaneBA = inPlaneB.clone().sub(inPlaneA);
    let t = lineA.clone().sub(inPlaneA).dot(inPlaneBA) / inPlaneBA.lengthSq();
    let rayPoint = segA.clone().lerp(segB, Math.min(Math.max(t, 0), 1));
    let ab = closestToSegment(rayPoint, segA, segB)
    let cd = closestToSegment(ab, lineA, lineB)
    return ab.distanceTo(cd)
}
```
