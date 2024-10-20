>[!NOTE]
>[Tarea del capítulo seis del curso de sistemas operativos de la carrera de Informática Administrativa en UNAH-VS]

# Capítulo seis. Concurrencia. Interbloqueo e Inanición
## Términos clave

**1. Algoritmo del Banquero**

Método utilizado en sistemas operativos para evitar el **interbloqueo (*deadlock*)**. Consiste en simular el comportamiento de un banquero que debe decidir si otorga o no préstamos a diferentes clientes (procesos), basándose en la disponibilidad de recursos (dinero) y en la certeza de que los préstamos solicitados podrán ser devueltos sin riesgo de insolvencia (*deadlock*).

**2. Barrera de Memoria**

(en inglés, *memory barrier* o *memory fence*) es una instrucción utilizada en sistemas multiprocesador para controlar el **orden de ejecución y visibilidad** de operaciones de memoria. Su propósito es asegurar que las lecturas y escrituras de memoria ocurran en un orden específico, garantizando la coherencia entre los diferentes hilos o procesos que comparten memoria.

**3. Cerrojo Cíclico**

Es una **primitiva de sincronización** utilizada en programación concurrente. Permite que un conjunto de hilos o procesos se sincronicen en fases de ejecución, es decir, esperan mutuamente hasta que todos alcancen un punto de encuentro en el código. Una vez que todos los hilos participantes llegan a esa barrera, se liberan al mismo tiempo y pueden continuar hacia la siguiente fase.

**4. Detección del Interbloqueo**

(en inglés, ***deadlock detection***) es un enfoque utilizado en sistemas operativos para identificar **si ha ocurrido un interbloqueo entre procesos o hilos**.

**5. Diagrama de Proceso Conjunto**

(en inglés, ***Process Communication Diagram*** o simplemente ***Interprocess Diagram***) es una **representación gráfica** utilizada en sistemas operativos para **visualizar la interacción y comunicación entre proceso**s que comparten recursos o se comunican mediante mecanismos específicos.

**6. Espera Circular**

(en inglés, ***circular wait***) es una condición que puede llevar a un interbloqueo en sistemas operativos. Se produce cuando varios procesos están esperando indefinidamente por recursos que están siendo retenidos por otros procesos en una **cadena o ciclo cerrado de dependencias**.

**7. Exclusión Mutua**

(en inglés, *mutual exclusion*) es un principio fundamental en la concurrencia y la gestión de recursos en sistemas operativos. Implica que **cuando un recurso crítico es accedido por un proceso**, ningún otro proceso puede acceder a ese recurso al mismo tiempo.

**8. Expropiación**

(en inglés, *preemption*) se refiere a la capacidad del sistema de interrumpir un proceso en ejecución y **reasignar los recursos que este está utilizando** a otro proceso.

**9. Grafo de Asignación de Recursos**

Es una representación gráfica utilizada en sistemas operativos para modelar la asignación y solicitud de recursos entre procesos. Este tipo de grafo ayuda a visualizar las relaciones entre procesos y recursos, permitiendo identificar posibles interbloqueos (deadlocks).

**10. Inanición**

(en inglés, *starvation*) ocurre cuando un proceso espera indefinidamente para acceder a los recursos necesarios para continuar su ejecución, debido a que **otros procesos con mayor prioridad acaparan esos recursos** de manera constante. Esto impide que el proceso afectado progrese, incluso si no existe un interbloqueo.

**11. Interbloqueo**

(en inglés, *deadlock*) es una situación en sistemas operativos donde dos o más procesos se encuentran **bloqueados indefinidamente** esperando recursos que están siendo retenidos por los otros procesos involucrados. Esto genera un ciclo de espera sin solución, impidiendo que los procesos avancen.

**12 Mensaje**

Un **mensaje** es una **unidad de datos** que un proceso envía a otro para intercambiar información y coordinar su ejecución.

**13. Predicción del Interbloqueo**

Es una técnica utilizada para anticipar si una secuencia de solicitudes de recursos puede llevar al sistema a un estado de interbloqueo. En lugar de esperar a que ocurra un interbloqueo y luego detectarlo, la predicción trata de evitarlo proactivamente al analizar el uso actual y futuro de los recursos.

**14. Prevención del interbloqueo**

La prevención del interbloqueo es una estrategia en sistemas operativos para **garantizar que un interbloqueo nunca pueda ocurrir**, impidiendo que se cumplan al menos una de las condiciones necesarias para que se produzca. Esta técnica introduce restricciones en la asignación de recursos y en el comportamiento de los procesos para evitar situaciones de interbloqueo.

**15. Recurso Consumible**

Un recurso consumible es aquel que **puede ser producido, consumido o destruido** por los procesos del sistema operativo. A diferencia de los recursos reutilizables, estos dejan de existir después de ser utilizados y no se pueden volver a asignar. Ej. Señales, mensajes e interrupciones.

**16. Recurso Reutilizable**

Un recurso reutilizable es aquel que puede ser **asignado a un proceso, liberado y luego reutilizado** por otro proceso sin perder su funcionalidad o valor. Ej. Memoria, núcleos de procesador, dispositivos de E/S, semáforos y mutexes.

**17. Retención y Espera**

Retención y espera son dos condiciones que pueden dar lugar a situaciones de interbloqueo en sistemas operativos. Juntas, son parte de las condiciones necesarias para que un interbloqueo ocurra.
- **Retención:**
Se refiere a la situación en la que un proceso **sostiene uno o más recursos** mientras espera por otros recursos que están siendo ocupados por otros procesos. Este comportamiento es común en sistemas operativos donde los procesos requieren múltiples recursos para completar su tarea.
- **Espera:**
Es la condición en la que un proceso **está esperando por uno o más recursos** que están actualmente asignados a otros procesos. La espera es un estado natural de los procesos en la ejecución, pero se convierte en un problema cuando se encuentra en una espera circular con otros procesos.

**18. Tubería**

Una **tubería** (o ***pipe*** en inglés) es un mecanismo de intercomunicación entre procesos que permite que la salida de un proceso se convierta en la entrada de otro.

## Cuestiones de Repaso

**1. Cite ejemplos de recursos reutilizables y consumibles.**

- **Recursos reutilizables**: memoria, impresoras, sistemas de archivos, sockets de red.
- **Recursos consumibles**: tiempo de CPU (ciclos de CPU), datos de entrada, mensajes en comunicación.

**2. ¿Cuáles son las tres condiciones que deben cumplirse para que sea posible un interbloqueo?**

1. Exclusión mutua
2. Retención y espera
3. Espera circular

**3. ¿Cuáles son las cuatro condiciones que producen un interbloqueo?**

1.	Exclusión mutua
2.	Retención y espera
3.	Espera circular
4.	No preemción

**4. ¿Cómo se puede prever la condición de retención y espera?**

Se pueden utilizar diferentes estrategias. Entre estas destacan:

- No permitir que un proceso retenga recursos mientras espera.
- Requerir que los procesos soliciten todos los recursos que necesitan al inicio.
- Usar estrategias de asignación que limiten la retención y espera, como FIFO.
- Implementar mecanismos de sincronización como monitores y semáforos.

**5. Enumere dos maneras cómo se puede prever la condición de sin expropiación.**

1. Permitiendo la expropiación de recursos.
2. Obligando a los procesos a solicitar todos los recursos necesarios al inicio de su ejecución.

**6. ¿Cómo se puede prever la condición de espera circular?**

- Asignando recursos según un orden predefinido.
- Permitiendo que los procesos liberen recursos antes de solicitar otros.
- Implementando un protocolo que verifique la posibilidad de ciclos.

**7. ¿Cuál es la diferencia entre predicción, detección y prevención del interbloqueo?**

- **Prevención**: Establece políticas y condiciones para evitar que ocurra el interbloqueo desde el inicio.
- **Detección**: Identifica si un interbloqueo ya ha ocurrido en el sistema mediante monitoreo y análisis.
- **Predicción**: Anticipa la posibilidad de interbloqueo basándose en modelos y análisis de patrones antes de que suceda.

