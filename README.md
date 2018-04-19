# Rail Transit in GHM Greater Bay Area (TfL Standard)

## Standard Sizes
![CHandX](/elements/CHandX.svg)

For simplicity, x-height is set to be 6. Correspondingly, the size of latin scripts is `8.5pt` and the size of CJK scripts is `6.7pt`. The cap-height is 8 (rounded to integer). 

## Line Thickness
![LineThickness](/elements/LineThickness.svg)

The thickness of the route line equals to x-height. Non metro lines would be shown as solid lines, which are to be displayed as parallel lines. The styling properties with CSS can be defined as

```xml
<style type="text/css">
    .LineDiagram {fill:none;stroke-width:6}
    .NonMetro {stroke:#fff;stroke-width:2}
</style>
```

Station ticks are $2x/3=4$ squared. This object can be definded as

```xml
<defs>
    <path id="st" class="StationTick" d="M 2,0 H 7"/>
    <path id="term" class="StationTick" d="M -7,0 H 7"/>
</defs>
```

## Interchange Circles
text

## Radii and Angles
The line must be drawn at an angle of 45&deg; or 90&deg; where a change of direction is necessary. $3x=18$ is applied to the innermost curve where lines run adjacent. 

The arc takes two arguments for x-radius and y-radius (same as it's arc of a circle). Considering the line thickness, these two arguments should be $\displaystyle rx=ry=18+6/2=21$. This is also called turning radius. 

| DIRECTION | PATH CODE |
|:---:|---|
| &rarr; &#8600; &darr; | `a 21,21 0 0,1 21,21` |
| &rarr; &#8599; &uarr; | `a 21,21 0 0,0 21,-21` |
| &darr; &#8601; &larr; | `a 21,21 0 0,1 -21,21` |
| &darr; &#8600; &rarr; | `a 21,21 0 0,0 21,21` |
| &larr; &#8598; &uarr; | `a 21,21 0 0,1 -21,-21` |
| &larr; &#8601; &darr; | `a 21,21 0 0,0 -21,21` |
| &uarr; &#8599; &rarr; | `a 21,21 0 0,1 21,-21` |
| &uarr; &#8598; &larr; | `a 21,21 0 0,0 -21,-21` |


![image](/elements/LineDiagram.svg)