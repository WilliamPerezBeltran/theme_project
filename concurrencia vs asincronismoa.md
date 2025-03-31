# Concurrencia vs. Asincronismo

## Definiciones

### Concurrencia 🏃‍♂️🏃‍♀️
- Capacidad de un sistema para manejar **múltiples tareas al mismo tiempo**, pero **no necesariamente ejecutándolas en paralelo**.
- Se logra con **hilos (threads), procesos o corutinas**.
- Un solo procesador puede **intercalar** la ejecución de tareas (conmutación de contexto).
- **Ejemplo en Go:** Usar **goroutines** para manejar múltiples conexiones de red sin bloquear el programa.

### Asincronismo ⏳
- Ejecución de tareas **sin bloquear el flujo principal**, permitiendo que el sistema haga otras cosas mientras espera una respuesta.
- Se basa en **callbacks, promesas o async/await**.
- No requiere múltiples hilos, se puede lograr con un solo hilo y eventos (ejemplo: Node.js con el Event Loop).
- **Ejemplo en JavaScript:** Realizar una **llamada fetch()** sin detener la ejecución del código.

## Ejemplo práctico 🎭

### Restaurante 🍽️
- **Concurrencia:** Hay varios cocineros preparando diferentes platos al mismo tiempo.
- **Asincronismo:** Un solo cocinero mete un plato al horno y, en lugar de esperar, sigue cocinando otros platos hasta que el horno le avise que el plato está listo.

## Resumen 📌
- **Concurrencia** = Manejo de múltiples tareas (paralelo o alternado).
- **Asincronismo** = No bloquear ejecución mientras se espera un resultado.

# Concurrencia vs. Asincronismo vs. Procesos vs. Hilos vs. Paralelismo

## Definiciones

### Concurrencia 🏃‍♂️🏃‍♀️
- Capacidad de un sistema para manejar **múltiples tareas al mismo tiempo**, pero **no necesariamente ejecutándolas en paralelo**.
- Se logra con **hilos (threads), procesos o corutinas**.
- Un solo procesador puede **intercalar** la ejecución de tareas (conmutación de contexto).
- **Ejemplo:** Un restaurante con varios cocineros preparando diferentes platos al mismo tiempo.

### Asincronismo ⏳
- Ejecución de tareas **sin bloquear el flujo principal**, permitiendo que el sistema haga otras cosas mientras espera una respuesta.
- Se basa en **callbacks, promesas o async/await**.
- No requiere múltiples hilos, se puede lograr con un solo hilo y eventos (ejemplo: Node.js con el Event Loop).
- **Ejemplo:** Un solo cocinero mete un plato al horno y, en lugar de esperar, sigue cocinando otros platos hasta que el horno le avise que el plato está listo.

### Proceso 🖥️
- Una instancia en ejecución de un programa.
- Tiene su propio espacio de memoria y recursos.
- Los procesos no comparten memoria entre sí, por lo que se comunican mediante mecanismos como IPC (Inter-Process Communication).
- **Ejemplo:** Un restaurante con diferentes estaciones de cocina independientes, cada una funcionando como un proceso separado (panadería, parrilla, ensaladas).

### Hilo (Thread) 🧵
- Una unidad de ejecución dentro de un proceso.
- Comparte memoria y recursos con otros hilos del mismo proceso.
- Permite dividir un proceso en tareas más pequeñas que se ejecutan en paralelo o concurrentemente.
- **Ejemplo:** Dentro de una estación de cocina, cada cocinero (hilo) se encarga de una parte de la preparación del plato.

### Paralelismo ⚡
- Ejecución de múltiples tareas **simultáneamente** en múltiples procesadores o núcleos.
- Requiere hardware con múltiples núcleos para ejecutar tareas en paralelo sin conmutación de contexto.
- **Ejemplo:** Un restaurante con varios cocineros, cada uno con su propia cocina, preparando diferentes platos exactamente al mismo tiempo.

## Resumen 📌
- **Concurrencia** = Manejo de múltiples tareas (paralelo o alternado).
- **Asincronismo** = No bloquear ejecución mientras se espera un resultado.
- **Proceso** = Programa en ejecución con su propia memoria.
- **Hilo** = Subtarea dentro de un proceso que comparte recursos.
- **Paralelismo** = Ejecución simultánea de múltiples tareas en hardware multicore.


