## Evidencia.

## Creación del proyecto

```console
cargo new session05_controldeflujo
cd session05_controldeflujo
```

Abrimos VScode
```console
code .
```

## Código

```rust
// Tuve que agregarlo para poder leer de consola,
// de momento solo replique un ejemplo que vi, en posteriores semanas,
// veremos a detalle el tema.
use std::io;


fn main() {    
    // Para la lectura del numero, revisé ejemplos y encontrè esta forma.
    // muy limpia por cierto.
    println!("Introduce un número:");

    let mut numero_str = String::new();

    io::stdin()
        .read_line(&mut numero_str)
        .expect("Error al leer la línea");

    let numero: i32 = numero_str
        .trim()
        .parse()
        .expect("No ingresaste un número válido");

    println!("Hola, el número es: {}", numero);
    // Acá ya tenemos el número en: numero.
    // no dejaremos que avance el 0 o menor y mayor a 10
    if numero <= 0 || numero > 10 {
        println!("Debe ser un numero que vaya de 1 a 10.");
        return;
    }    
    // Para saber si es par, usamos la vieja confiable: numero % 2
    let modulo = numero % 2;
    if modulo==0 {
        println!("{} es par. ", numero);
    }else{
        println!("{} es impar. ", numero);
    }
    //Ahora el for
    for i in 1..=50{
        if i % numero == 0 {
            println!("{}", i);
        }
    }
    // Por ultimo el match
    match numero {
        8..=10 => println!("alto"),
        4..=7 => println!("medio"),
        1..=3 => println!("bajo"),
        _ => println!("Nota inválida"),
    }    
}
```
