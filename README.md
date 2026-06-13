# CTF - Requiem Cipher 🎵🔐

¡Bienvenidos a **CTF-Requiem Cipher**! 🎉  
Un reto donde la música no es solo música… y donde cada nota oculta un secreto que solo los más atentos sabrán descifrar.

Prepárate para enfrentarte a un desafío avanzado de **esteganografía musical**, permutaciones pseudoaleatorias y criptografía simétrica que pondrán a prueba tu capacidad de análisis en capas. 😈


## ¿De qué trata CTF-Requiem Cipher? 🤔

En este reto, una pieza musical aparentemente inocente esconde varias capas de información cifrada.

Se ha entregado un archivo **MIDI** que a simple vista parece una composición normal… pero que en su interior contiene una **clave AES**, un conjunto de **bits ocultos**, y un **código QR** que abre la puerta al mensaje final.

Tu misión será responder a la gran pregunta:

> **¿Puede esconderse un sistema criptográfico completo dentro de una melodía MIDI?**

Spoiler: sí… si sabes dónde mirar. 💀


## 🧠 Conceptos clave del reto

Durante el desafío tendrás que aplicar:

- 🎵 Análisis de formato MIDI y sus eventos
- 🕵️ Esteganografía en canales y velocidades de notas
- 🔀 Permutaciones pseudoaleatorias (seeded RNG)
- 📷 Reconstrucción de imágenes QR desde bits
- 🔐 Criptografía simétrica AES-CBC
- 🧠 Correlación de múltiples capas de información

Este no es un reto de fuerza bruta… es un reto de **observación y razonamiento en cadena**.



## ¿Por dónde empiezo? 🛠️

### 1. Descarga el reto

📥 [Descargar Requiem Cipher]((https://labs.thehackerslabs.com/machines/197))

### 2. Analiza el archivo

El reto incluye un archivo `requiem_cipher.mid`.  
Un MIDI no almacena audio, sino **instrucciones musicales**:

- Qué nota se toca
- Cuándo se toca
- Con qué intensidad (`velocity`)
- En qué canal y en qué pista

Si sabes que los datos pueden esconderse en esos campos… ya estás dentro del juego.

### 3. Encuentra las capas ocultas

No estás ante una pieza musical normal.  
Aquí hay **tres niveles de ocultación**:

| Canal | Nota | Contenido oculto |
|-------|------|-----------------|
| Canal 2 | 73 / 74 | Clave AES-128 |
| Canal 9 | 35 | Bits del código QR |
| Resto | Varias | Ruido / distracción |

Eso cambia completamente las reglas.

### 4. Rompe el sistema

Si logras seguir la cadena completa:

```
MIDI → clave AES → bits ocultos → deshacer permutación → QR → IV + ciphertext → AES-CBC → flag
```

Habrás provocado el **Requiem total del cifrado** 💥


## 🧩 Pistas y solución

Si te quedas atascado, puedes consultar la solución completa:

📖 [Writeup Requiem Cipher](https://beafn28.gitbook.io/beafn28/mis-ctfs/requiem-cipher)


## 🚀 ¿Estás listo?

Este reto no es trivial.  
Requiere entender cómo funciona la esteganografía **más allá de los metadatos y los archivos de imagen**.

Pero si lo resuelves, habrás aprendido una de las técnicas más originales de ocultación de información en criptografía aplicada.


## 💀 Mensaje final

> En esteganografía, no hace falta gritar para transmitir un mensaje…  
> basta con afinar el oído en el canal correcto.

Buena suerte, hacker.  
Y recuerda…

**hasta las sinfonías pueden guardar secretos.** 🎼💥
