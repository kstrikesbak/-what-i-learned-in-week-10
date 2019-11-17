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
## `holy-grid-template-areas`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Holy Grid Template Areas</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="./style.css" rel="stylesheet" type="text/css">
  </head>
  <body>
    <div id="app">
      <div id="header"></div>
      <div id="nav"></div>
      <div id="article-1"></div>
      <div id="article-2"></div>
      <div id="ad-area"></div>
      <div id="footer"></div>
    </div>
    <script src="./main.js"></script>
  </body>
</html>
```
```css
#app {
  display: grid;
  height: 1300px;
  width: 2000px;
  
  grid-template-columns: 1.5fr 3fr 3fr 2.5fr;
  grid-template-rows: 2fr 3fr 3fr 2fr;
  
  grid-template-areas:
  "area-1 area-1 area-1 area-1"
  "area-5 area-3 area-3 area-6"
  "area-5 area-4 area-4 area-6"
  "area-2 area-2 area-2 area-2"
  
}

#header, #footer {
  background-color: #9BCE1D;
}

#header {
  grid-area: area-1;
  
}

#footer {
  grid-area: area-2;
}

#main {
  background-color: #F7F5D8
}

#article-1 {
  background-color: lightcoral;
  grid-area: area-3;
}

#article-2 {
  background-color: violet;
  grid-area: area-4;
}

#nav {
  background-color: cornflowerblue;
  grid-area: area-5;
}

#ad-area {
  background-color: cornflowerblue;
  grid-area: area-6;
}
```

## `holy-responsive-grid`
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Media Queries Holy Grail - Grid</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="./style.css" rel="stylesheet" type="text/css">
  </head>
  <body>
    <div id="app">
      <div id="header">HEADER</div>
      <div id="nav">NAV</div>
      <div id="article-1">ARTICLE 1</div>
      <div id="article-2">ARTICLE 2</div>
      <div id="ads">ADS</div>
      <div id="footer">FOOTER</div>
    </div>
  </body>
</html>
```css
* {
  box-sizing: border-box;
}

#app {
  display: grid;
  font-size: 8em;
  text-align: center;
  height: 100vh;
  grid-template-columns: 0.7fr repeat(2,1fr) 0.7fr;
  grid-template-rows: 0.7fr repeat(2,1fr) 0.5fr;
  grid-template-areas: 
  "hea hea hea hea"
  "nav ar1 ar1 ads"
  "nav ar2 ar2 ads"
  "foo foo foo foo"
  ;
}

#header {
  background-color: #f3ca40;
  grid-area: hea;
}

#nav {
  background-color: #4b4e6d;
  grid-area: nav;

}

#article-1 {
  background-color: #6a8d92;
  grid-area: ar1;
}

#article-2 {
  background-color: yellow;
  grid-area: ar2;
}

#ads {
  background-color: #f2a541;
  grid-area: ads;
}

#footer {
  background-color: #f08a4b;
  grid-area: foo;
}

@media (max-width: 800px) {
  #app {
  font-size: 5em;
  grid-template-columns: repeat(4,1fr);
  grid-template-rows: repeat(8,1fr);
  grid-template-areas: 
  "hea hea hea hea"
  "hea hea hea hea"
  "nav nav nav nav"
  "ar1 ar1 ads ads"
  "ar1 ar1 ads ads"
  "ar2 ar2 ads ads"
  "ar2 ar2 ads ads"
  "foo foo foo foo"
  ;
  }
}

@media (max-width: 500px) {
  #app {
  font-size: 3em;
  grid-template-columns: 1;
  grid-template-rows: repeat(10,1fr);
  grid-template-areas: 
  "hea hea hea hea"
  "hea hea hea hea"
  "nav nav nav nav"
  "ar1 ar1 ar1 ar1"
  "ar1 ar1 ar1 ar1"
  "ads ads ads ads"
  "ar2 ar2 ar2 ar2"
  "ar2 ar2 ar2 ar2"
  "foo foo foo foo"
  "foo foo foo foo"
  ;
  }
}
```

## `Japanese Grid Big`

![japanese-grid-help](japanese-grid-help.png)

```html
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
```

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
## `Thingagram`
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Busra Photo Album</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link href="./style.css" rel="stylesheet" type="text/css">
    </head>
    <body>
        <div id="animation">
            <link href="https://fonts.googleapis.com/css?family=Raleway:200,100,400" rel="stylesheet" type="text/css" />
            <h1><strong>Busra Sariguzel</strong> <em>is</em>
            <span
            class="txt-rotate"
            data-period="900"
            data-rotate='[ "C", "O", "D", "E", "CODE." ]'></span>
            </h1>
        </div>
        <div id="app">
            <div id="nav">
                    <ul style="list-style-type:none">
                        <li id="home" class="navbar"><a href="./index.html">Home</a></li>
                        <li id="news" class="navbar"><a href="news.asp">News</a></li>
                        <li id="contact" class="navbar"><a href="contact.asp">Contact</a></li>
                        <li id="about" class="navbar"><a href="./index-1.html">About</a></li>
                    </ul>
            </div>
            <div id="picture-one" class="picture"><img src="./assets/b22.jpeg" alt="picture-one"></div>
            <div id="picture-two" class="picture"><img src="./assets/b21.jpeg" alt="picture-two"></div>
            <div id="picture-three" class="picture"><img src="./assets/b20.jpeg" alt="picture-three"></div>
            <div id="picture-four" class="picture"><img src="./assets/b19.jpeg" alt="picture-four"></div>
            <div id="picture-five" class="picture"><img src="./assets/b18.jpeg" alt="picture-five"></div>
            <div id="picture-six" class="picture"><img src="./assets/b17.jpeg" alt="picture-six"></div>
            <div id="picture-seven" class="picture"><img src="./assets/b16.jpeg" alt="picture-seven"></div>
            <div id="picture-eight" class="picture"><img src="./assets/b8.jpg" alt="picture-eight"></div>
            <div id="picture-nine" class="picture"><img src="./assets/b9.jpg" alt="picture-nine"></div>
            <div id="picture-ten" class="picture"><img src="./assets/b10.jpg" alt="picture-ten"></div>
            <div id="picture-eleven" class="picture"><img src="./assets/b3.jpg" alt="picture-eleven"></div>
            <div id="picture-twelve" class="picture"><img src="./assets/b12.jpg" alt="picture-twelve"></div>
            <div id="picture-thirteen" class="picture"><img src="./assets/b13.jpg" alt="picture-thirteen"></div>
            <div id="picture-fourteen" class="picture"><img src="./assets/b14.jpg" alt="picture-fourteen"></div>
            <div id="picture-fifteen" class="picture"><img src="./assets/b6.jpg" alt="picture-fifteen"></div>
            <div id="footer"><footer><br><p id="p-foot"><strong>Busra</strong> is not just a pretty face. <br> She is a <em>highly skilled</em> <strong>web developer</strong>. <br> Please see her <a href="https://github.com/busrasariguzel/">GITHUB</a> for more details!</p><br></footer></div>
        </div>
        <script src="./play.js"></script>
    </body>
</html>
```
```css
* {
    margin: 0;
    padding: 0;
}
body {
    background-image: url("Delicate.jpg")
}

#animation {
    font-family: 'Raleway', sans-serif;
    padding: 1em 2em;
    font-size: 35px;
    background: #222;
    color: #aaa
}

ul .navbar a
{
    color: black;
    text-decoration: none;
    font-family: 'Roboto Mono', monospace;
}

ul .navbar a:hover
{
    color:silver;
}

h1,h2 {
    font-weight: 200;
    margin: 0.4em 0;
}
h1 { font-size: 3.5em; }
h2 {
    color: #888;
    font-size: 2em;
}

#app {
    display: grid;
    font-size: 8em;
    text-align: center;
    height: 100vh;
    grid-template-columns: repeat(5,1fr);
    grid-template-rows: repeat(5,1fr);
    grid-template-areas:
    "navbar navbar navbar navbar navbar"
    "pic-01 pic-02 pic-03 pic-04 pic-05"
    "pic-06 pic-07 pic-08 pic-09 pic-10"
    "pic-11 pic-12 pic-13 pic-14 pic-15"
    "footie footie footie footie footie"
    ;
}

img {
    height: 100%;
    width: 100%;
}

.picture {
    border: black solid;
}

#header {
    font-family: sans-serif;
}

footer, p {
    font-family: 'Roboto Mono', monospace;
    font-size: 100px;
    color:black;
}

#picture-one {
    /* background-color: lightblue; */
    grid-area: pic-01;
    /* border: salmon; */
}

#picture-two {
    /* background-color: lightblue; */
    grid-area: pic-02;

}

#picture-three {
    /* background-color: #6a8d92; */
    grid-area: pic-03;
}

#picture-four {
    /* background-color: #f3ca40; */
    grid-area: pic-04;
}

#picture-five {
    /* background-color: #4b4e6d; */
    grid-area: pic-05;

}

#picture-six {
    /* background-color: #6a8d92; */
    grid-area: pic-06;
}

#picture-seven {
    /* background-color: #f3ca40; */
    grid-area: pic-07;
}

#picture-eight {
    /* background-color: #4b4e6d; */
    grid-area: pic-08;

}

#picture-nine {
    /* background-color: #6a8d92; */
    grid-area: pic-09;
}
    
#picture-ten {
    /* background-color: yellow; */
    grid-area: pic-10;
}

#picture-eleven {
    /* background-color: #f2a541; */
    grid-area: pic-11;
}

#picture-twelve {
    /* background-color: #4b4e6d; */
    grid-area: pic-12;

}

#picture-thirteen {
    /* background-color: #6a8d92; */
    grid-area: pic-13;
}
    
#picture-fourteen {
    /* background-color: yellow; */
    grid-area: pic-14;
}

#picture-fifteen {
    /* background-color: #f2a541; */
    grid-area: pic-15;
}

#animation {
    grid-area: animat;
}

#header {
    /* background-color:red; */
    grid-area: headie;
}

#footer {
    /* background-color: #f08a4b; */
    grid-area: footie;
}

#nav {
    /* background-color: pink; */
    grid-area: navbar;
    font-size: 1em;
    font-family: Arial, Helvetica, sans-serif;
}

ul {
    display: grid;
    grid-template-areas: 
    'home news cont abou'
    ;
}

#home {
    grid-area: home;
}
#news {
    grid-area: news;
}
#cont {
    grid-area: cont;
}

#about {
    grid-area: abou;
}

@media (max-width: 500px) {

    #animation {
        font-family: 'Raleway', sans-serif;
        padding: 1em 2em;
        font-size: 8px;
        background: #222;
        color: #aaa
    }

    #app {
    grid-template-columns: repeat(3,1fr);
    grid-template-rows: repeat(7,1fr);
    grid-template-areas:
    "navbar navbar navbar"
    "pic-01 pic-02 pic-03"
    "pic-04 pic-05 pic-06"
    "pic-07 pic-08 pic-09"
    "pic-10 pic-11 pic-12"
    "pic-13 pic-14 pic-15"
    "footie footie footie";
    }
    footer, #p-foot{
        font-size: 0.4em;
    }
    #nav ul {
        font-size: 0.2em;
    }
}

@media (max-width: 800px) and (min-width: 600px){

    #animation {
        font-family: 'Raleway', sans-serif;
        padding: 1em 2em;
        font-size: 17px;
        background: #222;
        color: #aaa
    }

    #app {
        font-size: 5em;
        grid-template-columns: repeat(3,1fr);
        grid-template-rows: repeat(7,1fr);
        grid-template-areas:
        "navbar navbar navbar"
        "pic-01 pic-02 pic-03"
        "pic-04 pic-05 pic-06"
        "pic-07 pic-08 pic-09"
        "pic-10 pic-11 pic-12"
        "pic-13 pic-14 pic-15"
        "footie footie footie";
    }
    footer, #p-foot{
        font-size: 0.7em;
    }
    #nav ul {
        font-size: 0.5em;
    }
}
```
```javascript
var TxtRotate = function(el, toRotate, period) {
    this.toRotate = toRotate;
    this.el = el;
    this.loopNum = 0;
    this.period = parseInt(period, 10) || 2000;
    this.txt = '';
    this.tick();
    this.isDeleting = false;
};

TxtRotate.prototype.tick = function() {
    var i = this.loopNum % this.toRotate.length;
    var fullTxt = this.toRotate[i];

    if (this.isDeleting) {
    this.txt = fullTxt.substring(0, this.txt.length - 1);
    } else {
    this.txt = fullTxt.substring(0, this.txt.length + 1);
    }

    this.el.innerHTML = '<span class="wrap">'+this.txt+'</span>';

    var that = this;
    var delta = 300 - Math.random() * 100;

    if (this.isDeleting) { delta /= 2; }

    if (!this.isDeleting && this.txt === fullTxt) {
    delta = this.period;
    this.isDeleting = true;
    } else if (this.isDeleting && this.txt === '') {
    this.isDeleting = false;
    this.loopNum++;
    delta = 500;
    }

    setTimeout(function() {
    that.tick();
    }, delta);
};

window.onload = function() {
    var elements = document.getElementsByClassName('txt-rotate');
    for (var i=0; i<elements.length; i++) {
    var toRotate = elements[i].getAttribute('data-rotate');
    var period = elements[i].getAttribute('data-period');
    if (toRotate) {
        new TxtRotate(elements[i], JSON.parse(toRotate), period);
    }
    }
    // INJECT CSS
    var css = document.createElement("style");
    css.type = "text/css";
    css.innerHTML = ".txt-rotate > .wrap { border-right: 0.08em solid #666 }";
    document.body.appendChild(css);
};
```
