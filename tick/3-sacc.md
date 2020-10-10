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


nav {
  margin: 30px;
  background-color: $color-pri;

    &::after {
    content: '';
    clear: both;
    display: table;
  }
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
      text-decoration: none;
      text-transform: uppercase;
      color: $color-text-dark;
    }
  }
}

.buttons {
  float: right;
}

.btn-main:link, .btn-hot:link {
  padding: 10px;
  display: inline-block;
  text-align: center;
  border-radius: 100px;
  text-decoration: none;
  text-transform: uppercase;
  width: $width-button;
  color: $color-text-light;
}

.btn-main {
  &:link {
     background-color: $color-sec;
  }

  &:hover {
     background-color: darken($color-sec, 15%);
  }
}

.btn-hot {
  &:link {
     background-color: $color-tert;
  }

  &:hover {
     background-color: lighten($color-tert, 15%);
  }
}
```
