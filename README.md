# useful
Helper functions for Love2D development made by me and for me; you can use them and stuff though.

# Math
* all members of `math` brought into global scope
* `tau` - equals `pi * 2`
* `lerp(start, stop, amount)` - linearly interpolates `start` to `stop` by `amount`
* `keepBetween(x, minimum, maximum)` - loops x between minimum and maximum inclusively; for example, if minimum is 3 and maximum is 5, and x starts at 0 and increases every function call, the return values will be `3, 4, 5, 3, 4, 5, 3, 4, 5`
* `round(number, decimal = 1)` - rounds `number` to nearest number divisible by `decimal`; for example `round(15.6, 1)` returns `16` and `round(15.6, 0.5)` returns `15.5`
* `sign(x)` - returns the sign of `x`; positive numbers return `1`, negative numbers return `-1`, zero returns `0`
* `bti(x)` - converts boolean values to integers; `true` becomes `1` and `false` becomes `0`
* `clamp(x, minimum, maximum)` - returns the value of `x` clamped between `minimum` and `maximum`
* `dist(x1,y1,x2,y2)` - returns the geometric distance between `(x1,y1)` and `(x2,y2)`
* `dist2(x1,y1,x2,y2)` - returns the squared distance between `(x1,y1)` and `(x2,y2)`; because this function does not use `sqrt(x)`, it is recommended for optimization to use this function when the exact magnitude of the distance is not needed, such as when comparing which of two distance is greater
* `dsin(x)`, `dcos(x)`, `dtan(x)` - trigonometric functions for values of `x` in degrees
* `dasin(x)`, `dacos(x)`, `datan(x)` - inverse trigonometric functions for values of `x` that return degrees
* `offsetToPolar(x,y)` - converts Cartesian coordinates `(x,y)` to polar coordinates; returns `radians, distance`
* `polarToOffset(radians, distance)` - converts polar coordinates `(radians, distance)` to Cartesian coordinates; returns `x,y`
* `rotateTowardsAngle(start, stop, amount)` - lerps `start` angle to `stop` angle (in radians), avoiding rotational errors near the wraparound point; for example, if `start` is `3 * pi / 2` and `stop` is `0`, `start` will lerp towards `2 * pi` instead of towards `0`

# Table
* `dupeTable(tab)` - returns a deep copy of `tab`
* `choose(tab)` - returns a random value from `tab`
* `keys(tab)` - returns a table containing all of the key values of `tab`
* `tableToStr(name)` - serializes a table into a format which can be printed cleanly or exported to a file
* `contains(tab, value)` - returns whether `tab` contains the value `value`

# Love2D Drawing
* `drawShadow(draw_function, arg, x, y, etc_args...)` - draws a drawable with a shadow by calling `draw_function(arg, x + 1, y + 1, etc_args...)` with the color `0,0,0`, followed by calling `draw_function(arg, x, y, etc_args...)` with the currently set color. This function only works if `draw_function()` has `x` and `y` as the second and third arguments.
* `drawImg(img, x, y, scale, center)` - draws `img` at `x` and `y` with x and y scale of `scale`; if `center` is true, then image will be centered at `x` and `y`
