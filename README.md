# css-battle


```html
<div id="a"></div>
<div class="l"></div>
<div class="l" id="b"></div>
<div class="l" id="c"></div>
  
  <style>
body {
  background: #66284A;
  display: grid;
  justify-content: center;
  align-content: center;
  grid-template-areas: "a"
}
  div {
    background: #F0CD48;
    place-self: center;
  }
#a {
    grid-area: a;
    border-radius: 50%;
    width: 150px;
    height: 150px;
}
.l {
    grid-area: a;
    width: 40px;
    height: 240px;
    border-radius: 20px
  
}
#b {
    transform: rotate(60deg)
}
#c {
    transform: rotate(-60deg)
}
</style>

```
