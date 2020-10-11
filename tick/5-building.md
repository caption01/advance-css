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
