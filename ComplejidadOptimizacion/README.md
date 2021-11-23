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
Todos los problemas NPC son NP y NP-Hard. Son aquellos problemas que:
- **NO** han podido ser solucionados en tiempo polinomial por una máquina determinista.
- **SI** pueden ser solucionados en tiempo polinomial por una máquina no determinista.
- **Todo problema en NPC** puede ser solucionado a través de ellos.

### La clase NPC y su atractivo
Si un problema NPC puede ser solucionado en tiempo polinomial, entonces todos los problemas NPC pueden también ser resueltos en tiempo polinomial.

## Reducción
Es un algoritmo que convierte instancias de un problema A a instancias de un problema B, donde las instancias positivas de A sigan siendo instancias positivas de B, al igual que con instancias negativas.

Para mostrar que un problema es tan difícil como otro se usa este concepto, teniendo en cuenta que reducción es un procedimiento que transforma en tiempo polinomial cualquier instancia $\alpha$ de un problema A a una instancia $\beta$ del problema B, y que permite dar la solución al problema A de forma correcta.

# Problema de satisfactibilidad (SAT)
El problema de satisfactibilidad booleana es el primer problema demostrado NP completo. SAT es NP y cualquier problema NP puede ser reducido a SAT en tiempo polinomial.

El problema consiste en un conjunto V de n variables booleanas ```v1, v2, v3...vn``` y un conjunto C de m clausulas ```c1, c2, c3...cm``` en forma normal conjuntiva (FNC). Se busca si existen valores de las variables que hagan que la expresión sea verdadera (es decir, satisfactible).

## 3SAT
Es una colección de C cláusulas en forma normal conjuntiva (FNC) donde cada cláusula contiene exactamente 3 literales. Para probar que 3SAT es NPC:
- Probar que 3SAT $\in$ NP.
- Probar que 3SAT $\in$ NP-Hard.

### 3SAT $\in$ NP
- Dada una instancia positiva de 3SAT y el certificado, sólo se debe chequear cada cláusula para evaluar que se satisfaga. La verificación se puede hacer en tiempo polinomial $3*|C|$ equivalente a $O(|C|)$.
- Dada una instancia negativa de 3SAT, ningún certificado puede hacer que el algoritmo verifique la instancia.

## 3SAT $\in$ NP-Hard
- Se procede a realizar una reducción desde SAT. Nótese que 3SAT es un problema más restringido que SAT, y se debe describir un algoritmo que transforme cada instancia de SAT a 3SAT en tiempo polinomial SAT $\prec_p$ 3SAT.
- Transformar cada cláusula de una instancia de SAT en un conjunto de cláusulas de 3 - SAT (lógicamente equivalentes).

# Demostración de NPC de programación entera (IP)
- **Instancia:** Un conjunto $v$ de variables enteras, un conjunto de desigualdades sobre las variables, una función $f(v)$ para maximizar y un entero $B$.

**Ejemplo programación entera:**
$$v_1 \geq 1, v_2 \geq 0$$
$$v_1 + v_2 \leq 3$$
$$f(v) = 2v_2, B = 3 => f(v) \geq B$$

### Instancia positiva o negativa
Un problema de decisión dada una instancia o es positiva o es una instancia negativa, no puede ser ambas. Por otra parte si alguna combinación de valores cumple con todas las condiciones es una instancia positiva, de lo contrario es instancia negativa.

Para probar que la programación entera es NPC se necesita:
- (Ser NP) Probar que _IP_ $\in$ _NP_.
- (Ser NP-Hard) Probar que _IP_ $\in$ _NP - Hard_.
	- Seleccionar un problema NPC A conocido.
	- Describir un algoritmo que transforme cada instancia de A a una instancia de IP. Esto es A $\prec_p$ IP.
	- Probar que el algoritmo anterior corre en tiempo polinomial y que la nueva instancia es de tamaño polinomial.
	- Probar que el algoritmo es correcto.

## ¿Está IP en NP?
La clase NP es aquella cuyos problemas son verificables en tiempo polinomial.

Dada una instancia positiva de IP y el certificado $v$, sólo se debe verificar que cada desigualdad se cumpla y que $f(v) \geq B$. Esto se puede hacer en tiempo $O(mn)$ donde $m$ es el número de desigualdades y $n$ el número de variables.

Dada una instancia negativa de IP ningún certificado puede hacer que el algoritmo verifique la instancia, por tanto _IP_ $\in$ _NP_.

## Instancias positivas en 3-SAT se reducen a instancias positivas en IP
- Si una instancia de 3-SAT es positiva, es porque existe una asignación de cada variable $x$ que satisface todas las cláusulas.
- Por cada variable $x$ en 3-SAT, hay dos variables $x$ y $\overline{x}$ = 0 en IP.
- Si $x$ es asignada a falso en 3-SAT, considere $x$ = 0 y $\overline{x}$ = 1 en IP.
- Dada una cláusula $C_i = (l_{i1} \vee l_{i2} \vee l_{i3})$ en la instancia de 3_SAT, si la asignación satisface $C_i$, entonces también se satisface la desigualdad $l_1 + l_2 + l_3 \geq 1$.

## Instancias negativas en 3-SAT se reducen a instancias negativas en IP
- Si una instancia 3-SAT es negativa, es porque en cada asignación de verdad de cada variable $x$ al menos una cláusula queda sin satisfacer.
- Si esa cláusula es $C_i = (l_{i1} \vee l_{i2} \vee l_{i3})$ en la instancia de 3SAT, entonces la asignación correspondiente en IP tampoco satisface la desigualdad $l_1 + l_2 + l_3 \geq 1$.
- Por lo tanto no existe solución para la instancia en IP, o sea que también es una instancia negativa.

## Complejidad de la reducción
- Si se tienen $n$ variables en SAT, se crean $2n$ variables y $6n$ desigualdades en IP.
- Si se tienen $m$ clausulas en SAT, se crean $m$ desigualdades en IP.

Se demostró que IP es NP. También se mostró que IP es NP-Hard a través de una reducción de SAT. Adicionalmente la reducción es correcta como se evidenció en cada caso y se puede realizar un tiempo polinomial, luego se concluye que IP es NPC.

## Aclaraciones sobre la reducción
- La reducción preserva la estructura del problema. Note que la reducción no resuelve el problema, simplemente lo pone en un formato diferente.
- Las posibles instancias resultantes de IP son un pequeño subconjunto de las posibles instancias. Dado que algunas de ellas son duras, el problema en general es duro.
- La transformación captura la esencia del por qué IP es duro - no tiene que ver con grandes coeficientes o con grandes rangos en los dominios de las variables - la restricción 0-1 es suficiente.

# Demostración de NPC de Vertex Cover

### Definición
Una instancia es un grafo $G = (V, E)$ y un entero $k \leq |V|$.

### Pregunta
¿Existe un subconjunto de a lo sumo $k$ vértices, donde cada arista $e \in E$ tiene al menos uno de los vértices en el subconjunto?

- **Entrada:** Un grafo no dirigido $G = (V, E)$ y una constante $k \leq 	|V|$.
- **Salida:** 1 si existe un subconjunto $V'$ de $V$ tal que $|V'|$.

## ¿Está VC en NP?
Dada una instancia positiva de VC y el certificado $V'$, sólo se debe verificar que cada arista tenga un vértice en $V'$ y que $|V'| \leq k$. Esto se puede hacer en tiempo $O(m |V'| + |V|)$ donde $m$ es el número de aristas.

Dada una instancia negativa de $VC$ ningún certificado puede hacer que el algoritmo verifique la instancia (o falla porque no cubre o falla por el tamaño), y por tanto VC $\in$ NP.

## Definiendo la reducción
- **Idea 1:** Simular cada variable booleana $X$ de 3-SAT con un par de nodos de un grafo representando los literales $x$ y $-x$. En un VC del grafo, debe quedar siempre uno de los dos nodos y nunca los dos, de manera que esto represente una asignación de verdad. Por lo menos $n$ vértices se necesitan para cubrir todas las aristas.
- **Idea 2:** Simular cada cláusula de 3-SAT con un grafo completo de 3 nodos (uno por literal).
- **Idea 3:** Conectar cada grafo asociado a una cláusula con los literales correspondientes asociados a la asignación de verdad.

## Procedimiento de reducción
Dada una instancia 3-SAT con $n$ variables y $c$ cláusulas, construimos un grafo $G = (V, E)$ aplicando las ideas 1, 2 y 3.