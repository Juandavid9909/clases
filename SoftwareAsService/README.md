# Taller 1

## Diferencia entre aplicación cliente-servidor y aplicación web
La aplicación cliente-servidor se usa mediante una red privada y si algún usuario externo desea acceder debe usar VPN's, mientras que las aplicaciones web son más globales. Para el cliente servidor se instala una interfaz localmente y en aplicaciones web es mediante la web.

## Frameworks
Son estructuras tecnológicas que nos permiten una organización y desarrollo más eficiente y sencillo.

## Computación en la nube
Se permite elegir qué queremos guardar y procesar, además de que es administrable desde dispositivos móviles, ejemplo AWS, Azure.

### Beneficios
Disminución de costos, almacenamiento flexible y accesibilidad.

### Desventajas
La información no está local por lo que las políticas de datos se pueden no cumplir.

# Taller 2

## Plan de continuidad de negocio
Es una herramienta tanto de análisis como de toma de decisiones, para asegurar la excelencia operativa ante cualquier escenario adverso, es un plan logístico para la práctica de cómo una organización debe recuperar y restaurar sus funciones críticas parcial o totalmente interrumpidas dentro de un tiempo predeterminado después de una interrupción no deseada o desastre. En los Estados Unidos, las entidades gubernamentales se refieren al proceso como planificación de continuación de operaciones.

## Acuerdo de nivel de servicio ANS
Un acuerdo de nivel de servicio, también conocidas por las siglas SLA, es un acuerdo escrito entre un proveedor de servicio y su cliente con objeto de fijar el nivel acordado para la calidad de dicho servicio.

## Plan de contingencia
Un plan de contingencia es aquel que se tiene como un plan b en caso tal de que todo lo planeado anteriormente pueda salir mal. Esto con el fin de controlar los problemas que se puedan llegar a presentar.

## Disponibilidad en tecnologías de la información
La alta disponibilidad es la calidad de un sistema o componente que asegura un alto nivel de rendimiento operativo durante un período de tiempo determinado.

## Redundancia
La redundancia es la repetición de datos y hardware que son de carácter crítico que se quiere asegurar ante la posibilidad de fallos que pudieran surgir ya sea por el desgaste natural del uso del hardware o software.

La redundancia puede hacer que tu sistema sea más eficiente, esto pues al tener más réplicas instaladas tendrás la capacidad de realizar mayor trabajo, atender solicitudes y procesar más datos, con esto tu sistema será más rápido ya que disminuye la latencia y permite que el sistema maneje un alto rendimiento de datos.

El problema se podría ver al momento de tener un aumento que puede ser innecesario en el tamaño de las bases de datos, además de contar con la posibilidad de tener corrupción de datos debido a la redundancia.

## Disponibilidad
- Continuidad en la prestación de un servicio.
- La disponibilidad es uno de los elementos consideradores en los acuerdos de nivel de servicio (ANS).
- El rol de los planes de contingencia.
	- Deben ser definidos.
	- Deben ser probados.
	- Se debe registrar la evidencia de las pruebas.
- El costo de los planes de contingencia.
- Ejemplos de planes de contingencia:
	- Restaurar un backup.
	- Habilitar un servidor de respaldo.
	- Solución en la nube.
	- Trabajo manual.

## Alta disponibilidad
- Las exigencias de los procesos de negocio.
- La dependencia en las TICs.
- El costo de la no disponibilidad de un servicio.
- Los tiempos de recuperación del servicio.
- Las regulaciones sobre operaciones 100% automáticas.
- El precio de la alta disponibilidad.
- El usuario no percibe la falla.
- El proceso continua su normal flujo.
- La recuperación es un proceso interno.
- Se requiere de redundancia.
- A mayor redundancia mayor costo en administración, implementación y mantenimiento.
- Un plan de contingencia no se considera alta disponibilidad.

## Hardware redundante
Se usa para hacer respaldos, no sólo en discos duros, también puede ser en fuentes de poder ya que si una se quema la otra puede entrar en respaldo.

## Redundancia en redes
Por ejemplo un Firewall puede tener redundancia de salida a internet, enrutadores y switches.

## Redundancia en software
Se pueden replicar, tener balanceadores de carga de solicitudes HTTP, un claro ejemplo sería tener 2 bases de datos donde una de las bases de datos sería un nodo pasivo que replica información y si falla la base de datos 1 activar instantáneamente la base de datos 2.

## Redundancia en bases de datos
- Múltiples nodos.
- Puede existir el balanceo de carga.
- El balanceo de carga contribuye al buen **performance**.
- Replicación en **tiempo real**. Cuidado con las inconsistencias => Se afecta la integridad de la información.

## Conclusiones
- Alta disponibilidad no es equivalente a un plan de contingencia.
- La alta disponibilidad tiene un costo, tan alto como tan exigente y crítico sea el servicio implicado.
- El balanceo de carga permite optimizar el uso de recursos de hardware.