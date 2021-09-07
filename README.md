## ✨ || Instalacion

Para instalar el paquete zJuqn necesitas:

- Necesitas instalar [**Node.js**](https://nodejs.org/en/download/).

- Necesitas instalar [**discord.js**](https://npmjs.com/package/discord.js).

Luego puede abrir el terminal de su app y escribir:

```
$ npm install zjuqn
```

## 📜 || Tabla de contenidos

### Funciones:


-  [`Passwords()`](https://github.com/zJuqn/zJuqnNPM-Docs#passwordsGen) - Funcion para crear contraseñas con la cantidad de caracteres que elijas

-  [`WelcomeImage()`](https://github.com/zJuqn/zJuqnNPM-Docs#welcomeImage) - Funcion para crear una imagen con canvas

-  [`Wikipedia()`](https://github.com/zJuqn/zJuqnNPM-Docs#wikipedia) - Funcion para buscar preguntas en wikipedia

-  [`npmData()`](https://github.com/zJuqn/zJuqnNPM-Docs#npmdata) - Funcion para obtener datos de un npm

-  [`boostCard()`](https://github.com/zJuqn/zJuqnNPM-Docs#boostcard) - Funcion crear una boostCard

-  [`ship()`](https://github.com/zJuqn/zJuqnNPM-Docs#ship) - Simula un ship/amor


### Funciones de imagenes:

| Funcion       |             Descripcion                                    |
|---------------|------------------------------------------------------------|
| [blur](https://github.com/zJuqn/zJuqnNPM-Docs#blur)          | Coloca tu avatar borroso                                   |
| [circle](https://github.com/zJuqn/zJuqnNPM-Docs#circle)        | Coloca tu avatar en forma de circulo                       |
| [lisa](https://github.com/zJuqn/zJuqnNPM-Docs#lisa)          | Crea una imagen con un tablero con texto                   |
| [gay](https://github.com/zJuqn/zJuqnNPM-Docs#gay)           | Coloca sobre un avatar/imagen la famosa bandera gay        |
| [gobierno](https://github.com/zJuqn/zJuqnNPM-Docs#gobierno)      | Coloca tu avatar en una junta de gobierno                  |
| [invert](https://github.com/zJuqn/zJuqnNPM-Docs#invert)        | Invierte los colores de tu avatar/imagen                   |
| [sepia](https://github.com/zJuqn/zJuqnNPM-Docs#sepia)         | Coloca la imagen/avatar con un tono calido                 |
| [stonks](https://github.com/zJuqn/zJuqnNPM-Docs#stonks)        | Coloca un avatar/imagen en la cara del stonks              |
| [triggered](https://github.com/zJuqn/zJuqnNPM-Docs#triggered)     | Coloca tu avatar/imagen en forma furiosa                   |
| [deletetrash](https://github.com/zJuqn/zJuqnNPM-Docs#deletetrash)   | Haz que tu avatar/imagen aparezca en una ventana de windows|
| [gray](https://github.com/zJuqn/zJuqnNPM-Docs#gray)          | Invierte los colores de tu avatar/imagen a grises          |
| [anuncio](https://github.com/zJuqn/zJuqnNPM-Docs#anuncio)       | Coloca tu avatar/imagen en un anuncio                      |

# || Funciones:

## passwordsGen

Genera una contraseña aleatoria con los caracteres que tu elijas.

**Ejemplo:**

```js
// Definimos el package
const  zjuqn = require('zjuqn')

// Obtiene la funcion de el package
const  passGen = zjuqn.Passwords

// passGen(5) osea genera una contraseña de 5 caracteres
console.log(passGen(5)) 
```

## WelcomeImage

Esta funcion se usa para crear una imagen de bienvenida usando el package [canvas](https://npmjs.com/package/canvas), puedes customizar el color, el subtitulo y el background


La función devuelve un Promise(\<Attachment\>) para almacenar en búfer la imagen y convertirla en un [Attachment](https://discord.js.org/#/docs/main/stable/class/MessageAttachment), así que la funcion debe estar acompañada de un await.


```js
await  WelcomeImage()
```

**Parametros requeridos:**
- background
- avatar
- subtitulo
- color

**Ejemplo de los parametros:**

```js
await  WelcomeImage(background, avatar, subtitulo, color)
```

**Ejemplo:**

```js
//Definimos el package
const { WelcomeImage } = require('zjuqn')

//Definimos el background
const bg = "https://cdn.discordapp.com/attachments/881694247747731518/883073688541483038/circulo-brillante-iluminacion-purpura-aislado-sobre-fondo-oscuro_1441-2396.png"

//Definimos el avatar
const av = message.author.displayAvatarURL({ format: 'png'})

//Definimos el subtitulo
const sub = "Bienvenido"

//Definimos el color
const color = "#ccc"


//Creamos la imagen
const imagen = await WelcomeImage(bg, av, sub, color)

//Enviamos la imagen
        message.channel.send({ files: [imagen]})
```

## Wikipedia

Con esta funcion podemos buscar cosas en wikipedia en ESPAÑOL LATINOAMERICA

```js
//Definimos el package
const { Wikipedia } = require('zjuqn')

//Definimos los argumentos y si no coloca argumentos retornamos
        let pregunta = args.join(" ")
        if(!pregunta) {
            return message.reply(':x: | Porfavor ingrese lo que quiere buscar. Uso de el comando: **wikipedia <pregunta>**')
        }

        //Creamos una nueva funcion de Wikipedia
        const res = new Wikipedia({
            message: message,//Definimos el message
            color: "RED",//Definimos el color del embed
            query: pregunta//Definimos lo que buscara
        })

        res.fetch()//Ejecutamos la funcion fetch que es la que nos enviara el embed con la informacion
```

## npmData

Con esta funcion puedes buscar datos de un npm

```js
//Definimos el package
const { npmData } = require('zjuqn')
const Discord = require('discord.js')

/**
 * @param {Discord.Message} message//Hacemos el parametro message que es el parametro que nosotros ingresaremos en la constante res
 */ 

//Definimos los argumentos y si no coloca argumentos retornamos
        let npmname = args.join(" ")
        if(!npmname) {
            return message.reply(':x: | Porfavor ingrese el nombre del npm a buscar!')
        }

        //Ingresamos los datos
        const res = new npmData({
            message: message,//Definimos el message
            color: "BLUE",//Definimos el color del embed
            npm: npmname//Definimos lo que buscara
        })

        res.fetch()//Ejecutamos la funcion fetch que es la que nos enviara el embed con la informacion del npm
```

## boostCard

```js
//Definimos el package
const  zjuqn  = require('zjuqn')

//Hacemos la funcion
const card = zjuqn.boostCard

//Definimos una constante con el avatar
const av = message.author.avatarURL({ format: 'png'})


//Genera la imagen
const boostCa = await card(av)

//Envia la imagen

//Definimos discord.js
const { MessageEmbed } = require('discord.js')

//Hacemos un nuevo embed

const embedCard = new MessageEmbed()
.setTitle("BoostCard")
.setImage(boostCa)//Colocamos la boostCard en la imagen
.setFooter("Gracias por el boost")

message.channel.send({embeds: [embedCard]})//Enviamos el embed

```

## ship

La función devuelve un Promise(\<Attachment\>) para almacenar en búfer la imagen y convertirla en un [Attachment](https://discord.js.org/#/docs/main/stable/class/MessageAttachment), así que la funcion debe estar acompañada de un await.

```js
const zjuqn = require("zjuqn")

await zjuqn.ship(avatar1, avatar2, background, image)
```

**Parametros:**

- avatar1
- avatar2
- background
- image

**Ejemplo:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Definimos el background
const bg = "https://cdn.discordapp.com/attachments/857028526153400380/883075610660970586/welcomeapi.png"

//Definimos la imagen que aparecera en el centor de las dos imagenes
const imgn = "https://cdn.discordapp.com/attachments/881694247747731518/884562722228940830/Heart-SG2001-transparent.png"

//Realizamos la funcion
const file = await zjuqn.ship(message.author.avatarURL({format: 'png'}), message.author.avatarURL({format: 'png'}), bg, imgn)
```

## blur

Funcion para que un avatar comun se desenfoque

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
const blur =  zjuqn.blur(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```
![](https://cdn.discordapp.com/attachments/857032641332248597/883748331917045760/zjuqn-blur.png)

## gay

Con esta funcion con el avatar de cualquier persona puedes hacer que se coloque una bandera multicolor

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
const gay =  zjuqn.blur(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```
![](https://cdn.discordapp.com/attachments/857032641332248597/883748330730053692/gay-npm.png)

## gray

Con esta funcion colocas el avatar de una persona en color gris/blanco y negro

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
const gray =  zjuqn.blur(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```
![](https://cdn.discordapp.com/attachments/857032641332248597/883748324333740062/zjuqnpm-gray.png)

## lisa

**Parametros:**


- texto

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.lisa("HOLAAAAAAAA SOY LISA").then(m => {
    message.channel.send({ files: [m]})
})
```

## deletetrash

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.deletetrash(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## anuncio

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.anuncio(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## sepia

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.sepia(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## gobierno

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.gobierno(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## triggered

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.triggered(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## stonks

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.stonks(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## circle

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.circle(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

## invert

**Parametros:**

- avatar

**Ejemplos:**

```js
//Definimos el package
const zjuqn = require('zjuqn')

//Hacemos la funcion
zjuqn.invert(message.author.avatarURL({ format: 'png'})).then(m => {
    message.channel.send({ files: [m]})
})
```

[Servidor De Soporte](https://discord.gg/fCbkwngUHz) | [zJuqn NPM](https://www.npmjs.com/package/zjuqn)
