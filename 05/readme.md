# 🎯 Objetivo general
Aprender a usar las estructuras de control de flujo en Rust para tomar decisiones y ejecutar bloques de código de forma condicional o repetitiva.

## 📌 Subtemas que cubrirás

* if, else, y expresiones condicionales

* match: patrón muy poderoso en Rust

* Bucles: loop, while, y for

* Uso de break, continue, y valores de retorno en bucles

* Control de flujo como expresiones (todo retorna algo en Rust)

## ✅ Actividades detalladas

### 1. ✴ if y else (condicional básica)

```rust
let edad = 20;

if edad >= 18 {
    println!("Mayor de edad");
} else {
    println!("Menor de edad");
}
```

💡 Puedes usar if como expresión:

```rust
let mensaje = if edad >= 18 { "Adulto" } else { "Menor" };
```

### 2. 🔁 loop (bucle infinito controlado)

```rust
let mut contador = 0;

loop {
    println!("Contador: {}", contador);
    contador += 1;
    if contador == 3 {
        break;
    }
}
```

💡 loop puede retornar valores:

```rust
let resultado = loop {
    if contador == 3 {
        break contador * 2;
    }
};
```

### 3. 🔄 while

```rust
let mut n = 0;
while n < 5 {
    println!("n = {}", n);
    n += 1;
}
```


#### 4. 🔂 for con rangos y colecciones

```rust
for i in 1..=5 {
    println!("i = {}", i);
}
```

💡 También puedes iterar sobre arrays:

```rust
let frutas = ["manzana", "banana", "uva"];
for fruta in frutas.iter() {
    println!("{}", fruta);
}
```

### 5. 🎯 match (control de flujo por patrones)

```
let nota = 8;

match nota {
    10 => println!("Excelente"),
    7..=9 => println!("Bien"),
    0..=6 => println!("Necesita mejorar"),
    _ => println!("Nota inválida"),
}
```

💡 Puedes usar match como expresión:

```rust
let resultado = match nota {
    10 => "Perfecto",
    7..=9 => "Satisfactorio",
    _ => "Reprobado",
};
```

## 🧪 Mini reto (opcional)
Crea un programa que:

* Pida un número entre 1 y 10 (hardcoded si quieres)

* Imprima si es par o impar (if)

* Use un for para imprimir todos los múltiplos del número entre 1 y 50

* Use match para calificar el número (ej: 1–3: bajo, 4–7: medio, 8–10: alto)

## 📋 Checklist de validación – Session 5
|Ítem |	Estado|
| --- | ---|
| [ ] Usé if y else con condición booleana	 |  | 
| [ ] Asigné una variable usando un if como expresión		 |  | 
| [ ] Usé loop con break		 |  | 
| [ ] Usé loop que devuelve un valor con break		 |  | 
| [ ] Usé while con condición		 |  | 
| [ ] Usé for sobre un rango (1..=5)		 |  | 
| [ ] Usé for sobre una colección (ej: array)		 |  | 
| [ ] Usé match con patrones de rango y valor		 |  | 
| [ ] Asigné una variable usando un match como expresión		 |  | 
| [ ] (Opcional) Resolví el mini reto		 |  | 
