                    ┌─────────────────────────┐
                    │   Programación Funcional │
                    └─────────────────────────┘
                              │
    ┌─────────────────────────┼─────────────────────────┐
    │                         │                         │
Funciones de Orden Superior   Funciones Anónimas         Inmutabilidad
    │                         (lambda)                   │
    │                                                   │
- map(func, iterable)         lambda x: x**2            - tuple
- filter(func, iterable)      lambda a, b: a + b        - frozenset
- sorted(..., key=func)                                   - namedtuple (read-only)
- any(), all(), max(), min() 
- Propias funciones que
  reciben/devuelven funciones

    ┌──────────────────────────────────────────────────────────────┐
    │                          functools                           │
    └──────────────────────────────────────────────────────────────┘
    - reduce(func, iterable)
    - partial(func, *args)   → Currying
    - lru_cache               → Memoización
    - wraps                   → Decoradores limpios

    ┌──────────────────────────────────────────────────────────────┐
    │                           itertools                           │
    └──────────────────────────────────────────────────────────────┘
    - chain, cycle, repeat
    - islice, tee, starmap
    - combinations, permutations
    - groupby

    ┌──────────────────────────────────────────────────────────────┐
    │                  Expresiones y Generadores                   │
    └──────────────────────────────────────────────────────────────┘
    - List comprehension: [x**2 for x in data]
    - Generator expression: (x**2 for x in data)
    - Set comprehension, Dict comprehension

    ┌──────────────────────────────────────────────────────────────┐
    │                Funciones Puras y Composición                  │
    └──────────────────────────────────────────────────────────────┘
    - Sin efectos secundarios
    - Siempre mismo output para mismo input
    - Composición manual: f(g(h(x)))
    - Librerías: toolz, fn.py

