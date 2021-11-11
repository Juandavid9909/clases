# Motivación

## Problema del cambio de monedas
Considere el problema del cambio de monedas definido de la siguiente forma: Si A = {1, 20, 50} y P = 72, ¿cuál es la salida correcta?

La respuesta correcta es {2, 1, 1}. Para solucionar este problema podemos implementar un algoritmo que se encargue de dividir el valor por cada moneda (desde la mayor a la más pequeña) permitiéndonos saber cuántas monedas de cada valor podemos colocar. Cabe resaltar que este algoritmo no siempre da la solución más eficiente, esto debido a que si por ejemplo tenemos A = {1, 20, 50} y P = 62 el algoritmo retornará la respuesta {12, 0, 5} cuando la solución más efectiva es {2, 3, 0}.

Una solución correcta puede ser recorrer el arreglo de monedas iniciando de menor a mayor contando la cantidad de monedas que se usan por cada una (iniciando en 50, la siguiente iteración desde 20 y así sucesivamente).

Existen problemas en la vida real que tienen soluciones computacionales eficientes (problemas fáciles) y otros para los que no se ha encontrado ninguna solución computacional eficiente (problemas difíciles).

Como ingenieros de sistemas, podemos encontrarnos con diversos problemas computacionales que:
- Son reales, importantes y de optimización.
- Son fáciles de entender y, aún, de especificar, pero...
- No somos capaces de solucionarlos eficientemente con un computador.
- Los algoritmos naturales que resuelven el problema son ineficientes (consumen mucha memoria, tardan mucho o ambas).

# Complejidad computacional
La complejidad computacional considera los algoritmos para resolver un problema dado. Existen diversas formas de medir la complejidad de un algoritmo. La complejidad se mide en función del tamaño de la entrada.

## Clases de complejidad
- **Temporal:** Tiempo requerido por un algoritmo para resolver un problema dado.
- **Espacial:** Espacio que requieren las estructuras de datos de un algoritmo para resolver un problema dado.

## Problemas indecidibles
Están por fuera del alcance de el curso pero entre ellos se tiene el problema de la parada que es indecidible no computable.

## Problemas decidibles
Están dentro del alcance del curso y son aquellos para los cuales se puede construir un algoritmo que lleve a una respuesta correcta.

- **Problemas tratables:** Son aquellos que se pueden solucionar con algoritmos polinomiales $O(n^k)$.
- **Problemas intratables:** Son aquellos para los que no conocemos algoritmos eficientes, es decir, los algoritmos que existen solucionan el problema en tiempo no polinomial $\Omega (a^n)$.

## Problemas de optimización
Problemas donde cada solución factible tiene un valor asociado y se espera encontrar la solución con el mejor valor.

## Problemas de decisión
Problemas cuya respuesta es simplemente SI o NO. El estudio de la complejidad aplica directamente sobre problemas de decisión puesto que es conveniente al realizar **reducciones**.

## Máquinas deterministas
Esta ejecuta un solo paso ante la lectura de un símbolo de entrada. Este es un modelo computacional actual.

## Máquinas no deterministas
Ejecuta la mejor acción posible ante la lectura de un símbolo de entrada. Ante una posible ramificación puede explorar todas las bifurcaciones a la vez.

# Clasificación de problemas
## Clase P
La clase P corresponde a los problemas que se resuelven en tiempo polinomial con una máquina de Turing determinista.

## Clase NP (Non deterministic polynomial)
Consiste de aquellos problemas que se resuelven en tiempo polinomial con una máquina de Turing no determinista.

## Clase NP - versión alternativa
Es aquella cuyos problemas son verificables en tiempo polinomial, lo que significa que dada una solución y un certificado de tamaño polinomial, entonces, es posible verificar, en tiempo polinomial respecto al tamaño de la entrada, que la solución es correcta.

## Clase NPC
Son aquellos problemas que:
- **NO** han podido ser solucionados en tiempo polinomial por una máquina determinista.
- **SI** pueden ser solucionados en tiempo polinomial por una máquina no determinista.
- **Todo problema en NPC** puede ser solucionado a través de ellos.

### La clase NPC y su atractivo
Si un problema NPC puede ser solucionado en tiempo polinomial, entonces todos los problemas NPC pueden también ser resueltos en tiempo polinomial.