# **WHAT I LEARNED IN  WEEK 10** 
___

    Can't believe it's Week 10. 
    Tell JK I'm still Rowling. - Kejal

## `CodeWars`

### string ends with?
```javascript 
function solution(str, ending){
  return str.endsWith(ending);
}
```

### Convert the score
```javascript
function scoreboard(str) {
  let words = "nilonetwothreefourfivesixseveneightnine"
  let newArr = []
  arr = str.split(' ')
  for (i = 0 ; i < arr.length ; i++) {
    if (words.includes(arr[i])) {
      if (arr[i] === 'nil') {
        newArr.push(0)
      }
      if (arr[i] === 'one') {
        newArr.push(1)
      }
      if (arr[i] === 'two') {
        newArr.push(2)
      }
      if (arr[i] === 'three') {
        newArr.push(3)
      }
      if (arr[i] === 'four') {
        newArr.push(4)
      }
      if (arr[i] === 'five') {
        newArr.push(5)
      }
      if (arr[i] === 'six') {
        newArr.push(6)
      }
      if (arr[i] === 'seven') {
        newArr.push(7)
      }
      if (arr[i] === 'eight') {
        newArr.push(8)
      }
      if (arr[i] === 'nine') {
        newArr.push(9)
      }
    }
  }
  return newArr
}
```
### Well of Ideas - Harder Version
```javascript
function well(arr){
  let count = 0
  let goal = 'good'
  for (let i = 0 ; i < arr.length ; i++) {
    for (let j = 0 ; j < arr[i].length ; j++) {
    let mission = arr[i][j].toString().toLowerCase()
    if (mission.includes(goal)) {
      count++
    }

    }
    }
    
  if (count === 0){
    return "Fail!"
  }
  
  if (count < 3) {
    return "Publish!"
  }
  if (count >= 3) {
    return "I smell a series!"
  }
}
```

### Player Contact Manager
```javascript
function playerManager(players) {
  // your code

  if (players===null||players.length===0) {
    return []
  }
  let newArr = []
  let playersInArray = players.split(', ')
  for (i = 0 ; i < playersInArray.length ; i+=2) {
    newArr.push({'player':playersInArray[i], 'contact':playersInArray[i+1]*1})
  }
  return newArr
}
```

### Abbreviate a Two Word Name
```javascript
function abbrevName(name) {
  name = name.toUpperCase()
  let newStr = ''
  for (let i = 0 ; i < name.length ; i++) {
    if (i===0) {
      newStr += name[i] + '.'
    } else if (name[i] === ' '){
      newStr += name[i+1]
    }
  }
  return newStr
}
```



## `Japanese Grid Big`

![image](japanese-grid-help.png)

<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Project for Colin</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link href="./style.css" rel="stylesheet" type="text/css">
    </head>
    <body>
        <div id="app">
            <div id="bamboo-big"><img src="./assets/bamboo-big.png"></div>
            <div id="bamboo"><img src="./assets/bamboo.png"></div>
            <div id="cell-tower"><img src="./assets/cell-tower.png"></div>
            <div id="dolls-rectangle"><img src="./assets/dolls-rectangle.png"></div>
            <div id="dolls-square"><img src="./assets/dolls-square.png"></div>
            <div id="fish-flag-wide"><img src="./assets/fish-flag-wide.png"></div>
            <div id="fish-flag"><img src="./assets/fish-flag.png" id='fish-flag'></div>
            <div id="flag-rectangle"><img src="./assets/flag-rectangle.png" id='flag-rectangle'></div>
            <div id="flag-square"><img src="./assets/flag-square.png" id='flag-square'></div>
            <div id="gate-wide"><img src="./assets/gate-wide.png"></div>
            <div id="gate"><img src="./assets/gate.png" id='gate'></div>
            <div id="horn-horizontal"><img src="./assets/horn-horizontal.png" id='horn-horizontal'></div>
            <div id="horn-vertical"><img src="./assets/horn-vertical.png" id='horn-vertical'></div>
            <div id="kimono-1"><img src="./assets/kimono-1.png" id='kimono-1'></div>
            <div id="kimono-2"><img src="./assets/kimono-2.png" id='kimono-2'></div>
            <div id="lantern-short"><img src="./assets/lantern-short.png" id='lantern-short'></div>
            <div id="lantern-tall"><img src="./assets/lantern-tall.png" id='lantern-tall'></div>
            <div id="lanterns-three"><img src="./assets/lanterns-three.png" id='lanterns-three'></div>
            <div id="map-wide"><img src="./assets/map-wide.png" id='map-wide'></div>
            <div id="map"><img src="./assets/map.png" id='map'></div>
            <div id="masks-wide"><img src="./assets/masks-wide.png" id='masks-wide'></div>
            <div id="masks"><img src="./assets/masks.png" id='masks'></div>
            <div id="monster-wide"><img src="./assets/monster-wide.png" id='monster-wide'></div>
            <div id="monster"><img src="./assets/monster.png" id='monster'></div>
            <div id="pagoda-big"><img src="./assets/pagoda-big.png" id='pagoda-big'></div>
            <div id="pagoda"><img src="./assets/pagoda.png" id='pagoda'></div>
            <div id="painting"><img src="./assets/painting.png" id='painting'></div>
            <div id="quadropi-five"><img src="./assets/quadropi-five.png" id='quadropi-five'></div>
            <div id="quadropus"><img src="./assets/quadropus.png" id='quadropus'></div>
            <div id="sake-wide"><img src="./assets/sake-wide.png" id='sake-wide'></div>
            <div id="sake"><img src="./assets/sake.png" id='sake'></div>
            <div id="sunrise-horizontal"><img src="./assets/sunrise-horizontal.png" id='sunrise-horizontal'></div>
            <div id="sushi-extra-wide"><img src="./assets/sushi-extra-wide.png" id='sushi-extra-wide'></div>
            <div id="sunrise-vertical"><img src="./assets/sunrise-vertical.png" id='sunrise-vertical'></div>
            <div id="sushi-wide"><img src="./assets/sushi-wide.png" id='sushi-wide'></div>
            <div id="sushi"><img src="./assets/sushi.png" id='sushi'></div>
            <div id="vase-horizontal"><img src="./assets/vase-horizontal.png" id='vase-horizontal'></div>
            <div id="vase-vertical-short"><img src="./assets/vase-vertical-short.png" id='vase-vertical-short'></div>
            <div id="vase-vertical-tall"><img src="./assets/vase-vertical-tall.png" id='vase-vertical-tall'></div>
            <div id="volcano"><img src="./assets/volcano.png" id='volcano'></div>
            <div id="wave-horizontal"><img src="./assets/wave-horizontal.png" id='wave-horizontal'></div>
            <div id="wave-vertical"><img src="./assets/wave-vertical.png" id='wave-vertical'></div>
            <div id="writing-horizontal"><img src="./assets/writing-horizontal.png" id='writing-horizontal'></div>
            <div id="writing-vertical"><img src="./assets/writing-vertical.png" id='writing-vertical'></div>
    </div>
    </body>
</html>

```css
#app {
    display: grid;
    grid-template-columns: repeat(18, 1fr);
    grid-template-rows: repeat(11, 1fr);
    width: 75%;
}
img {
    height: 100%;
    width: 100%;
}

#bamboo-big{
    grid-column: 2 / 5;
    grid-row: 3 / 5;
}
#bamboo{
    grid-column: 13 / 15 ;
    grid-row: 11 / 12 ;
}
#cell-tower {
    grid-column: 11 / 15;
    grid-row: 9/11;
}
#dolls-rectangle {
    grid-column: 1 / 5 ;
    grid-row: 8 / 9;
}
#dolls-square {
    grid-column: 13 / 15;
    grid-row: 1 / 3;
}
#fish-flag-wide {
    grid-column: 5/9;
    grid-row: 11/12;
}
#fish-flag {
    grid-column: 1 / 4;
    grid-row: 1 / 2;
}
#flag-rectangle {
    grid-column: 3 / 5;
    grid-row: 6 / 8;
}
#flag-square {
    grid-column: 7 / 9;
    grid-row: 1 / 3;
}
#gate {
    grid-column: 1 / 4;
    grid-row: 9 / 11;
}
#gate-wide {
    grid-column: 15 /19;
    grid-row: 5 / 7;
}
#horn-horizontal {
    grid-column: 11/13;
    grid-row: 2 / 3;
}
#horn-vertical {
    grid-column: 9 / 11;
    grid-row: 9 / 12;
}
#kimono-1{
    grid-column: 5/9;
    grid-row: 9/11;
}
#kimono-2{
    grid-column: 15 / 19;
    grid-row: 1/3;
}
#lantern-short{
    grid-column: 5 / 7;
    grid-row: 1 / 3;
}
#lantern-tall{
    grid-column: 17 / 19;
    grid-row: 7 / 10;
}
#lanterns-three{
    grid-column: 9 / 15;
    grid-row: 3 / 5;
}
#map-wide{
    grid-column: 15 / 19;
    grid-row: 4 / 5;
}
#map{
    grid-column: 1 / 4;
    grid-row: 2 / 3;
}
#masks-wide{
    grid-column: 5 / 9;
    grid-row: 4 / 6;
}
#masks{
    grid-column: 5 /7;
    grid-row: 7/9;
}
#monster-wide{
    grid-column: 9/13;
    grid-row: 1 /2;
}
#monster{
    grid-column: 1 /  3;
    grid-row: 6 / 8;
}
#pagoda-big{
    grid-column: 9 / 13;
    grid-row: 6 / 8;
}
#pagoda{
    grid-column: 11 / 13 ;
    grid-row: 11 / 13;
}
#painting{
    grid-column: 5/9;
    grid-row: 3/4;
}
#quadropi-five{
    grid-column: 9 / 15;
    grid-row: 8 / 9;
}
#quadropus{
    grid-column: 2/5;
    grid-row: 5/6;
}
#sake-wide{
    grid-column: 15 / 19;
    grid-row: 10 / 11;
}
#sake{
    grid-column: 9 / 11;
    grid-row: 5 / 6;
}
#sunrise-horizontal{
    grid-column: 17 / 19;
    grid-row: 3 / 4;
}
#sushi-extra-wide{
    grid-column: 5 / 9;
    grid-row: 6 / 7;
}
#sunrise-vertical{
    grid-column: 4 / 5;
    grid-row: 9 / 12;
}
#sushi-wide{
    grid-column: 1 / 4;
    grid-row: 11/ 12;
}
#sushi{
    grid-column: 11 / 13;
    grid-row: 5 / 6;
}
#vase-horizontal{
    grid-column: 9 / 11;
    grid-row: 2 / 3;
}
#vase-vertical-short{
    grid-column: 4 / 5;
    grid-row: 1 / 3;
}
#vase-vertical-tall{
    grid-column: 1 / 2;
    grid-row: 3 / 6;
}
#volcano{
    grid-column: 15 / 19;
    grid-row: 11 / 12;
}
#wave-horizontal{
    grid-column: 7 / 9;
    grid-row: 7 / 9;
}
#wave-vertical{
    grid-column: 13 / 15;
    grid-row: 5 / 8;
}
#writing-horizontal {
    grid-column: 15 / 17;
    grid-row: 3 / 4;
}
#writing-vertical{
    grid-column: 15 / 17;
    grid-row: 7 / 10;
}
```

