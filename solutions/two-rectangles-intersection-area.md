# Find an area of the intersection of two rectangles

## Task 

```
class Rect {
  double x, y, width, height;   
  // you can use x1, y1, x2, y2 properties, too
}
```
`double intersectionArea(Rect r1, Rect r2)`

## Solution

```typescript
class Rect {
  double x, y, width, height;   
    constructor(public x: number,
                public y: number,
                public width: number,
                public height: number) {
                    if( isNaN(x) || 
                        isNaN(y) || 
                        isNaN(width) || 
                        isNaN(height)) throw new Error('Value is NaN');
                    
                    if( width === 0 || height === 0 ) throw new Error('Rectangle area is 0');
                }    

    public get maxX() {
        return this.x + width;
    }

    public get maxY() {
        return this.y + height;
    }

    public inersectsRectangle(r: Rect) {
        return this.x < r.maxX() && this.maxX() > r.x &&
            this.y < r.maxY() && this.maxY() > r.y;
    }

    public getIntersectedArea(r: Rect) {
        if(!this.intersectsRectange(r)) return 0;     
        const intersectionWidth: number = Math.min(this.maxX(), r.maxX()) - Math.max(this.x, r.x);
        const intersectionHeight: number = Math.min(this.maxY(), r.maxY()) - Math.max(this.y, r.y);

        return intersectionWidth * intersectionHeight;
    }
}


// check how it works: 
const r1 = new Rect(0, 0, 5, 5);
const r2 = new Rect(3, 3, 6, 6);

function intersectionArea(r1: Rect, r2: Rect) {
    return r1.getIntersectedArea(r2);
}
const area1 = intersectionArea(r1, r2);
// or ...
const area2 = r1.getIntersectedArea(r2);
```

## Limitations
* As the area is just AxB, where both A and B are doubles, we can reach maximum value of the double type variable, calculating the area of the intersection, if `intersectedWidth x intersectedHeight > double`