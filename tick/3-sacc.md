#### Main Sass Feature

- Variable

- Nesting

- Operators

- Partials & import

- Mixins

- Runction

- Extends

- Control directive

#### Scss

```
* {
  margin: 0;
  padding: 0;
}

$color-pri: #f9ed69; //yellow color
$color-sec: #f08a5d; //orange
$color-tert: #b83b5e; //pink
$color-text-dark: #333;
$color-text-light: #eee;

$width-button: 150px;

@mixin clearfix {
   &::after {
    content: '';
    clear: both;
    display: table;
  }
}

@mixin style-link-text($col) {
  text-decoration: none;
  text-transform: uppercase;
  color: $col;
}

@function divided($a, $b) {
  @return $a / $b
}

nav {
  margin: 30px;
  background-color: $color-pri;

  @include clearfix;
}

.navigation {
  list-style: none;
  float: left;

  li {
    display: inline-block;
    margin-left: 30px;

    &:first-child {
      margin: 0;
    }

    a:link {
      @include style-link-text($color-text-dark);
    }
  }
}

.buttons {
  float: right;
}

%btn-placeholder {
  padding: 10px;
  display: inline-block;
  text-align: center;
  border-radius: 100px;
  width: $width-button;

  @include style-link-text($color-text-light);
}

.btn-main {
  &:link {
    @extends %btn-placeholder;
    background-color: $color-sec;
  }

  &:hover {
     background-color: darken($color-sec, 15%);
  }
}

.btn-hot {
  &:link {
    @extends %btn-placeholder;
    background-color: $color-tert;
  }

  &:hover {
     background-color: lighten($color-tert, 15%);
  }
}
```

#### Power Feature Scss

- Variable.

  using @<`varaable-name`> to declare variable.

- @Mixin and @include.

  to build like function that can take args to modify properties.

- %<`btn-placeholder`> to declare.

  sing for create style-pattern and @extends it to element that using (follow DRY. rule).
