# Dudas
----
## ¿Hay operador ternario como en java?
La respuesta corta es: Rust no tiene un operador ternario como condición ? verdadero : falso en Java, porque no lo necesita.

## 🔍 ¿Por qué?
Porque en Rust if es una expresión, no solo una instrucción como en Java.

✅ Ejemplo en Java

```java
String mensaje = (edad >= 18) ? "Mayor" : "Menor";
```

✅ Equivalente idiomático en Rust

```rust
let mensaje = if edad >= 18 { "Mayor" } else { "Menor" };
```

🔸 Este if:

* Devuelve un valor.
* Puede ser usado directamente en una asignación
* No requiere ternario

## 📌 Reglas clave
* Ambos bloques (then y else) deben devolver el mismo tipo

```rust
let x = if true { 10 } else { 20 }; // OK (i32 ambos)
let y = if true { "sí" } else { "no" }; // OK (&str ambos)
```

* Si omites el else, el valor es () (unit):

```rust
let r = if true { 5 }; // r: () → probablemente no lo que querías
```

## 🧠 ¿Y si quieres algo más compacto?
Puedes usar if como expresión en cualquier lugar:

```rust
println!("{}", if edad >= 18 { "Mayor" } else { "Menor" });
```
## 🦀 Conclusión
No existe cond ? x : y en Rust porque el lenguaje ya te permite hacer eso de forma más clara con if como expresión.

---
