# Análisis económico de inversiones

## Inversión
Usar un capital en algún negocio para obtener un mayor capital.

## Economía
Es esa ciencia que estudia el uso o como se administran unos recursos con el fin de satisfacer ciertas necesidades a un grupo de personas.

## Ingeniería
El uso que hacemos de un conocimiento técnico para hacer unos diseños para desarrollar formas de utilizar en forma económica ciertos materiales en beneficio de las personas

## Palabras claves
Inversión - capital, economía - recursos - necesidades - grupos humanos, ingeniería - desarrollar - en forma económica - materiales y las fuerzas de la naturaleza - beneficio de la humanidad.

El valor del dinero depende de la magnitud y el período de tiempo. Sólo se puede hacer sumas y restas de flujos de dinero que estén ubicados en el mismo período.

## Flujos de caja descontado
Mover flujos de dinero hacia el pasado o hacia el futuro, para hacerlo es necesario usar una tasa de interés.

## Proceso de toma de decisiones
- Identificar y entender el problema
- Recolectar datos relevantes y definir alternativas de solución viables
- Estimar flujos de efectivo
- Identificar el criterio económico
- Evaluar cada alternativa
- Seleccionar la mejor alternativa
- Implementar la solución y medir resultados

## Principios fundamentales
- El dinero tiene valor en el tiempo
- Realice inversiones que se justifican económicamente
- Escoja la alternativa de inversión mutuamente excluyente que maximice el valor económico
- Dos alternativas de inversión son equivalentes si tienen el mismo valor económico
- El ingreso marginal debe exceder el costo marginal
- Continúe invirtiendo siempre y cuando cada incremento de inversión adicional resulte en un retorno mayor que el retorno esperado por el inversionista
- Enfocarse en las diferencias
- Compare alternativas de inversión durante un período de tiempo común
- El riesgo y el retorno de una inversión tienen una relación directa
- Costos del pasado son irrelevantes, a menos que impacten costos futuros

# Parte 1: Crecimiento y desarrollo
Crecimiento económico no es igual a desarrollo, proyectos -> crecimiento -> desarrollo.

## Crecimiento económico
Corresponde al aumento del valor de los bienes y servicios finales, o el valor de la renta producidos por una economía en un determinado período de tiempo. Se encuentra enfocado en una región o país. Aquí hacen parte:

- **Capital:** Maquinaria, equipos, instalaciones
- **Educación:** Los países con mayor educación tienen el mayor crecimiento económico
- **Progreso tecnológico:** En la medida que los países logren desarrollar e incorporar tecnologías tendrán mayores niveles de crecimiento

## Desarrollo económico sostenible
Es la capacidad de un país o región para crear riqueza con la finalidad de promover o mantener el bienestar económico y social de sus habitantes.

Crecimiento: Var % positiva PIB.
PIB per cápita = PIB / Población

## Desempleo
Complemento del empleo, personas que pueden laborar / personas laborando activamente.

## Inflación
Aumento del nivel general de los precios -> Var IPC (índice de precios al consumidor) -> Precio -> Canasta familiar.

## Deflación
Los precios bajan debido a algún impacto como puede ser el COVID-19.

## Tasa de cambio
### Mercados cambiarios
Dólares que llegan y se van del país producto de las exportaciones

# Nomenclatura de los flujos
- **Presente o pasado** $P_i =$ flujo de efectivo que se da en el presente o en el pasado con respecto a un observador. En los diagramas de flujo las flechas hacia arriba indican ingresos y las flechas hacia abajo egresos.
- **Futuro** $F_j =$ flujo de efectivo que se da en el futuro con respecto al observador.
- **Anualidad** $A_{n_1-n_2} =$ flujos de efectivo consecutivos uniformes (todos con la misma cantidad). La anualidad inicia en el periodo $n_1$ y termina en el período $n_2$. Sin embargo, el primer flujo de la anualidad se da un período posterior a donde inicia la mensualidad.
- **Gradiente aritmético** $(B, G)_{n_1-n_2}$ flujos de efectivo consecutivos que crecen/decrecen en una misma magnitud **G** cada período. El gradiente aritmético inicia en un período $n_1$ y termina en un período $n_2$. Sin embargo la base **B**, que es el primer flujo del gradiente, se da en un período posterior a donde inicia el gradiente aritmético. La diferencia entre $n_2$ y $n_1$ da el número de flujos.
- **Gradiente geométrico** $(T, s)_{n_1-n_2}$ flujos de efectivo consecutivos que crecen/decrecen en un mismo porcentaje **s** cada período. El gradiente inicia en el período $n_1$ y termina en el período $n_2$. Sin embargo, la base **T**, que es el primer flujo del gradiente, se da en un período posterior a donde inicia el gradiente geométrico.

# Equivalencias

## Interés
El interés I, es la compensación que reciben los individuos, firmas o personas naturales, por el sacrificio en que incurren al ahorrar una suma P.

- El interés en cantidad monetaria es la diferencia entre la cantidad de dinero pagado (recibido) al final menos la cantidad de dinero recibido (pagado) al inicio:
$$I = monto final - monto inicial$$

- Este fenómeno económico real, se mite con la **tasa de interés i**, la cual a su vez, se representa por un porcentaje. Este porcentaje se calcula dividiendo el interés **I** recibido o pagado por un período, por el monto inicial **P**; de modo que la tasa de interés será:
$$i = \frac{I}{P}$$

## Interés simple vs interés compuesto
- **Interés simple:** El interés para cada período se calcula con base únicamente sobre el valor del monto inicial:
$$I_t = P * i$$

- **Interés compuesto:** El interés para cada período se calcula sobre el monto inicial más el monto total del interés acumulado en todos los períodos anteriores:
$$I_t = (P + \sum_{j=1}^{j=t-1}I_j) * i$$

# Equivalencia entre anualidad, presente y futuro

## Fórmulas
Recordemos que:
- **i:** Interés.
- **n:** Período de tiempo.
- **F:** Valor futuro.
- **P:** Valor presente.
- **A:** Magnitud/anualidad.

### Calcular presente teniendo valor futuro
$$P =  \frac{F}{(1 + i)^n}$$

### Calcular futuro teniendo valor presente
$$F = \frac{P}{(1 + i)^n}$$

### Teniendo la anualidad calcular un futuro
$$Fi = A(1 + i)^n - A$$
$$F = \frac{A((1 + i)^n - 1)}{i}$$

### Calcular anualidad teniendo futuro
$$A = \frac{Fi}{(1 + i)^n - 1}$$

### Calcular presente teniendo anualidad
$$P = A \frac{(1 + i)^n - 1}{i (1 + i)^n}$$

### Calcular anualidad teniendo presente
$$A = P \frac{i (1 + i)^n}{(1 + i)^n - 1}$$