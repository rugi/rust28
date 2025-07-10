# Notas extras de @rugi, lenguaje origen: java.
-------

## 📊 Tipos de datos primitivos en Rust
|Tipo de dato|	Sintaxis	| Rango de valores	| Ejemplos|
| --- | ---- | -----| ---- |
|Enteros con signo | ``` i8, i16, i32, i64, i128, isize ```|	-2ⁿ⁻¹ a 2ⁿ⁻¹ - 1	 | ``` let x: i8 = -120; let y: i32 = 100000;  let z: isize = -1; ``` |
|Enteros sin signo | ``` u8, u16, u32, u64, u128, usize  ``` |	0 a 2ⁿ - 1 |```	let a: u8 = 255; let b: u32 = 1_000_000; let c: usize = 42; ``` |
|Punto flotante | ``` f32, f64 |	IEEE-754: ±~10³⁸ (f32), ±~10³⁰⁸ (f64)  ``` |```	let pi: f64 = 3.1416; let temp: f32 = -15.5; let e: f64 = 2.71828; ``` |
|Booleano |	bool |	 ``` true, false  ``` | ```	let activo: bool = true; let apagado = false; let resultado = 5 > 2; ``` |
|Carácter Unicode |	 ``` char  ``` | Un solo caracter Unicode de 4 bytes | ``` let letra: char = 'A'; let emoji: char = '🚀'; let simbolo = 'π'; ``` |
|Cadena de texto | ```  (&str)	&str  ``` |	Cadena inmutable UTF-8 | ``` let saludo = "Hola"; let mensaje = "🦀 Rust!"; let vacio = "";  ```|
|Tuplas | ``` (T1, T2, ...)	  ``` | Agrupación de tipos heterogéneos	| ``` let t = (42, true, "ok"); let coord = (3.5, 7.2); let solo = ('A',); ``` |
|Arrays |	``` [T; N]   ```|	Colección fija de elementos del mismo tipo | ``` let a = [1, 2, 3]; let b: [u8; 4] = [0; 4]; let c = ["L", "M", "X"];  ```|

-------

## ¿Existe el cast forzado como en java?

### ✔️ Sí, existe: se hace con as
Rust no tiene casting implícito entre tipos numéricos. Si quieres convertir un tipo a otro, debes hacerlo explícitamente con el operador:

```rust
let x: u8 = 42;
let y: f32 = x as f32;
```

🛠️ Sintaxis:

```rust
<valor> as <tipo_destino>
```

Ejemplo:
```rust
let edad: u8 = 30;
let edad_doble = edad as u16;
let promedio = edad as f32 / 2.0;
```

⚠️ Diferencias con Java

| Aspecto |	Java	| Rust |
| --- |----| ---- | 
| Cast implícito	| Permitido (ej. de int a long) |	❌ No permitido (siempre requiere as)|
| Cast explícito	 | (float) x	|x as f32|
| Verificación de desbordamiento |	Solo en tiempo de ejecución con wrappers|	❌ En Rust no falla en tiempo de compilación (pero puedes usar TryFrom o checked_*)|
| Seguridad	| Puede fallar silenciosamente (ej. overflow) |	Puedes optar por conversión segura (TryFrom, from, etc.) |

💥 Ejemplo de truncamiento (ojo con esto)

```rust
let grande: u16 = 1000;
let chico: u8 = grande as u8;  // pierde información
println!("{}", chico);         // imprime: 232
```

Porque 1000 mod 256 = 232. ¡Rust lo permite, pero tú eres responsable!

✅ Alternativas más seguras

* u8::try_from(1000) devuelve Err(...)
* i32::from(u8_var) es más claro y más seguro cuando el rango es seguro

```rust
use std::convert::TryFrom;

let x: u16 = 1000;
match u8::try_from(x) {
    Ok(val) => println!("Valor convertido: {}", val),
    Err(_) => println!("¡No se puede convertir sin pérdida!"),
}
```

🦀 Conclusión

| En Rust	| Equivalente Java| 
|  --- | ---- |  
| x as T	 |  (T) x | 
| T::from(x)	|  new T(x) | 
| T::try_from(x) | 	conversión con validación manual | 

----

Rust no lanza una excepción por desbordamiento en tiempo de ejecución en modo release, pero sí puede “reiniciar” el valor por diseño mediante una técnica llamada "wrapping", es decir, el valor se desborda de forma controlada, como tú bien mencionas.

⚙️ ¿Qué pasa en Rust cuando un entero se desborda?
🧪 En modo debug (cargo run)
Rust detecta el overflow y detiene el programa con un panic!

Ejemplo:

```rust 
let x: u8 = 255;
let y = x + 1; // panic en modo debug
```

🚀 En modo release (cargo build --release)
Rust NO lanza error. El valor simplemente se desborda (wrap-around)

```rust
let x: u8 = 255;
let y = x + 1; // y = 0

💡 Esto ocurre por razones de performance y compatibilidad con comportamiento de bajo nivel.


🛠️ Formas explícitas de desbordar (si lo deseas):

1. 🔁 wrapping_*()

```rust
let x: u8 = 255;
let y = x.wrapping_add(1); // y = 0
```

2. 📏 checked_*() — para detectar overflow sin panic

```rust
let x: u8 = 255;
match x.checked_add(1) {
    Some(valor) => println!("Suma ok: {}", valor),
    None => println!("¡Overflow detectado!"),
}
```

3. ⛔ overflowing_*() — devuelve el resultado + un flag de overflow

```rust
let x: u8 = 255;
let (resultado, overflow) = x.overflowing_add(1);
println!("Resultado: {}, ¿overflow? {}", resultado, overflow);
// Resultado: 0, ¿overflow? true
```

📦 Comparativa de métodos para aritmética segura
|Método Rust |	Comportamiento |	Uso típico|
| --- | --- |
|wrapping_add()|	Desborda sin avisar (como C)|	Juegos, criptografía|
|checked_add()|	Devuelve None si hay overflow	|Seguridad y control|
|overflowing_add()|	Devuelve resultado y flag de overflow	|Bajo nivel|
|saturating_add()	|Fija al máximo valor permitido	| Contadores|
|+ (suma normal)	|Panic en modo debug, wrap en release	|General|
