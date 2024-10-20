**1. ¿Cuándo ocurre un interbloqueo (deadlock)?**
: Ocurre cuando un conjunto de procesos está bloqueado porque cada uno
espera un recurso que está siendo retenido por otro proceso del grupo.

**2. ¿Qué recursos se introducen con el interbloqueo?**
: Con el interbloqueo se introducen dos tipos de recursos: **recursos
reutilizables** y **recursos consumibles**.

**3. ¿Cuáles son algunos ejemplos de recursos reutilizables?**
: La memoria, semáforos, impresoras, etc. Es importante destacar que estos
recursos **se pueden liberar y reasignar**.

4\. ¿Cuáles son algunos ejemplos de recursos reutilizables?

Señales o mensajes. Es importante destacar que estos **se consumen al
ser utilizados**.

5\. ¿Qué es el grafo de asignación de recursos?

Es una herramienta gráfica que representa las relaciones entre procesos
y recursos para detectar ciclos que pueden conducir a interbloqueos.

6\. ¿Cuáles son las condiciones para que ocurra un interbloqueo?

Para que ocurra un interbloqueo, tiene que cumplirse al menos una de las
siguientes condiciones:

-   Exclusión mutua

-   Retención y espera

-   Sin expropiación

-   Espera circular

7\. ¿Cuándo ocurre la exclusión mutua?

Ocurre cuando solo un proceso a la vez puede usar un recurso.

8\. ¿Cuándo ocurre la retención y espera?

Ocurre cuando un proceso mantiene recursos asignados mientras espera
otros.

9\. ¿Cuándo ocurre la condición "sin expropiación"?

Ocurre cuando los recursos no se pueden forzar a ser liberados.

10\. ¿Cuándo ocurre la espera circular?

Ocurre cuando existe una cadena de procesos donde cada proceso espera un
recurso que tiene el siguiente.

11\. ¿Qué tipos de estrategias existen para manejar los interbloqueos?

Las estrategias existentes para manejar los interbloqueos se pueden
clasificar en tres tipos:

-   Prevención del interbloqueo

-   Predicción del interbloqueo

-   Detección del interbloqueo

12\. ¿En qué consisten las estrategias de prevención del interbloqueo?

Las estrategias de prevención del interbloqueo consisten en evitar que
se cumplan las condiciones necesarias para un interbloqueo.

13\. ¿Cómo se puede prevenir una condición de exclusión mutua?

La exclusión mutua se puede prevenir evitando la necesidad de asignar
recursos en exclusiva siempre que sea posible.

14\. ¿Cómo se puede prevenir una condición de retención y espera?

Una condición de retención y espera se puede prevenir obligando a los
procesos a solicitar todos los recursos al inicio, evitando que acumulen
recursos.

15\. ¿Cómo se puede prevenir una condición de "sin expropiación"?

Una condición de "sin expropiación" puede evitarse haciendo posible la
devolución forzada de recursos.

16\. ¿Cómo se puede prevenir una condición de espera circular?

Una condición de espera circular puede prevenirse asignando un orden
jerárquico a los recursos, de forma que los procesos solo puedan pedir
recursos siguiendo ese orden, evitando ciclos.

17\. ¿En qué consisten las estrategias de predicción del interbloqueo?

Consisten en predecir la posibilidad de un interbloqueo antes de que
ocurra.

18\. ¿Cuáles son las estrategias principales para la predicción del
interbloqueo?

Las dos principales estrategias para la predicción del interbloqueo son:

-   Denegación de la iniciación del proceso

-   Denegación de asignación de recursos

19\. ¿Cómo funciona la denegación de la iniciación de procesos?

Un proceso solo comienza si es seguro que podrá completar su ejecución
sin interbloqueo.

20\. ¿Cómo funciona la denegación de asignación de recursos?

Si la asignación de un recurso puede causar un interbloqueo, se rechaza
la solicitud y el proceso debe esperar.

21\. ¿De dónde toma inspiración el enfoque de predicción del
interbloqueo?

Este enfoque se inspira en el algoritmo del banquero de **Dijkstra**,
que verifica si una asignación es segura antes de proceder.

22\. ¿En qué consisten las estrategias de detección del interbloqueo?

Estas estrategias se utilizan cuando no se pudo prevenir ni predecir un
interbloqueo. Consisten en detectar y recuperarse de un interbloqueo.

23\. ¿Cuál es la estrategia utilizada para detectar un interbloqueo?

Para detectar un interbloqueo se utiliza la estrategia denominada
**Algoritmo de detección del interbloqueo**.

24\. ¿Cómo funciona el algoritmo de detección del interbloqueo?

Funciona monitoreando el sistema en busca de ciclos en el grafo de
asignación de recursos, lo que indica un interbloqueo.

25\. ¿Qué estrategias se utilizan para recuperarse de un interbloqueo?

Para recuperarse de un interbloqueo se utilizan dos estrategias:

-   Abortar procesos

-   Liberar recursos

26\. ¿En qué consiste la estrategia de aborto de procesos?

Consiste en terminar algunos procesos para romper el ciclo de
interbloqueo.

27\. ¿En qué consiste la estrategia de liberación de recursos?

Consiste en expropiar recursos de ciertos procesos y reasignarlos.

28\. ¿Qué es la estrategia integrada de tratamiento del interbloqueo?

Es una estrategia propuesta por el autor, William Stallings, donde
propone combinar varias técnicas de detección, prevención y recuperación
en función de las necesidades del sistema.

29\. ¿Qué ejemplos hay de la estrategia integrada de tratamiento del
interbloqueo?

Se proponen dos ejemplos:

-   algunos sistemas **permiten interbloqueos temporalmente**, pero los
    detectan y recuperan rápidamente

-   Otros sistemas aplican políticas preventivas estrictas en
    operaciones críticas, evitando que los interbloqueos lleguen a
    ocurrir

30\. ¿Qué es la concurrencia?

La concurrencia es la capacidad de ejecutar múltiples tareas o procesos
de manera **simultánea**, permitiendo que varios programas o partes de
un programa avancen al mismo tiempo.

la concurrencia asegura que los procesos se **alternen rápidamente** en
su ejecución, generando la **ilusión de simultaneidad** en sistemas con
un solo procesador, y en sistemas con múltiples núcleos, algunos
procesos realmente se ejecutan en paralelo.

31\. ¿Qué es el paralelismo?

El paralelismo es la capacidad de un sistema para ejecutar múltiples
tareas de manera simultánea, utilizando varios procesadores o núcleos a
la vez.

32\. ¿Cuál es la diferencia entre paralelismo y concurrencia?

El paralelismo implica que varios procesos o hilos se ejecuten al mismo
tiempo, en distintas **unidades de procesamiento**. En la concurrencia,
los procesos se alternan rápidamente en un solo núcleo.

33\. Explique el problema de los filósofos comenzales.

Este es un **problema clásico de concurrencia**, utilizado para ilustrar
los retos relacionados con el acceso simultáneo a recursos compartidos.
En este problema, un grupo de filósofos se sienta a cenar con palillos
entre ellos, y cada filósofo necesita dos palillos para comer. El
problema radica en cómo evitar que los filósofos queden bloqueados
esperando palillos (interbloqueo) o que alguno no coma nunca
(inanición).

34\. ¿Qué soluciones se pueden dar al problema de los filósofos
comensales?

Se proponen dos soluciones con distintos métodos:

-   **Semáforos**: Se utilizan semáforos para controlar la toma de los
    palillos de forma que se evite el interbloqueo.

-   **Monitor**: Un monitor es una abstracción que permite coordinar el
    acceso a los palillos y asegura que ningún filósofo pase hambre
    (evitando la inanición).
