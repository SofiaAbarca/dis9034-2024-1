# clase-05

El proyecto lo hice a base de la tarea de la clase 03 <https://editor.p5js.org/Mossgan/sketches/aXxPivtQI> donde quiero que que la imagen rote y se mueva interactuando con el mouse, además, una interacción que al momento de hacer click se aplique en la imagen un filtro negativo

Voy a definir como condicional fotito para subir mas adelante el jpg

```js
let fotito;

//Defino la imagen wiwi.jpg para cargarla en el proyecto
function preload() {
  fotito = loadImage('wiwi.jpg');
}

function setup() {
  createCanvas(windowWidth, windowHeight);
}
```

Hago el fondo de color blanco

```js
function draw() {
background(255, 255, 255);
```

Aquí hice que cuando se haga click el fondo se vuelva negro

```js
if (mouseIsPressed === true) {
  background(0, 0, 0);
}
```

Defino la interacción del mouse donde si se hace click se aplique un filtro negativo en fotito <https://p5js.org/reference/#/p5.Image/filter>

```js
if (mouseIsPressed === true) {
  fotito.filter(INVERT);
}
```

loop para colocar las elipses de forma aleatoria

```js
for (let i = 0; i < 50; i++) {
```

Le agregue elipses que se generan de forma aleaotria. <https://editor.p5js.org/23younkerb/sketches/V_lYT1KkO>

```js
fill(random(0), random(0), random(0), random(0));
ellipse(random(windowWidth), random(windowHeight), random(25));
frameRate(5);
}
```

Utilizó push y pop para mantener el control de la acción específica que es que rote la imagen <https://p5js.org/es/reference/#/p5/push>

```js
push();
```

Además hice una constante para que rote cada 10 milisegundos en el axis Z <https://p5js.org/es/reference/#/p5/rotateZ>

```js
rotate(millis() / 10);
```

Definí la posición de la imagen en el centro como punto inicial y de ahí reacciona la rotación <https://p5js.org/es/reference/#/p5/imageMode>

```js
imageMode(CORNER);
```

La interaccion de la imagen con el mouse hace que se aleje segun donde esta el cursor, es decir, si el cursor se encuentra en el centro la imagen se aleja del centro y viceversa <https://openprocessing.org/sketch/105403/>

```js
image(fotito, mouseX, mouseY, -500, 200);
pop();
```

<https://editor.p5js.org/Mossgan/full/WJnYeZBDY> Pantalla completa
<https://editor.p5js.org/Mossgan/sketches/WJnYeZBDY> Editor
