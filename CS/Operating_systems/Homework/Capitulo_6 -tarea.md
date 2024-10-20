>[!NOTE]
>[Tarea del capítulo seis del curso de sistemas operativos de la carrera de Informática Administrativa en UNAH-VS]

# Capítulo seis. Concurrencia. Interbloqueo e Inanición
## Términos clave

**1. Algoritmo del Banquero:**
Método utilizado en sistemas operativos para evitar el **interbloqueo (deadlock)**. Consiste en simular el comportamiento de un banquero que debe decidir si otorga o no préstamos a diferentes clientes (procesos), basándose en la disponibilidad de recursos (dinero) y en la certeza de que los préstamos solicitados podrán ser devueltos sin riesgo de insolvencia (deadlock).

**2. Barrera de Memoria**
(en inglés, memory barrier o memory fence) es una instrucción utilizada en sistemas multiprocesador para controlar el **orden de ejecución y visibilidad** de operaciones de memoria. Su propósito es asegurar que las lecturas y escrituras de memoria ocurran en un orden específico, garantizando la coherencia entre los diferentes hilos o procesos que comparten memoria.

**3. Cerrojo Cíclico**
Es una **primitiva de sincronización** utilizada en programación concurrente. Permite que un conjunto de hilos o procesos se sincronicen en fases de ejecución, es decir, esperan mutuamente hasta que todos alcancen un punto de encuentro en el código. Una vez que todos los hilos participantes llegan a esa barrera, se liberan al mismo tiempo y pueden continuar hacia la siguiente fase.

**4. Detección del Interbloqueo**
(en inglés, deadlock detection) es un enfoque utilizado en sistemas operativos para identificar **si ha ocurrido un interbloqueo entre procesos o hilos**.