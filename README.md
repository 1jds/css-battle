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
