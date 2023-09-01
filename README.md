# Repo For Some of my Solutions to CSS Battle Challenges and Notes on These

## Daily Target for 01/09/2023

In order to complete this challenge, it would, of course, be possible to use absolute positioning. However, it's more pleasing to use CSS Grid to both center within the container (here the `body`) and overlap the grid children. The children are able to be overlapped by assigning them to the same grid area. The `place-self: center` centers every child within grid-area 'a'.

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
