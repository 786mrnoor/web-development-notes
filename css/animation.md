# CSS Animation

An animation lets an element gradually change from one style to another.

## `@keyframes`

control the steps in an animation sequence by defining CSS styles for points along the animation sequence.

> **Note:** CSS declarations with `!important` is ignored in a keyframe:

```css
@keyframes mymove {
  from {top: 0px;}  /* from is same as 0% */
  50%  {background: blue !important;} /* ignored */
  to   {top: 200px;} /* to is same as 100% */
}
```

## CSS Animation Properties

- `animation-name` - Specifies the name of the `@keyframes` animation
- `animation-duration` - Specifies how long time an animation should take to complete one cycle
- `animation-timing-function` - Specifies the speed curve of the animation
- `animation-delay` - Specifies a delay for the start of an animation
- `animation-iteration-count` - Specifies the number of times an animation should be played
- `animation-direction` - Specifies whether an animation should be played forwards, backwards or in alternate cycles
  - `normal` Default value. The animation is played as normal (forwards)
  - `reverse` - The animation is played in reverse direction (backwards)
  - `alternate` - The animation is played forwards first, then backwards
  - `alternate-reverse` - The animation is played backwards first, then forwards
- `animation-fill-mode` - Specifies a style for the element when the animation is not playing (before it starts, after it ends, or both)
  - `none` - 	Default value. Animation will not apply any styles to the element before or after it is executing
  - [`forwards`](https://www.w3schools.com/cssref/tryit.php?filename=trycss3_animation-fill-mode) - The element will retain the style values that is set by the last keyframe (depends on animation-direction and animation-iteration-count)
  - [`backwards`](https://www.w3schools.com/cssref/tryit.php?filename=trycss3_animation-fill-mode2) - The element will get the style values that is set by the first keyframe (depends on animation-direction), and retain this during the animation-delay period
  - [`both`](https://www.w3schools.com/cssref/tryit.php?filename=trycss3_animation-fill-mode3) - The animation will follow the rules for both forwards and backwards, extending the animation properties in both directions
- `animation-play-state` - Specifies whether the animation is running or paused
  - `paused`
  - `running`