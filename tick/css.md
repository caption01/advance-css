#### 0. Reset before start

```
/* reset behavior */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* setup project */
body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: #777;
  padding: 30px;
}

```

#### 1. Shape Element with "Clip-path"

```
background-image: linear-gradient(to right bottom, #7ed56fb7, #28b485c5),
    url("../img/hero.jpg");
  background-size: cover;
  background-position: top;

  /* set origin for logo */
  position: relative;

  clip-path: polygon(0 0, 100% 0, 100% 90%, 0 100%);
```

#### 2. Center every thing with "transfrom/translate 50 50"

```
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
```

#### 3. Build animation with "@keyframe"

```
.heading-primary-main {
  display: block;
  font-size: 60px;
  font-weight: 400;
  letter-spacing: 35px;

  animation-name: moveInLeft;
  animation-duration: 1.5s;
  animation-timing-function: ease-out;

  <!-- shothand version -->
  <!-- animation: moveInRight 1.5s ease-out; -->

}

@keyframes moveInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100px);
  }

  80% {
    opacity: 0.8;
    transform: translateX(10px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}
```
