#### Building Thinking

#### 1. re-usable code

    - create utils class to re-usable code in another part

     for exam: .u-margin-bottom-8 (set margin bottom 8rem) or .u-text-align (set text center)

#### 2. text color gradient with "bg-color & -webket"

```
background-image: linear-gradient(
    to right,
    $color-primary-light,
    $color-primary-dark
  );
  -webkit-background-clip: text;
  color: transparent;
  letter-spacing: 0.2rem;
  transition: all 0.2s;
```

### 3. composition image

```
.composition {
  position: relative;

  &__photo {
    width: 55%;
    box-shadow: 0 1.5rem 4rem rgba($color-black, 0.4);
    border-radius: 2px;
    position: absolute;
    z-index: 10;
    transition: all 0.2s;
    outline-offset: 2rem;

    &--p1 {
      left: 0;
      top: -2rem;
    }

    &--p2 {
      right: 0;
      top: 2rem;
    }

    &--p3 {
      left: 20%;
      top: 10rem;
    }

    &:hover {
      outline: 1.5rem solid $color-primary;
      transform: scale(1.05) translateY(-0.5rem);
      box-shadow: 0 2.5rem 4rem rgba($color-black, 0.5);
      z-index: 20;
    }
  }

  <!-- to select non-hovered images in composition div -->
  &:hover &__photo:not(:hover) {
    transform: scale(0.9);
  }
}
```
