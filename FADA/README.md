# Diseño y análisis de algoritmos
Son indispensables estos pasos: Entender el problema, diseñar el algoritmos, probar la correctitud (si no es correcto regresar al paso anterior), analizarlo (sí no está bien regresar al paso anterior) e implementarlo.

## Pasos para el análisis de eficiencia de un algoritmo
- Determinar los parámetros que indican el tamaño de la entrada.
- Identificar la operación básica del algoritmo.
- Verificar si el número de veces que se ejecuta la operación básica depende exclusivamente del tamaño de la entrada. En caso contrario, se tendrán que analizar el peor (mejor) caso o el caso promedio.
- Definir una expresión matemática que represente el número de veces que la operación básica se ejecuta en el algoritmo.
- Determinar una solución explícita para la expresión del punto anterior, y determinar su orden de crecimiento.

## ¿Qué es hacer análisis de algoritmos?
- Calcular tiempo de computación.
- Espacio (memoria).
- Analizar las estructuras de datos utilizadas.
- Identificar el tipo y número de datos de entrada al algoritmo.
- Medidas de análisis (tiempo de ejecución) | Medidas experimentales.

### Ejemplo
```
Algoritmo Misterio(A[0...n-1])
Entrada: Un arreglo A[0...n-1]
S <- 0`
for i <- 0 to n-1 do
	S <- A[i] + S
return S
```

|      Paso para el análisis de eficiencia          | Resultado |
|----------------|-------------------------------|
| Tamaño de entrada | $n$ |
| Operación básica | Línea 3 ```S <- A[i] + S``` |
| Depende exclusivamente del tamaño de entrada | Sí |
| Expresión correspondiente al # de veces que se ejecuta la operación básica | $\sum_{i=0}^{n-1}1$ |
| Forma explícita de la expresión | $n$ |
| Orden de crecimiento | $O(n)$ |

## Correctitud
Se dice que un algoritmo es **correcto**, si para cada instancia, el algoritmo termina con la salida correcta.

## Análisis de algoritmos
- Correctitud.
- Eficiencia.
	- Tiempo.
	- Espacio.
- Estructuras de datos utilizadas.
- Modelo computacional.
- El tipo y número de datos con los cuales trabaja (escalabilidad).

## Tiempo de cómputo
El tiempo de cómputo $T$ de un algoritmo depende del tamaño de la entrada $T(n) = f(n)$, donde $n$ es el tamaño de la entrada.

**Ejemplo:**
Teniendo $T_1(n) = 3n^2$ y $T_2(n) = 6n^3$ , para $n = 100$, se tiene que $T_1(n) = 3*100^2 = 30000$ y $T_2(n) = 6*100^3 = 6000000$ el mejor $T$ sería el $T_1$ ya que es de orden cuadrático.

# Algoritmos de ordenamiento

## Insertion sort - $O(n^2)$
```
for j <- 2 to length[A]
	do key <- A[j]
		i <- j-1
		while i > 0 and A[i] > key
			do A[i+1] <- A[i]
				i <- i-1
		A[i+1] <- key
```

| Instrucción | Costo | Veces que se repite |
|----------------|------------------------|--------------------|
| ```for j <- 2 to length[A]``` | $c_1$ | $n$ |
| ```do key <- A[j]``` | $c_2$ | $n-1$ |
| ```i <- j-1``` | $c_3$ | $n-1$ |
| ```while i > 0 and A[i] > key``` | $c_4$ | $\sum_{j = 2}^{n} t_j$ |
| ```do A[i+1] <- A[i]``` | $c_5$ | $\sum_{j = 2}^{n} (t - 1)$ |
| ```i <- i-1``` | $c_6$ | $\sum_{j = 2}^{n} (t - 1)$ |
| ```A[i+1] <- key``` | $c_7$ | $n-1$ |