# Diseño y análisis de algoritmos
Son indispensables estos pasos: Entender el problema, diseñar el algoritmos, probar la correctitud (si no es correcto regresar al paso anterior), analizarlo (sí no está bien regresar al paso anterior) e implementarlo.

## Pasos para el análisis de eficiencia de un algoritmo
- Determinar los parámetros que indican el tamaño de la entrada.
- Identificar la operación básica del algoritmo.
- Verificar si el número de veces que se ejecuta la operación básica depende exclusivamente del tamaño de la entrada. En caso contrario, se tendrán que analizar el peor (mejor) caso o el caso promedio.
- Definir una expresión matemática que represente el número de veces que la operación básica se ejecuta en el algoritmo.
- Determinar una solución explícita para la expresión del punto anterior, y determinar su orden de crecimiento.

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
- Correctitud
- Eficiencia
	- Tiempo
	- Espacio
- Estructuras de datos utilizadas
- Modelo computacional
- El tipo y número de datos con los cuales trabaja (escalabilidad)

# Algoritmos de ordenamiento

## Insertion sort
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
| ```while i > 0 and A[i] > key``` | $c_4$ | $(n-1)()$ |
| ```do A[i+1] <- A[i]``` |  |  |
| ```i <- i-1``` |  |  |
| ```A[i+1] <- key``` | $c_7$ | $n-1$ |