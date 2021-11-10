# Los lenguajes de programación

## Paradigmas de programación
Un paradigma es un enfoque de programación basado en un conjunto coherente de principios o en una teoría matemática.

## Programar sistemas complejos
Están compuestos por partes que interactúan de una forma muy bien definida y proveen un buen comportamiento. Los paradigmas son el sustento de la construcción de sistemas complejos.

## Vista tradicional de los lenguajes de programación
- Lenguajes de máquina
- Lenguajes estructurados
- Programación procedimental
- Programación modular
- POO
- Programación orientada a servicios

## Concurrencia
Actividades que evolucionan independientemente, el mundo de la programación es concurrente en 3 niveles:
- **Sistemas distribuidos:** Computadores enlazados por una red, cada actividad concurrente es llamada un computador
- **Sistema operativo de cada computador:** La concurrencia es llamada proceso, cada proceso tiene un espacio en memoria independiente (computación competitiva)
- **Actividades dentro de los procesos:** Son llamadas hilos, todos los hilos comparten el mismo espacio en memoria (computación cooperativa)

Aplicar concurrencia en lenguajes como C++ y Java se necesitan conceptos como monitores o candados, los cuales son difíciles, sin embargo el problema no es la concurrencia, son los monitores debido a que no son el concepto adecuado para concurrencia.

## Flujos de datos determinísticos
Un programa se escribe en forma de producto/consumidor donde hay un productor, un consumidor y el productor produce cosas que consume el consumidor.

Los hilos comparten la variable Xs por la cual intercambian datos (variable de flujo de datos) que resulta en un comportamiento que se llama "comunicación por flujos". Algunas veces no es suficiente para expresar todos los problemas de programación que deseamos, por ejemplo cuando hay 2 clientes que desean hablar con un servidor ya que el servidor atenderás las solicitudes por orden, cosa que no se desea.

## Escogencia no determinística
Aparece cuando 2 o más entidades (clientes) interactúan con la misma entidad (servidor). Cada cliente interactúa con el servidor independientemente de los otros clientes y el servidor debe decidir qué mensaje manejará primero, por lo que escoge y esta escogencia es llamada como no determinismo. Al añadir este nuevo concepto a un lenguaje de programación surge el paradigma de programación de flujo de datos multiagente.

### Ejemplos
#### Flujo de datos determinístico
- Simulación lógica digital
- Problema de Josephus
- Problema de Hamming (programación perezosa)
- Problemas de buffer acotados

#### Flujos multiagentes
- Multiagentes que están conversando unos con otros
- Protocolos distribuidos (RMI o algoritmos distribuidos)
- Sistema de control de ascensores

### Nota
POO es el paradigma incorrecto para la programación en Internet, esto debido a lo siguiente:
- **Importante:** Aislamiento, concurrencia, mensajes asíncronos, programación de alto orden
- **No importante:** Herencia, clases, métodos, diagramas UML, monitores

## Principio de extensión creativa
Tiene que ver con cuándo crear o cuándo aparece un nuevo paradigma. Si estamos usando algún paradigma y los programas empiezan a volverse complicados por razones técnicas entonces se introduce este nuevo concepto de programación, por ejemplo las excepciones ya que C no cuenta con esta facilidad.

## Conceptos generales y específicos de programación en Oz

| Concepto | Explicación | Código |
|-------------------|--------------|--------------|
| Cálculos sencillos   | Permite imprimir los resultados de las operaciones en una nueva ventana |```{Browse 9999*9999} O {Browse {Fact 5}}```
| Variables declarativas | Declarar nuevas variables |```declare v = 9999 * 9999```
| Funciones | Bloques de código reutilizables |```declare fun {Fact N} if N==0 then 1 else N*{Fact N-1} end end```
| Datos estructurados (listas) | Estructura de datos que nos permite almacenar muchos datos dentro de ella |```[5 6 7 8] o nil, H=5 T=[6 7 8] {Browse H|T}```
| Descomposición de listas | Descomponer listas creadas |```declare L=[5 6 7 8] case L of H|T then {Browse H} {Browse T} end```


- **Variables declarativas:** Una vez una variable obtiene un valor siempre será el mismo, aunque pueda ser diferente en cada computación el valor será el mismo durante la actual computación
- **Listas:** Para acceder a la cabeza (H) se usa ```L.1=5``` y para la cola (T) ```L.2=[6 7 8]```