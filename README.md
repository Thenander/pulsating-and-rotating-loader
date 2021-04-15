# Pulsating and rotating loader

This loader is dependent of the root font size (rem).  
If `1rem` is equal to `16px` the loader is `64px` x `64px` (ie the default in most browsers.)

## Usage

Copy and paste the following snippet in your **HTML** markup:

```
<div class="pulsating-and-rotating-loader">
  <div>
    <div></div>
  </div>
</div>
```

Copy and paste the following code-block in your **CSS** file:

```
.pulsating-and-rotating-loader {
  height: 3.75;
  width: 3.75;
}
.pulsating-and-rotating-loader div {
  box-sizing: border-box;
  padding: 0.4em;
  width: 100%;
  height: 100%;
  border: 0.2em solid #000;
  border-radius: 100vw;
  animation-name: puls;
  animation-timing-function: cubic-bezier(0, 0.5, 1, 1);
  animation-duration: 1s;
  animation-iteration-count: infinite;
  transform: scale(0);
  opacity: 1;
}
.pulsating-and-rotating-loader div div {
  border-radius: 100vw;
  border-top: 0.2em solid #000;
  border-right: 0.2em solid transparent;
  border-bottom: 0.2em solid transparent;
  border-left: 0;
  animation-timing-function: linear;
  animation-name: spin;
  animation-duration: 0.4s;
  animation-iteration-count: infinite;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes puls {
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 0;
  }
}
```

### Even easier if you use Sass!

Copy and paste the following code-block in your **SCSS** file:

```
$border: 0.2em solid #000;

.pulsating-and-rotating-loader {
  height: 3.75em;
  width: 3.75em;
  div {
    box-sizing: border-box;
    padding: 0.4em;
    width: 100%;
    height: 100%;
    border: $border;
    border-radius: 100vw;
    animation-name: puls;
    animation-timing-function: cubic-bezier(0, 0.5, 1, 1);
    animation-duration: 1s;
    animation-iteration-count: infinite;
    transform: scale(0);
    opacity: 1;
    div {
      border-radius: 100vw;
      border-top: $border;
      border-right: 0.2em solid transparent;
      border-bottom: 0.2em solid transparent;
      border-left: 0;
      animation-timing-function: linear;
      animation-name: spin;
      animation-duration: 0.4s;
      animation-iteration-count: infinite;
    }
  }
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes puls {
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 0;
  }
}
```

[Online DEMO](https://microlab.se/pulsating-and-rotating-loader)
