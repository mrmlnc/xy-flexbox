# XY (flexbox)

> XY (flexbox) is a small and very flexible collection of mixins for building grids based on flexbox.

![Bower version](https://img.shields.io/bower/v/xy-flexbox.svg)

## What is?

This is a collection of mixins for all preprocessors (Less, Stylus, Sass), which you can use to create a grid that is convenient for you and your project.

If you need to set only the width of columns - you just do it. Later you can add offset, push or pull for the columns using the appropriate mixin.

## WTF? Flexbox? The future?

Ok. See the [XY (float)](https://github.com/mrmlnc/xy-float).

## Have suggestions?

Welcome to the [Issues](https://github.com/mrmlnc/xy-flexbox/issues)!

## How to use

Just import the file, which includes mixins in your project.

```less
// Less
@import "lib/xy";
// Sass
@import "lib/xy";
// Stylus
@import "lib/xy";
```

## Mixins

  * [xy-make-container](#xy-make-container)
  * [xy-make-container-width](#xy-make-container-width)
  * [xy-make-row](#xy-make-row)
  * [xy-make-column](#xy-make-column)
  * [xy-make-columns-width (offset, push, pull)](#xy-make-columns-width-offset-push-pull)
  * [xy-make-grid-columns](#xy-make-grid-columns)

## Utilities

  * [xy-make-row-align](#xy-make-row-align)
  * [xy-make-columns-order](#xy-make-columns-order)
  * [xy-make-columns-align](#xy-make-columns-align)

### xy-make-container

> Creates a container

Parameters:

  * **gutter** - distance between columns

### xy-make-container-width

> Defines of the maximum width for the container

Parameters:

  * **breakpoint** - device breakpoint
  * **width** - container width

### xy-make-row

> Creates a row

Parameters:

  * **gutter** - distance between columns

### xy-make-column

> Creates a column

Parameters:

  * **gutter** - distance between columns

### xy-make-columns-(width, offset, push, pull)

> Defines of width (offset, push or pull) for the column

Parameters:

  * **alias** - the alias of the current layout (breakpoint)
  * **count** - the number of columns

### xy-make-grid-columns

> Generator complete collection of styles for a single alias

Parameters:

  * **alias** - the alias of the current layout (breakpoint)
  * **breakpoint** (optional) - device breakpoint
  * **count** - the number of columns

Includes:

  * xy-make-columns-width
  * xy-make-columns-offset
  * xy-make-columns-push
  * xy-make-columns-pull
  * xy-make-columns-align (utilities)
  * xy-make-columns-order (utilities)

## xy-make-row-align

> Alignment for every column in row

Parameters:

  * **alias** - the alias of the current layout (breakpoint)
  * **breakpoint** (optional) - device breakpoint

## xy-make-columns-order

> Flex column reordering

Parameters:

  * **alias** - the alias of the current layout (breakpoint)
  * **breakpoint** (optional) - device breakpoint

## xy-make-columns-align

> Alignment per column

Parameters:

  * **alias** - the alias of the current layout (breakpoint)
  * **breakpoint** (optional) - device breakpoint

## Examples

**Example for Less**

```less
// Container
.container {
  .xy-make-container(30px);
  .xy-make-container-width(768px, 720px);
  .xy-make-container-width(992px, 960px);

  .row {
    .xy-make-row(30px);

    // Utilities (optional)
    .xy-make-row-align(sm, @grid-breakpoint-sm);
    .xy-make-row-align(md, @grid-breakpoint-md);
  }
}

// Column
.col {
  .xy-make-column(30px);
  .xy-make-grid-columns(xs, 12);
  .xy-make-grid-columns(sm, 768px, 12);
  .xy-make-grid-columns(md, 992px, 12);
}
```

More examples for all preprocessors can be seen in the [tests](https://github.com/mrmlnc/xy-flexbox/tree/master/tests) directory.

## License

MIT.
