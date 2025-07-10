# Session 4. Actividades.
## 🎯 Objetivo general
Dominar la sintaxis básica para declarar y usar:

* Variables (let)

* Mutabilidad (mut)

* Constantes (const)

* Tipos primitivos (números, booleanos, cadenas, caracteres)

* Inferencia de tipos

Con esto, empezarás a escribir código que usa datos, realiza operaciones simples y aplica buenas prácticas del lenguaje.

## ✅ Actividades detalladas
1. 🧪 Crear un nuevo proyecto llamado semana04_variables

```rust
cargo new session04_variables
cd session04_variables
```
Si ya tienes instalado Visual Code, puedes abrir el proyecto desde la linea de comandos con:

```console
code .
```

## 2. ✍ Declarar variables con let
Ejemplo:

```rust
fn main() {
    let nombre = "Isaac";
    let edad = 35;
    println!("Me llamo {} y tengo {} años", nombre, edad);
}
```

💡 Rust infiere tipos automáticamente, pero también puedes declararlos explícitamente:

```rust
let peso: f32 = 70.5;
```

## 3. 🔁 Probar mutabilidad
Rust no permite cambiar valores si no declaras mut:

```rust
fn main() {
    let mut contador = 0;
    contador += 1;
    println!("Contador: {}", contador);
}
```

💥 Si quitas mut, verás un error del compilador. ¡Pruébalo a propósito!

## 4. 🔒 Usar const para valores fijos
Se declara con tipo obligatorio y en mayúsculas por convención:

```rust
const PI: f64 = 3.1416;
```

💡 Intenta hacer PI = 5.0; y verás cómo Rust lo prohíbe con firmeza.

## 5. 📚 Usar distintos tipos primitivos
En tu main, crea variables de cada tipo:

```rust
let edad: u8 = 30;
let altura: f32 = 1.75;
let activo: bool = true;
let inicial: char = 'I';
let saludo: &str = "¡Hola!";
```

💡 También puedes hacer operaciones simples:

```rust
let resultado = edad as f32 * altura;
```
🎯 ## Mini reto final (opcional)

Haz un programa que imprima una ficha personal:

```rust
Nombre: Isaac
Edad: 35
Peso: 70.5 kg
Altura: 1.75 m
Activo: true
Inicial: I
```

Usa let, mut, const, al menos 3 tipos primitivos y una operación matemática.

📋 ## Checklist de validación – Semana 4
| Item |
| --- |
| [ ] Creé el proyecto semana04_variables	| 
| [ ] Declaré variables con let, con y sin tipo	| 
| [ ] Probé mut y vi el error al omitirlo	| 
| [ ] Usé una const y verifiqué que no se puede cambiar	| 
| [ ] Declaré variables de tipo: u8, f32, bool, char, &str	| 
| [ ] Hice al menos una operación matemática entre variables	| 
| [ ] Ejecuté cargo run y validé la salida	| 
| [ ] (Opcional) Completé el reto de la ficha personal	| 
