
### CGL_2_D(计算两条线段的距离)


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
