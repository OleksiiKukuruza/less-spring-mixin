# less-spring-mixin

less-spring-mixin for emulating spring physics animation

## Usage

```less
.animated-div {
  // You must create your inner mixin
  // with .springPropertiesMixin name
  // which will accept interpolated
  // value (like callback function)
  // mixin creates variable @animationDuration
  // which you should apply to animation
  @name: spring;
  .private {.springPropertiesMixin(@value) {
    transform: translateY(~'@{value}px');
  }}
  .less-spring-mixin(@name; {.private;}; 350; 10; 500; 100; 10);
  animation: @name @animationDuration * 1s linear;
}
```

In this example was emulated spring with following characteristics:

Tension: 350

Friction: 10

Start value: 500

End value: 100

Step: 10 (optional, default value 5)

## Result

```css
.animated-div {
  animation: spring 0.92s linear;
}
@keyframes spring {
  0% {
    transform: translateY(479.60033078px);
  }
  10% {
    transform: translateY(-1.3222199366652414px);
  }
  20% {
    transform: translateY(126.90181092834634px);
  }
  30% {
    transform: translateY(92.89623955782021px);
  }
  40% {
    transform: translateY(101.86520863048564px);
  }
  50% {
    transform: translateY(99.53494922874434px);
  }
  60% {
    transform: translateY(100.12396958484638px);
  }
  70% {
    transform: translateY(99.9671289060412px);
  }
  80% {
    transform: translateY(100.0086680590807px);
  }
  90% {
    transform: translateY(99.9977273485739px);
  }
  100% {
    transform: translateY(100.00059225225972px);
  }
}
```

### License

MIT