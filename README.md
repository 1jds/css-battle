# Repo For Some of my Solutions to CSS Battle Challenges and Notes on These

## Daily Target for 01/09/2023

In order to complete this challenge, it would, of course, be possible to use absolute positioning. However, it's more pleasing to use CSS Grid to both center within the container (here the `body`) and overlap the grid children. The children are able to be overlapped by assigning them to the same grid area. The `place-self: center` centers every child within grid-area 'a'.

Points of note: 
- assigning two elements to the same grid area overlaps them. This is explained further by Kevin Powell [in this video](https://youtube.com/shorts/ncPwkE10BOY?si=JS22WK8FBvLfHafo).
- using `display: grid; place-content: center;` is an easy way to center content.
- Of course, one could also use `display: flex; justify-content: center; align-items: center;`.

<img alt="screenshot of daily target image" src="https://github.com/1jds/css-battle/blob/main/screenshot-of-daily-target-for-2023-09-01.png">

  ```html
  <div id="a"></div>
  <div class="l"></div>
  <div class="l b"></div>
  <div class="l c"></div>
    
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
        grid-area: a;
      }
    #a {
        border-radius: 50%;
        width: 150px;
        height: 150px;
    }
    .l {
        width: 40px;
        height: 240px;
        border-radius: 20px  
    }
    .b {
        transform: rotate(60deg)
    }
    .c {
        transform: rotate(-60deg)
    }
</style>
  
  ```

## Challenge No. 121. Duck Hunt

This challenge can be solved using a combination of `linear-gradient`, `box-shadow`, and absolute positioning. The background of course, could be made with flexbox, or grid, or just block-level components. But the linear-gradient solution saves characters. Also, ordering the `<div>` elements in the HTML as they are removes the need to use `z-index` to layer the tree trunk under the leaves. An 'optimised' (but unreadable) version of the same which saves characters is added below.

<img alt="screenshot of my css battle number 121 answer" src="https://github.com/1jds/css-battle/blob/main/illustrative-screenshot-of-css-battle-121-duck-hunt.png">

Normal: 
```html
<div id="tree"></div>
<div id="foliage"></div>
<style>
  body {
    background: linear-gradient(#1E92FF, #1E92FF 60%, #69D10A 60%, #69D10A 73.3%, #6F6100 73.3%);
  }
  #foliage {
    position: absolute;
    left: 40;
    top: 60;
    width: 40px;
    height: 40px;
    background: #69D10A;
    border-radius: 50%;
    color: #69D10A;
    box-shadow: 20px 20px, -20px 20px, 0px 20px, 270px 70px, 270px 90px;
  }
  #tree {
    position: absolute;
    left: 50px;
    top: 80px;
    background: #441A0A;
    height: 100px;
    width: 20px;
  }
</style>
```

'Character optimised`:
```html
<div id="t"></div><div id="f"><style>body{background:linear-gradient(#1E92FF, #1E92FF 60%, #69D10A 60%, #69D10A 73.3%, #6F6100 73.3%)}#f{position:absolute;left:40;top:60;width:40;height:40;background: #69D10A;border-radius:50%;color:#69D10A;box-shadow:20px 20px, -20px 20px, 0px 20px, 270px 70px, 270px 90px}#t{position:absolute;left:50;top:80;background:#441A0A;height:100;width:20}
```

## Daily Target for 9/9/2023

This challenge provides an obvious use for CSS grid. It also provides an example of how color declarations should mostly be abstracted to utility classes or CSS custom properties.

<img alt="illustrative screenshot of daily target for 9/9/2023" src="https://github.com/1jds/css-battle/blob/main/illustrative-screenshot-of-daily-target-for-2023-09-10.png">

```html
<div class="a o"></div>
<div id=b></div>
<div class="c o"></div>
<div class="d o"></div>
<style>
  body {
    background: #E6D9AC;
    padding-top: 52px;
    padding-left: 117px;
    display: grid;
    grid-template-columns: 30px 91px 30px;
    grid-template-rows: repeat(6, 30px);
  }
  .o {
    background: #BD6C27;
  }
  .a {
    grid-area: 1 / 1 / 6 / 3;
  }
  #b {
    grid-area: 2 / 2 / 7 / 4;
    background: #8F2D2B;
  }
  .c {
    grid-area: 3 / 2 / 4 / 3;
  }
  .d {
    grid-area: 5 / 2 / 6 / 3;
  }
</style>
```

## Daily Target for 11/9/2023

This is an interesting example of abstraction - where the border `color` is abstracted into a class with just the `color` property, which allows the `border-left`, etc. properties to be reused in utility classes. The `width` and `height` are also being reused in utility classes, but that is more straightforward. Also worthwhile mentioning is that one can save characters by making the grid on the `body` take up the whole space, rather than using padding to center, or using a grid to center a `div` and then work within that container with its own internal grid, or some other method using flexbox or other. I wonder whether CSS sin/cos/etc. trigonometry could be used here to make shapes around a central point?

```css
<div class="item-b width-height purple left-border top-border"></div>
<div class="item-c width-height purple right-border bottom-border"></div>
<div class="item-a width-height violet right-border top-border"></div>
<div class="item-d width-height violet left-border bottom-border"></div>

<style>
  body {
    margin: 0;
    background: #B5D1FB;
    display: grid;
    grid-template: 75px 75px 75px 75px / 185px 30px 185px;
  }
  .width-height {
    width: 185px;
    height: 45px;
  }
  .right-border {
    border-right: 30px solid;
  }  
  .left-border {
     border-left: 30px solid;
   }
   .violet {
     color: #230259;
   }
   .purple {
     color: #8819F6;
   }
   .top-border {
     border-top: 30px solid;
   }
   .bottom-border {
     border-bottom: 30px solid;
   }
   .item-a {
    grid-area: 2 / 1 / 3 / 2;
    border-radius: 0 750px 0 0;
  }
  .item-c {
    grid-area: 3 / 1 / 4 / 2;
    border-radius: 0 0 750px 0;
  }
  .item-b {
    grid-area: 2 / 2 / 3 / 3;
    border-radius: 750px 0 0 0;
  }
  .item-d {
    grid-area: 3 / 2 / 4 / 3;
    border-radius: 0 0 0 750px;
  } 
</style>
```
