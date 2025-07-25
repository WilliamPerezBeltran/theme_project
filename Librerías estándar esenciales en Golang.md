# 📚 Librerías estándar esenciales en Golang

Una lista compacta de los paquetes de la librería estándar que **todo desarrollador Go debería conocer** para trabajar con confianza en CLI, APIs, sistemas backend y más.

---

## 🔧 Paquetes clave

| Paquete         | Descripción                                                                 | Ejemplos clave                                     |
|------------------|-----------------------------------------------------------------------------|----------------------------------------------------|
| `os`             | Manejo de archivos, procesos, entorno                                      | `os.Open`, `os.Create`, `os.Remove`, `os.Getenv`   |
| `io` / `os.ReadFile` | Lectura y escritura de streams y archivos                            | `io.Copy`, `ReadAll`, `WriteFile`                  |
| `fmt`            | Impresión y formateo de texto                                              | `fmt.Println`, `Printf`, `Sprintf`                 |
| `errors`         | Manejo y creación de errores personalizados                                | `errors.New`, `fmt.Errorf`                         |
| `encoding/json`  | Codificación y decodificación JSON                                         | `json.Marshal`, `json.Unmarshal`                   |
| `net/http`       | Servidores y clientes HTTP                                                 | `http.ListenAndServe`, `http.Get`                  |
| `time`           | Manipulación de fechas y tiempos                                           | `time.Now`, `time.Sleep`, `time.Parse`             |
| `strings`        | Operaciones con strings                                                    | `Split`, `Contains`, `Replace`, `ToUpper`          |
| `strconv`        | Conversión entre strings y tipos numéricos                                | `Atoi`, `Itoa`, `ParseFloat`                       |
| `context`        | Control de cancelación y timeout de operaciones concurrentes              | `context.WithCancel`, `WithTimeout`                |
| `sync`           | Control de concurrencia: mutexes, wait groups                             | `sync.Mutex`, `sync.WaitGroup`                     |
| `sync/atomic`    | Operaciones atómicas para concurrencia segura                             | `atomic.AddInt32`, `atomic.LoadInt64`              |

---

## 🧁 Bonus útiles

| Paquete         | Descripción                                        | Ejemplos clave                    |
|------------------|----------------------------------------------------|-----------------------------------|
| `log`            | Logging básico                                      | `log.Println`, `log.Fatal`        |
| `math/rand`      | Generación de números aleatorios                   | `rand.Intn`, `rand.Seed`          |
| `path/filepath`  | Manipulación de rutas en sistemas de archivos     | `filepath.Join`, `filepath.Ext`   |
| `regexp`         | Expresiones regulares                             | `regexp.MatchString`, `FindAll`   |

---

> ⚡ Sugerencia: Dominar estos paquetes te permitirá resolver el 90% de los problemas comunes sin usar librerías externas.


