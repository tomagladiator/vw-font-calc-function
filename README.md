# vw-font-calc-function
fluid for two breakpoints
```scss
@function fluid($smallValue, $largeValue) {
    // font-size: fluid(15px, 26px);

    $small: 375px;
    $large: 1440px;

    $m: ($largeValue - $smallValue) / ($large - $small);
    $b: $smallValue - $m * $small;

    $sign: "+";

    @if ($b < 0) {
        $sign: "-";
        $b: abs($b);
    }

    @return calc(#{$m*100}vw #{$sign} #{$b});
}
```
