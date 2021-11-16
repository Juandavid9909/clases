# Introducción
La computación gráfica se puede implementar en videojuegos, diseños, arquitectura, realidad virtual, imágenes médicas, sistemas de información geográfica o GPS. Los computadores usan OpenGL y DirectX para mostrar todo, además podemos realizar gráficos en 2D, ilustraciones y fuentes.

## Frame Buffer
Una imagen está compuesta por un arreglo de pixeles.

## Rasterización
Proceso de conversión de las primitivas gráficas (líneas, puntos, círculos, etc).

## Formación de imagen
Objeto, observador, fuente de luz, propiedades que describen los materiales.

## Modelaje geométrico
Como representar el mundo real:
- **Geometría:** Curvas, superficies, volumen.
- **Fotometría:** Luz, color, reflectancia.

# Hardware gráfico

## Sistema gráfico
- Procesador central
	- Memoria CPU
- Procesador gráfico
	- Memoria GPU
- Frame buffer

Cada pixel corresponde a una ubicación o área pequeña, en la imagen.

El frame buffer puede seer visto como el elemento principal de un sistema gráfico: resolución, profundidad o precisión y el color.

## Tecnologías de impresión

### Definiciones básicas
- **Tamaño de punto:** Diámetro del punto creado por el dispositivo.
- **Capacidad de direccionamiento:** Número de puntos por pulgada (puede ser diferente en _x_ y en _y_).
- **Resolución:** Espaciado más cercano que permite distinguir líneas negras y blancas adyacentes.

## Colores primarios sustractivos
Cyan, magenta y amarillo son los colores primarios sustractivos. Son los utilizados en las impresoras, dado que partiendo de una hoja en blanco se "sustraen" colores al blanco. La mezcla de los tres colores en valores iguales da el negro.

## Dithering
En una impresora blanco y negro, los puntos son dibujados con tinta negra, por tanto los puntos son negros. Las zonas no pintadas son blancas (si la hoja utilizada lo es).