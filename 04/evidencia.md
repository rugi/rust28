# Evidencia
## Código con lo solicitado

### Creación del proyecto
```console
cargo new session04_variables
cd session04_variables
```

Abrimos VScode
```console
code .
```

Codificamos:

```rust
fn main() {
    // Declarar variables
    let nombre = "Isaac";
    let edad = 46;
    let peso : f32 = 130.5;    
    print!("Me llamo {} y tengo {} años y peso {} kilos.", nombre, edad, peso);
    // Valores mutables
    let mut contador = 0;
    contador += 1;
    println!("Contador:{}", contador);
    // Usar constantes
    const PI: f64 = 3.14;
    const E: f64  = 3.14;
    // Distintos tipos primitivos
    let altura: f32   = 1.77;
    let activo: bool  = true;
    let inicial: char = 'I';
    let saludo: &str  = "Hola!" ;
    // Todo Junto:
    println!("Nombre :{}", nombre);
    println!("Edad   :{}", edad);
    println!("Peso   :{} kg", peso);
    println!("Altura :{} cm", altura);
    println!("Activo :{} ", activo);
    println!("Inicial :{} ", inicial);
}
```
