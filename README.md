Columns
=======

Responsive column scss template, supports up to 10 columns (modifyable). It supports non CSS3-browser but needs extra classes in that case, see column classes below

Options
-------

### SASS Options/functions
* $column_margin
  * _Sets the default margin to use around columns_
* @include make_columns($column_class, $nr_of_columns, $insert_clear: true, $margin: $column_margin)
  * _core function that generates the css_
  * _can be used independently to create rows and columns from custom classes or with separate margin and so on_

### Row classes:
* .row
  * _Defines the row element to hold columns_
* .count-(int)
  * _Defines amount of columns per row (it is possible to create multiple rows inside only one .row element, to support <IE9 you need to set first-in-row and last-in-row_
* .no-break
  * _Will not apply media queries and keep columns in a single row no matter what_
* .no-margin
  * _will overide the $useMargin variable and remove all margins_

### Row options
* data-min-cols="{1 * number of columns}"
  * _This option can disable breaking if less than specified. Defined by adding a 1 per column number. So if row has data-min-cols="111", the row wont break into less than 3 columns in row._
* data-flex="{bool}"
  * _Defines if row should use flexbox properties_

### Column classes:
* .column
  * _Defines the column element inside a row_
* .first-in-row
  * _Defines a column to be first in row, if you use a single row element with more columns than specified, you can use this class to set a new row. (clears left and left margin)_
* .last-in-row
  * _Defines a column to be last in row (clears right and right margin)_
* .colspan-(int)
  * _Defines a column to span over multiple columns_

Usage:
------

```html
<div class="row count-4 no-break no-margin">
  <div class="column first-in-row"></div>
  <div class="column colspan-2"></div>
  <div class="column last-in-row"></div>
</div>
```
