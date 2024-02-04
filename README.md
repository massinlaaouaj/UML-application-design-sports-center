# UML Sports Center

<center>

![image](https://i.imgur.com/n95TuRA.png) 

</center>

<br>

## Descripción del proyecto

Diseñar una aplicación para gestionar un centro deportivo.

<br>

## Funcionamiento del negocio

### Socios

Los socios se identifican con NIF y tienen contraseña, dirección de correo, número de cuenta y tienen cuota mensual asociada que se calcula en función de los servicios del polideportivo que tienen suscritos. Los servicios a los que se pueden suscribir pueden ser el uso libre de alguna instalación del polideportivo (ej. piscina, gimnasio, etc.) o clases (ej. aeróbic) con un monitor. Las instalaciones tienen una descripción, capacidad máxima y horario de apertura semanal (que puede ser diferente todos los días, de lunes a domingo). Algunas instalaciones del gimnasio pueden tener máquinas de deporte asociadas (ej. cintas de correr, máquinas de spinning, etc.); las máquinas tienen identificador, nombre y número de unidades disponibles en aquella instalación (que puede ser diferente en cada instalación donde esté la misma máquina). Por otra parte, las clases con monitor pueden tener uno (y sólo un) monitor asignado (que se identifica con NIF y tiene nombre y teléfono de contacto), instalación donde se realiza cada una de las sesiones (máximo una diaria, con hora de inicio y de fin, que puede ser diferente cada día de la semana), fecha de inicio y fin de las clases, y número máximo de asistentes (el mismo en todas las sesiones). Todos los servicios tienen asociado un precio y un identificador. Las clases, además del precio total de todas las sesiones, tienen un precio unitario por sesión (en caso de que alguien no quiera ir a todas las sesiones, véase más abajo). 

Los socios pueden consultar la lista de servicios que tienen suscritos y, si lo desean, darse de baja de alguno. También pueden consultar los servicios que ofrece el gimnasio y, opcionalmente, añadir alguno a su suscripción. En ambas consultas, el socio debe identificarse (con NIF y contraseña) y, en caso de hacer cualquier modificación, se actualiza la cuota de socio.


### Usuarios externos

Los usuarios externos no pagan cuota de socio ni están registrados en el sistema, pero pueden realizar reservas puntuales de los servicios del polideportivo; éstos incluyen clases puntuales (sesiones individuales en días concretos, no todas las sesiones de una clase) o acceso a una instalación durante un día entero. Para ello, primero seleccionan el tipo de servicio que quieren (instalación o sesión de una clase) y se les muestra un listado. Seleccionando uno se le muestran los horarios diarios del servicio y el precio de reserva (el precio de la instalación o el precio unitario de una sesión de la clase). Si selecciona un horario (uno día) y confirma la reserva, el sistema comprueba si hay plazas disponibles (consultando reservas previas ese día y los socios suscritos al servicio, y el número de plazas de la clase o capacidad de la instalación). Si hay plazas disponibles, se le pide que introduzca su NIF (que quedará asociado a su reserva), y se le muestra una confirmación. En caso de que no haya capacidad suficiente en una instalación se da un error y se devuelve al listado de selección. En caso de que no haya plazas en una clase, se le envía un mensaje al monitor asignado, quien considerará si es posible meter a un alumno más en la clase. En caso afirmativo, se realizará la reserva; en caso negativo, se informa al usuario y se devuelve al listado de selección. El pago se realiza en persona cuando se utiliza el servicio, así que no se guarda ninguna información bancaria.


### Administrativa

El administrativo puede dar de alta y baja socios y monitores; en las altas se introducen los datos correspondientes de cada uno, mientras que las bajas se realizan a partir del NIF. Cuando se hace un alta de un monitor se le asignará al menos una clase a impartir (puede ser más de una). La asignación de clases adicionales a monitor también se puede realizar más tarde, en cualquier momento. Cuando se hace una baja de un monitor, se debe desligar de todas las clases que imparte y, por cada una de ellas, seleccionarlas un sustituto. Durante este proceso, si se desea, también se puede dar de alta un nuevo monitor.


### Funciones automàticas del negocio

Cada primero de mes, un proceso automático se despierta y pide comprobar si los socios están al día de los pagos de las cuotas y esposa de baja aquellos que no lo están. Siempre que se da de baja un socio, tanto manual como automáticamente, éste recibe un mensaje informativo.

<br>

## Indice de contenido

- [Documentación técnica de los requisitos funcionales, y análisis del negocio](DocumentacionTecnicaRequisitosAnalisis/20230204_docTecnicaRequisitosYAnalisisNegocio_DOC.pdf)
- [Documentación técnica de los diseños de la interfaz de usuario, y diseño de las clases entidades](DocumentacionTecnicaInterfazDiseno/20230204_docTecnicaInterfazUsuarioDiseno_DOC.pdf)
