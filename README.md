@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --HEADER-BGCOLOR: #000;
    --HEADER-COLOR: whitesmoke;
}

html {
    font-size: 1.5rem;
    font-family: 'Nunito', sans-serif;
}

body {
    background-color: midnightblue;
    background-image: linear-gradient(to right, midnightblue, rebeccapurple);
    min-height: 100vh;
    display: flex;
    flex-flow: column nowrap;
}

header {
    color: var(--HEADER-COLOR);
    position: sticky;
    top: 0;
    z-index: 1;
}

.header-title-line {
    background-color: var(--HEADER-BGCOLOR);
    padding: 0.25rem 0.5rem;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
}

.menu-button {
    background-color: transparent;
    border: none;
    width: 48px;
    height: 48px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.closeMenuBtn {
    display: none;
    background-color: transparent;
    outline: none;
    /* border: 1px solid red; */
    border: none;
    position: absolute;
    top: 0.25rem;
    right: 0.5rem;
    width: 48px;
    height: 48px;
}

.menu-icon,
.menu-icon::before,
.menu-icon::after {
    background-color: var(--HEADER-COLOR);
    width: 40px;
    height: 5px;
    border-radius: 5px;
    position: absolute;
    transition: all 0.5s;
}

.menu-icon::before,
.menu-icon::after {
    content: "";
}

.menu-icon::before {
    transform: translate(-20px, -12px);
}

.menu-icon::after {
    transform: translate(-20px, 12px);
}

.header-title-line:focus-within .menu-icon {
    background-color: transparent;
    transform: rotate(720deg)
}

.header-title-line:focus-within .menu-icon::before {
    transform: translateX(-20px) rotate(45deg);
}

.header-title-line:focus-within .menu-icon::after {
    transform: translateX(-20px) rotate(-45deg);
}

nav {
    display: none;
    position: relative;
}

header:focus-within nav {
    display: block;
    transform-origin: top center;
    animation: showMenu 0.5s ease-in-out forwards;
}

header:focus-within .closeMenuBtn {
    display: block;
}

header:focus-within .closeMenuBtn:focus {
    transform: translateX(-50px);
}

.closeMenuBtn:focus+nav {
    transform-origin: top center;
    animation: hideMenu 0.5s ease forwards;
}

@keyframes showMenu {
    0% {
        transform: scaleY(0);
    }

    80% {
        transform: scaleY(1.2);
    }

    100% {
        transform: scaleY(1);
    }
}

@keyframes hideMenu {
    0% {
        transform: scaleY(1);
    }

    20% {
        transform: scaleY(1.2);
    }

    100% {
        transform: scaleY(0);
    }
}

nav ul {
    background-color: var(--HEADER-BGCOLOR);
    position: absolute;
    width: 100%;
    top: 0;
    z-index: 1;
    list-style-type: none;
    display: flex;
    flex-flow: column nowrap;
}

nav li {
    padding: 0.5rem;
    border-top: 1px solid var(--HEADER-COLOR);
}

nav a {
    display: block;
    text-align: center;
    width: 80%;
    margin: auto;
}

nav a:any-link {
    color: var(--HEADER-COLOR);
    font-weight: bold;
    text-decoration: none;
}

nav a:hover,
nav a:focus {
    transform: scale(1.2);
    transition: all 0.3s;
}

main {
    flex-grow: 1;
    display: grid;
    place-content: center;
    min-height: 200vh;
}


@media screen and (min-width: 768px) {
    .menu-button {
        display: none;
    }

    nav {
        display: block;
    }

    nav ul {
        flex-flow: row nowrap;
        justify-content: space-evenly;
        border-top: 1px solid var(--HEADER-COLOR);
    }

    nav li {
        border-top: none;
    }

    header:focus-within nav {
        animation: none;
    }
}
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --HEADER-BGCOLOR: #333;
    --HEADER-COLOR: whitesmoke;
}

html {
    font-size: 1.5rem;
    font-family: 'Nunito', sans-serif;
}

body {
    min-height: 100vh;
    display: flex;
    flex-flow: column nowrap;
}

header {
    background-color: var(--HEADER-BGCOLOR);
    color: var(--HEADER-COLOR);
}

.header-title-line {
    padding: 0.25rem 0.5rem;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
}

.menu-button {
    background-color: transparent;
    border: none;
    width: 48px;
    height: 48px;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
}

.menu-icon,
.menu-icon::before,
.menu-icon::after {
    background-color: var(--HEADER-COLOR);
    width: 40px;
    height: 5px;
    border-radius: 5px;
    position: absolute;
    transition: all 0.5s;
}

.menu-icon::before,
.menu-icon::after {
    content: "";
}

.menu-icon::before {
    transform: translate(-20px, -12px);
}

.menu-icon::after {
    transform: translate(-20px, 12px);
}

:is(header:hover, header:focus-within) .menu-icon {
    background-color: transparent;
    transform: rotate(720deg)
}

:is(header:hover, header:focus-within) .menu-icon::before {
    transform: translateX(-20px) rotate(45deg);
}

:is(header:hover, header:focus-within) .menu-icon::after {
    transform: translateX(-20px) rotate(-45deg);
}

:is(header:hover, header:focus-within) nav {
    display: block;
}

nav {
    background-color: var(--HEADER-BGCOLOR);
    display: none;
    transform-origin: top center;
    animation: showMenu 0.5s ease-in-out forwards;
}

@keyframes showMenu {
    0% {
        transform: scaleY(0);
    }

    80% {
        transform: scaleY(1.2);
    }

    100% {
        transform: scaleY(1);
    }
}

nav ul {
    list-style-type: none;
    display: flex;
    flex-flow: column nowrap;
}

nav li {
    padding: 0.5rem;
    border-top: 1px solid var(--HEADER-COLOR);
}

nav a {
    display: block;
    text-align: center;
    width: 80%;
    margin: auto;
}

nav a:any-link {
    color: var(--HEADER-COLOR);
    font-weight: bold;
    text-decoration: none;
}

nav a:hover,
nav a:focus {
    transform: scale(1.2);
    transition: all 0.3s;
}
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 1.5rem;
  font-family: 'Nunito', sans-serif;
}

body {
  min-height: 100vh;
  display: flex;
  flex-flow: column nowrap;
}

main {
  flex-grow: 1;
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

div {
  width: 200px;
  height: 200px;
  border: 1px solid #000;
  display: grid;
  place-content: center;
}

div:first-child {
  background-color: dodgerblue;
  /* transform: translateX(-50%); */
  /* transform: rotateX(180deg); */
  /* transform: scaleX(120%); */
  /* transform: skewX(-10deg); */
}

div:nth-child(2) {
  background-color: yellow;
  /* transform: translateY(-2rem); */
  /* transform: rotateY(180deg); */
  /* transform: scaleY(120%); */
  /* transform: skewY(10deg); */
}

div:last-child {
  background-color: limegreen;
  /* transform: translate(100%, -5rem); */
  /* transform: rotate(78deg); */
  /* transform: scale(50%, 50%); */
  /* transform: skew(-10deg, -10deg); */
}

div:hover {
  background-color: midnightblue;
  /* transition-property: background-color, transform;
  transition-duration: 2s, 3s;
  transition-delay: 0.5s; 
  transition-timing-function: linear;*/
  transition: all 2s 0.5s;
}

div:last-child:hover {
  transform: rotate(180deg);
}

.animate {
  /* animation-name: slide;
  animation-duration: 5s;
  animation-timing-function: ease-in-out;
  animation-delay: 1s;
  animation-iteration-count: 2;
  animation-direction: normal;
  animation-fill-mode: forwards; */
  animation: 5s ease-in-out 1s 2 normal forwards slide;
}

@keyframes slide {
  0% {
    transform: translateX(0);
  }

  33% {
    transform: translateX(300px) rotate(180deg);
  }

  66% {
    transform: translateX(-300px) rotate(-180deg);
  }

  100% {
    transform: translateX(0);
    background-color: rebeccapurple;
  }
}

