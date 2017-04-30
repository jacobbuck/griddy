# griddy

Simple grid framework for Sass.

## Getting Started

First off you'll need to import griddy to use it:

```scss
@import 'path/to/griddy';
```

To define a row element of your layout:

```scss
.some-row {
  @include griddy-row;
}
```

And to define a column element:

```scss
.some-column {
  @include griddy-column(1 of 2);
}
```

Columns can also be offset:

```scss
.some-column {
  @include griddy-column(1 of 2);
  @include griddy-offset(1 of 4);
}
```

The width parameter in `griddy-column` and `griddy-offset` can be a percentage (i.e. `25%`) or a human readable fraction (i.e. `1 of 4`).

You can also define gutters for your grid layout:

```scss
.some-row {
  @include griddy-row($gutter: 20px);
}

.some-column {
  @include griddy-column(1 of 2, $gutter: 20px);
}

.some-offset-column {
  @include griddy-column(1 of 4, $gutter: 20px);
  @include griddy-offset(1 of 4, $gutter: 20px);
}
```

Or globally define your gutter width:

```scss
$griddy-gutter: 20px;

.generic-row {
  @include griddy-row;
}

.generic-column {
  @include griddy-column(1 of 2);
}

.special-row {
  @include griddy-row($gutter: 40px);
}

.special-column {
  @include griddy-column(1 of 2, $gutter: 40px);
}
```

Or have no gutter:

```scss
$griddy-gutter: 0;
```

If you need to clear the preceding column in your layout:

```scss
.some-column:nth-child(3n+1) {
  @include griddy-clear;
}
```

By default griddy's direction is left-to-right, however you can change this by setting:

```scss
$griddy-direction: right;
```

## Browser Support

Works on all modern browsers which support `box-sizing` and `calc()`.

If you need support Internet Explorer 8, you might want to check out version [1.0.2](https://github.com/jacobbuck/griddy/tree/1.0.2).

## License

MIT - see [license](license)
