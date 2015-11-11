# Vertical Rhythm

## Description
A SASS-based tool that let's any designer create a vertical rhythm while designing in the browser.

## [DEMO](http://vicompany.github.io/vertical-rhythm/)
A collection of examples that displays the effects of a proper vertical rhythm.

## How it works
### Base typography
The goal of typography is to create balanced, readable and legible text. Good typography depends on many factors, luckily there are [calculators](http://www.pearsonified.com/typography/) that give a good indication of what combinations work best. Because we know designers are going to use the code, we wanted to start things of easy by letting them define the base font size and line height in pixels. These values are automatically converted to rems.
```
$px-font-size:   16;
$px-line-height: 24;
```

### Modular scales
The next step is selecting a modular scale. A modular scale is nothing more than a list of values that share the same relationship. For example: if we apply the golden section (1,618) to a base font size of 16px, the outcome would be:
*	Font size xs: 16 * 1,618<sup>-1</sup> = 9,89px
*	Font size s (starting point): 16px
*	Font size m: 16 * 1.618 = 25,89px
*	Font size l: 16 * 1,618<sup>2</sup> = 41,89px
*	Font size xl: 16 * 1,618<sup>3</sup> = 67,77px

There are 17 predefined modular scales:
```
$modular-scales: (
  "minor second": 1.067,
  "major second": 1.125,
  "minor third":  1.2,
  "major third": 1.25,
  "perfect fourth": 1.333,
  "augmented fourth": 1.414,
  "perfect fifth": 1.5,
  "minor sixth": 1.6,
  "golden section": 1.618,
  "major sixth": 1.667,
  "minor seventh": 1.778,
  "major seventh": 1.875,
  "octave": 2,
  "major tenth": 2.5,
  "major eleventh": 2.667,
  "major twelfth": 3,
  "double octave": 4
);
```

### Applying the Vertical Rhythm
Applying the vertical rhythm should be as easy as possible. For this, we've predefined 5 font sizes. To apply one of the font sizes to an element, you'll only need the following code (the mixin does the calculations):
```
small { @include vertical-rhythm($font-size-xs); }
p     { @include vertical-rhythm($font-size-s); }
h3    { @include vertical-rhythm($font-size-m); }
h2    { @include vertical-rhythm($font-size-l); }
h1    { @include vertical-rhythm($font-size-xl); }
```

### Alignment
To round it all up, aligning other elements can be done using predefined distance and size variables that are based on the vertical rhythm itself:
```
div { margin: $distance-s; }
img { height: $size-m; }
```

## License

Vertical Rhythm is licensed under the [MIT license](http://opensource.org/licenses/MIT).
