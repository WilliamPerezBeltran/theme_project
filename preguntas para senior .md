# Preguntas de Entrevista para Python Senior (De mayor a menor nivel)

## 🏆 Nivel Alto – Diseño y Arquitectura
- ¿Cómo diseñarías un *data pipeline* a gran escala en Python para procesar millones de registros al día?
- ¿Cómo manejar la concurrencia en Python para tareas CPU-bound vs I/O-bound?
- ¿Cómo optimizarías un servicio web en Python que es lento bajo alta carga?
- Si tuvieras que almacenar 1TB de logs en JSON y consultarlos eficientemente en Python, ¿cómo lo harías?
- Diferencias y trade-offs entre usar *multithreading*, *multiprocessing* y *async* en Python.
- ¿Cómo perfilarías (*profile*) una aplicación de Python para encontrar cuellos de botella?

## ⚙️ Nivel Medio – Dominio Avanzado del Lenguaje
- Explica el GIL (*Global Interpreter Lock*) de Python. ¿Cómo afecta a los programas multi-hilo?
- ¿Cómo funciona el recolector de basura (*garbage collector*) en Python? ¿Cuándo sería necesario gestionar la memoria manualmente?
- Explica cómo funcionan los *iteradores* y *generadores* en Python. ¿En qué se diferencia `yield` de `return`?
- ¿Cuándo usarías `functools.lru_cache`? ¿Qué ventajas y desventajas tiene?
- Diferencia entre objetos mutables e inmutables en Python, y cómo esto afecta el paso de parámetros a funciones.
- Diferencias entre `@staticmethod`, `@classmethod` y métodos de instancia.
- ¿Cómo funcionan internamente los *context managers* en Python? Muestra un ejemplo con `__enter__` y `__exit__`.
- ¿Cuál es la diferencia entre una *deep copy* y una *shallow copy* en Python? Da ejemplos.

## 🔧 Nivel Bajo – Resolución de Problemas y Ejercicios
- Dado un archivo grande (por ejemplo, un CSV de 10GB), ¿cómo lo leerías y procesarías en Python sin quedarte sin memoria?
- Escribe una función que fusione dos listas ordenadas sin usar funciones de ordenamiento integradas.
- ¿Cómo implementarías un decorador personalizado que reintente una función hasta N veces si falla?
- Implementa un *rate limiter* en Python para limitar llamadas a una API.
- Dado un diccionario anidado, conviértelo en un diccionario de un solo nivel con claves separadas por puntos.
- Escribe una función que detecte dependencias circulares en un grafo dirigido.

