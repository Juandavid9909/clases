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

# Proyecto

## Parte 1
### Base de datos maestro-esclavo
Primero que todo es necesario crear una base de datos en el servidor que se encargará de ejecutar el rol maestro, hecho esto creamos una tabla con un registro. Finalizado este proceso debemos irnos a la pantalla principal de phpMyAdmin, seleccionar replicación y dar en configurar en la opción de maestro, seleccionamos si queremos hacer la replicación sólo a una base de datos o hacerla a todas ignorando una en específico, seleccionamos nuestra base de datos maestro y copiamos las configuraciones que nos indica XAMPP, esto para modificar el archivo my.cnf y pegamos dichas instrucciones.

El siguiente paso es crear un usuario, para ello regresamos a la pantalla de replicación, y agregamos un usuario con el siguiente comando:

```
CREATE USER 'nombre'@'IP esclavo' IDENTIFIED BY 'password';
GRANT REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'nombre'@'IP esclavo' IDENTIFIED BY 'password';
```

Ahora tendremos que darle las instrucciones para que la tabla replique los datos completamente en la tabla del esclavo.

```
USE bdMaestro;
FLUSH TABLES WITH READ LOCK;
```

Exportamos las tablas de nuestra base de datos maestro, para esto simplemente damos en exportar y continuar. A partir de este momento empezaremos a trabajar en nuestro servidor esclavo; como primer paso debemos importar el SQL que exportamos del servidor maestro. Iremos nuevamente a la opción replicación y en este momento configuraremos la replicación esclava, para ello simplemente damos clic en configurar, al mismo tiempo en el Control Panel damos en config (sección de MySQL) y abrimos my.ini, comentamos la línea que dice ```server-id = 1``` en la sección maestro y descomentamos la línea que dice ```server-id = 2``` en la sección esclavo agregando también el comando ```binlog_do_db = replica```.

Ahora ingresamos las credenciales del servidor maestro con el siguiente comando:
```
CHANGE MASTER TO
	MASTER_HOST = 'IP maestro',
	MASTER_USER = 'usuario maestro',
	MASTER_PASSWORD = 'password usuario maestro',
	MASTER_LOG_FILE = 'archivo mysql-bin que retorna cuando vemos el estado del maestro',
	MASTER_LOG_POS = (pos que retorna cuando vemos el estado del maestro (sin parentesis));
```

En este punto habremos creado el hilo SQL esclavo pero no se estará ejecutando hasta este momento, por lo que debemos ejecutar la instrucción ```START SLAVE``` o también desde la pantalla de replicación dar clic en controlar esclavo y dar en inicio completo.