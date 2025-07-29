## 🎯Objetivo general

Comprender y aplicar los conceptos fundamentales de:

* Ownership (propiedad de datos).
* Moves (movimiento de valores).
* Copy types vs non-Copy types.
* Borrowing inmutable (&T).
* Reglas básicas del borrow checker.

Esto te permitirá *entender por qué Rust no necesita un garbage collector* y cómo garantiza seguridad de memoria en *tiempo de compilación*.

## 📌 Subtemas que cubriremos esta session.

### 1. 🔐 Ownership (propiedad única)

* Cada valor en Rust tiene un "owner".
* Solo un owner a la vez.
* El valor se libera cuando su owner sale de scope.

Ejemplo:

```rust
let s1 = String::from("Hola");
let s2 = s1; // s1 ya no es válido
```

### 2. 🔄 Move vs Copy

* Tipos como String, Vec, Box se mueven.
* Tipos como i32, bool, char se copian automáticamente.

```rust
let x = 10;
let y = x; // x aún es válido porque i32 implementa Copy

let a = String::from("Rust");
let b = a; // a ya no es válido
```

### 3. 📤 Borrowing inmutable (&T) 

* Puedes "prestar" un valor sin moverlo.
* Puedes tener múltiples préstamos inmutables al mismo tiempo.

```rust
let s = String::from("dato");
let ref1 = &s;
let ref2 = &s;
println!("{}, {}", ref1, ref2);
```

### 4. ❌ Errores comunes

* Usar una variable después de moverla.
* Intentar tener referencias mutables e inmutables al mismo tiempo.

### ✅ Actividades sugeridas

🧪 Crea un proyecto session06_ownership
1. Escribe un ejemplo de movimiento de String y observa el error si intentas usar la variable original.
2. Escribe un ejemplo con i32 y demuestra que no hay problema con las copias.
3. Crea una función que reciba un String como argumento → observa cómo se transfiere la propiedad.
4. Crea otra función que reciba &String → muestra cómo se evita el move.
5. Prueba tener múltiples referencias inmutables al mismo valor y verifica que es válido.
6. Intenta tener una mutable e inmutable al mismo tiempo → observa el error del compilador.

### 📋 Checklist de validación – Session 06


|Ítem	| Estado|
|---|---|
| [ ] | Probé mover un String y observé el error al usar la variable original	|
| [ ] | Usé un tipo Copy (i32, bool) y confirmé que no genera error al copiar	|
| [ ] | Hice una función que toma propiedad (String)	|
| [ ] | Hice una función que toma préstamo (&String)	|
| [ ] | Usé múltiples referencias inmutables sin error	|
| [ ] | Intenté mezclar mutables e inmutables y vi el error del compilador	|
| [ ] | Entendí que Rust mueve o presta, nunca copia implícitamente en tipos complejos|
