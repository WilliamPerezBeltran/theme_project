
# 📌 Diferencia entre *Persona y &Persona{...}

## 1. *Persona
Esto es un tipo, no un valor.

Significa: "puntero a Persona".

Ejemplo: una función puede retornar *Persona, o una variable puede tener tipo *Persona.

```go
func NewPersona(...) *Persona {
    ...
}
```
→ Aquí decimos que la función devuelve un puntero a una Persona, o sea, una dirección de memoria que apunta a una Persona.

## 2. &Persona{...}
Esto es un valor concreto.

Significa: "crea una instancia de Persona y devuelve su dirección de memoria".

Es decir, &Persona{...} devuelve un *Persona.

```go
return &Persona{
    Id:   id,
    Name: name,
}
```
→ Aquí se está creando una estructura y devolviendo su puntero, no una desreferenciación.

## ❌ ¿Qué NO hace esto?
Esto no desreferencia nada.

Desreferenciar sería hacer *p si p es un puntero.

## ✅ Conclusión clara
Cuando usas:

```go
func NewPersona(...) *Persona {
    return &Persona{...}
}
```
→ La función retorna un *Persona  
→ &Persona{...} crea la instancia y retorna su dirección de memoria  
→ NO se está desreferenciando nada, se está retornando un puntero
