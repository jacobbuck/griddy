Griddy
======

Simple grid framework for Sass.

Getting Started
---------------

First off you'll need to import griddy to use it:

```
@import 'path/to/griddy';
```

To define a row element of your layout:

```
.some-row {
	@include griddy-row;
}
```

And to define a column element:

```
.some-column {
	@include griddy-column(1 of 2);
}
```

Columns can also be offset:

```
.some-column {
	@include griddy-column(1 of 2);
	@include griddy-offset(1 of 4);
}
```

The width parameter in `griddy-column` and `griddy-offset` can be a percentage (i.e. `25%`) or a human readable fraction (i.e. `1 of 4`).

You can also define gutters for your grid layout:

```
.some-row {
	@include griddy-row(20px);
}

.some-column {
	@include griddy-column(1 of 2, 20px);
}
```

Or globally define your gutter width:

```
$griddy-gutter: 20px;

.generic-row {
	@include griddy-row;
}

.generic-column {
	@include griddy-column(1 of 2);
}

.special-row {
	@include griddy-row(40px);
}

.special-column {
	@include griddy-column(1 of 2, 40px);
}
```

Or have no gutter:

```
$griddy-gutter: 0;
```

If you need to clear the preceding column in your layout:

```
.some-column:nth-child(3n+1) {
	@include griddy-clear;
}
```

By default griddy's direction is left-to-right, however you can change this by setting:

```
$griddy-direction: right;
```

Browser Support
---------------

Works on all modern browsers. If you need support for older browsers, you might want to check out version `1.0.2`.

License
-------

MIT - see [LICENSE](LICENSE)
