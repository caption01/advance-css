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

#### 4. polygon shape with "transform skey()"

```
.section-feature {
  padding: 20rem 0;
  background-image: linear-gradient(
      to right bottom,
      rgba($color-primary-light, 0.8),
      rgba($color-primary-dark, 0.8)
    ),
    url("../img/nat-4.jpg");
  background-size: cover;
  transform: skewY(-7deg);
  margin-top: -10rem;

  <!-- select direct child -->
  & > * {
    transform: skewY(7deg);
  }

  <!-- exiting way -->
  // clip-path: polygon();
}

```

#### 5. card 2 side with "rotateY"

- perspective : handle effect error;
- backface-visibility: to hide back side of element (think is front/back side he hide back side to render)
- set back side initial rotateY at 180deg.

```
.card {
  perspective: 150rem;
  -moz-perspective: 150rem;
  height: 50rem;
  position: relative;

  &__side {
    color: white;
    font-size: 2rem;
    height: 50rem;
    transition: all 1s ease;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;

    // handle back part element
    backface-visibility: hidden;

    &--front {
      background-color: $color-white;
    }

    &--back {
      transform: rotateY(180deg);
      border-radius: 3px;
      box-shadow: 0 1.5rem 4rem rgba($color-black, 0.15);

      &-1 {
        background-image: linear-gradient(
          to right bottom,
          $color-secondary-light,
          $color-secondary-dark
        );
      }
    }
  }

  &:hover &__side--front {
    transform: rotateY(180deg);
  }

  &:hover &__side--back {
    transform: rotateY(0);
  }
}

```

#### 6. front-card picture filter with "backgrund-blend-mode"

```
background-size: cover;
height: 23rem;

<!-- decorate color over on image -->
background-blend-mode: screen;
clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%);
-webkit-clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%); }

.card__picture--1 {
  <!-- set color on image -->
  background-image: linear-gradient(to right bottom, #ffb900, #ff7730), url(../img/nat-5.jpg);
}
```

#### 7. front-card clone element props with "box-decoration-break: clone"

```
 &__heading {
    font-size: 2.8rem;
    font-weight: 300;
    text-transform: uppercase;
    color: $color-white;
    position: absolute;
    text-align: right;
    top: 12rem;
    right: 2rem;
    width: 75%;

    &-span {
      padding: 1rem 1.5rem;
      box-decoration-break: clone;
      -webkit-box-decoration-break: clone;

      &--1 {
        background-image: linear-gradient(
          to right bottom,
          rgba($color-secondary-light, 0.85),
          rgba($color-secondary-dark, 0.85)
        );
      }
    }
  }

```

#### 8. Create circle around content with "figure"

- figure and figcaption using for create element.

```
HTML:tag

<figure class="story__shape">
  <img src="img/nat-9.jpg" alt="tour" class="story__img">
  <figcaption class="story__caption">JACK WILSON</figcaption>
</figure>

CSS:

&__shape {
  width: 15rem;
  height: 15rem;
  background-color: orange;
  float: left;
  position: relative;

  <!-- to defined content around this el. shape props must using with float -->
  shape-outside: circle(50% at 50% 50%);
  -webkit-shape-outside: circle(50% at 50% 50%);

  <!-- to defined el. looklike -->
  clip-path: circle(50% at 50% 50%);
  -webkit-clip-path: circle(50% at 50% 50%);

  transform: translateX(-3rem) skewX(12deg);
}

&__img {
  height: 100%;
  transform: translateX(-4rem) scale(1.2);
  backface-visibility: hidden;
  transition: all 0.5s;
}

&__caption {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, 20%);
  color: $color-white;
  text-transform: uppercase;
  font-size: 1.7rem;
  text-align: center;
  opacity: 0;
  transition: all 0.5s;
  backface-visibility: hidden;
}

&:hover &__caption {
  opacity: 1;
  transform: translate(-50%, -50%);
}

&:hover &__img {
  transform: translateX(-4rem) scale(1);
  filter: blur(3px) brightness(80%);
}
```

#### 9. Bg-Linear tick for build poly shape

```
 background-image: linear-gradient(
      105deg, //control gradient deg.
      rgba($color-white, 0.9) 0%, // we can set multi color shade  (color) (position),
      rgba($color-white, 0.9) 50%,
      transparent 50%
    ),
    url(../img/nat-10.jpg);
```

#### 10. label slice down

- using json siblink selector (+ is menat after input el.) to help css select label element

```
&__input:placeholder-shown + &__label {
    opacity: 0;
    visibility: hidden;
    transform: translateY(-4rem);
  }

```

#### 11. navigation button tick with "checkout & label"

```
&__checkbox {
    display: none;
  }

  &__button {
    background-color: $color-white;
    height: 7rem;
    width: 7rem;
    position: fixed;
    top: 6rem;
    right: 6rem;
    border-radius: 50%;
    z-index: 2000;
  }

  &__background {
    height: 6rem;
    width: 6rem;
    border-radius: 50%;
    position: fixed;
    top: 6.5rem;
    right: 6.5rem;

    <!-- radius gradient -->
    background-image: radial-gradient(
      $color-primary-light,
      $color-primary-dark
    );
    z-index: 1000;

    transform: scale(50);
  }

  &__nav {
    height: 100vh;
    width: 100%;
    position: fixed;
    top: 0;
    right: 0;
    z-index: 1500;
  }
```

#### 12. item animation slice with "bg-size & bg-position"

```
&__link {
    &:link,
    &:visited {

      <!-- display must be inline block to animate translateX -->
      display: inline-block;

      font-size: 3rem;
      font-weight: 300;
      opacity: 0.8;
      padding: 1rem 2rem;
      color: $color-white;
      text-decoration: none;
      text-transform: uppercase;
      background-image: linear-gradient(
        120deg,
        transparent 0%,
        transparent 50%,
        $color-white 50%
      );

      <!-- to shift color white hidden to right side -->
      background-size: 220%;
      transition: all 0.4s;

      span {
        margin-right: 1.5rem;
        display: inline-block;
      }
    }

    &:hover,
    &:active {
      <!-- moving back white side by moving position -->
      background-position: 100%;
      color: $color-primary;
      transform: translateX(1rem);
    }
  }
```

#### 13. humberger nav-button with "::befre & ::after"

```
&__icon {
    position: relative;
    margin-top: 3.5rem;

    &,
    &::before,
    &::after {
      width: 3rem;
      height: 2px;
      background-color: $color-grey-dark-3;
      display: inline-block;
    }

    <!-- if we move "content" into upper block we cant using text-aline props watch lec. 51 on start clip-->
    &::before,
    &::after {
      content: "";
      position: absolute;
      left: 0;
      transition: all 0.2s;
    }

    &::before {
      top: -0.8rem;
    }

    &::after {
      top: 0.8rem;
    }
  }

  &__button:hover &__icon::before {
    top: -1rem;
  }

  &__button:hover &__icon::after {
    top: 1rem;
  }

  &__checkbox:checked + &__button &__icon {
    background-color: transparent;
  }

  &__checkbox:checked + &__button &__icon::before {
    top: 0;
    transform: rotate(135deg);
  }

  &__checkbox:checked + &__button &__icon::after {
    top: 0;
    transform: rotate(-135deg);
  }

```
