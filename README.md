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

[Servidor De Soporte](https://discord.gg/fCbkwngUHz) | [zJuqn NPM](https://www.npmjs.com/package/zjuqn)
