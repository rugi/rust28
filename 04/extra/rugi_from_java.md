# Notas extras de @rugi, lenguaje origen: java.
📊 Tipos de datos primitivos en Rust
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
