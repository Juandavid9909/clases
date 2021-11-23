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

# Introducción a OpenGL

## ¿Qué es OpenGL?
- Es una interfaz para la generación de gráficos (Graphics rendering API).
- Imágenes de alta calidad generadas a partir de primitivas geométricas.
- Independiente del sistema de ventanas.
- Independiente del sistema operativo.
- Inicialmente desarrollado por Silicon Graphics Inc.
- OpenGL es controlado por Kronos group, algunos de sus miembros son:
	- AMD/ATI, Apple Inc., Ericsson, Google, Intel Corporation, Motorola, Nokia, Nvidia, Samsung Electronics, Sony Computer Entertainment, Oracle/Sun Microsystems, Epic Games (Unreal Engine/Gears of War).

### Ventajas
- Es independiente del Hardware y del sistema operativo.
- Existe hardware dedicado que lo acelera considerablemente, permitiendo pintar escenas complejas a tiempo real (las últimas tarjetas pueden renderizar del orden de Millones de polígonos por segundo).
- Hay implementaciones para cualquier lenguaje (C, Python, Java, JavaScript, C#...).
- Al ser de bajo nivel da libertad para que el programador pueda construir encima lo que necesite.

## ¿Qué NO es OpenGL?
- Un lenguaje de programación, OpenGL se puede usar con casi cualquier lenguaje existente.
- Un programa de dibujo, OpenGL solo pinta primitivas gráficas (triángulos).
- Un motor gráfico, no tiene funciones de carga de recursos, gestión de escena, interfaz de usuario.
- Un gestor de escena 3D no permite detectar colisiones, seleccionar objetos con el ratón, etc.
- Un motor de videojuegos, no gestiona temas de audio, física, interacción, etc.
- Un sistema de ventanas.
- Un manejador de eventos.
- Un sistema de animación de objetos.
- Un sistema que controla la interacción entre objetos.
- Un sistema de base de datos de objetos tridimensionales.

## ¿Qué provee OpenGL?
- Un conjunto de funciones que controlan la configuración del sistema de dibujado.
- Un sistema de proyección que permite especificar objetos en 3 dimensiones y llevarlos a coordenadas de pantalla.
- Un conjunto de funciones para realizar transformaciones geométricas que permiten posicionar los objetos en el espacio.

## Sintaxis OpenGL
### Funciones
- Usa el pregifo "gl".
- Cada palabra después de gl, inicia con letra mayúscula.
- **Ejemplo:** glClearColor3f(), flBegin(), glEnd.

### Constantes
- Inician con "GL_".
- Sólo letras mayúsculas.
- Usa underscores(_) para separar palabras.
- **Ejemplo:** GL_COLOR_BUFFER_BIT.

## Backface culling
Es una técnica que permite acelerar el dibujado de polígonos eliminando aquellos cuya cara frontal NO sea vista. Esto pasa cuando se usan polígonos para definir superficies cerradas.

## Transformaciones geométricas
Se usan para:
- Definir la vista (orientación de la cámara, definir el tipo de proyección).
- Mapeo a la pantalla.

## MipMapping
- Un filtrado de más calidad que funcionara bien para todos los grados de escala implica un procesamiento de un nivel que es muy costoso de ralizar en tiempo real.
- **Solución:** Realizar el cálculo offline.
- En el momento de aplicar las texturas, OpenGL decide el nivel a utilizar en función de la cantidad de minimización a aplicar.
- Este cálculo es soportado directamente por el hardware.