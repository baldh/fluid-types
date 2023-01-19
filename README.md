## CSS `clamp()` and type fluidity

`clamp()` takes three parameters -
- a minimum value
- an ideal value
- a maximum value 

```css
.classname {
    font-size: clamp(1rem, 1rem + 3vw, 2rem);
}
``` 

The above snippet not only creates a full responsive text based on the viewport width but also fixes the minimum and maximum size of the 
font so that the font doesn't get too small or too big. 

## Calculating the "preferred value" 

The formula to calculate the "preferred value" is => `y = ((v/100) * x) + r` , where

- x - current viewport width value (`px`)
- y - resulting fluid font size for a current viewport width (`px`)
- v - viewport width value that affects fluid value change rate (`vw`) 
- r - relative size equal to the root font size. Default value is `16px`



## Calculating "preferred value" based on specific starting and ending points
`v = (100(y2 - y1))/(x2 - x1)`

`r = (x1y2 - x2y1)/(root-font-size*(x1 - x2))`

Here
- `y1` = minimum font size
- `x1` = viewport width at which font size is minimum
- `y2` = maximum font size
- `x2` = viewport width at which font size is maximum 