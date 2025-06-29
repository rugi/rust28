# Rust
## Session 1. Actividades.

🎯 Objetivo del día
✅ Instalar Rust usando rustup.
✅ Tener un toolchain estable funcionando.
✅ Entender y usar cargo y rustc para compilar y ejecutar un programa simple.

🛠 PASO 1: Instalar rustup
📌 Comando (Linux / macOS / WSL / Windows PowerShell):
 
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

O en Windows (PowerShell):

powershell
 
    Invoke-WebRequest -Uri https://win.rustup.rs -OutFile rustup-init.exe; .\rustup-init.exe

👉 Sigue el asistente (elige default).

💡 Reinicia tu terminal tras instalar, o abre una nueva.

🛠 PASO 2: Validar instalación
Corre estos comandos:

    rustc --version

    cargo --version

    rustup show

💡 Resultado esperado:

    rustc: algo como rustc 1.77.2 (o versión estable actual)

    cargo: versión compatible con el rustc instalado

    rustup: muestra el toolchain activo (debería ser stable)

🛠 PASO 3: Primer proyecto con cargo
Crea un nuevo proyecto:
 
    cargo new hello_rust
    cd hello_rust
    cargo run

💡 Espera: Hello, world! en la consola.

🛠 PASO 4: Compilar manualmente
Por cultura Rust: compila tú mismo:
 
    cargo build
    ./target/debug/hello_rust

(o target\debug\hello_rust.exe en Windows)

🛠 PASO 5: Entender qué es cada herramienta
📝 Reflexiona y anota:

¿Para qué sirve rustc?

¿Para qué sirve cargo?

¿Para qué sirve rustup?

Si quieres, escríbelo aquí y lo reviso contigo.

