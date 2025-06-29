🎯 Objetivo general
Aprender a:

* Usar rustup para actualizar y gestionar toolchains (incluyendo nightly).

* Instalar y usar herramientas de apoyo: clippy, rustfmt, cargo-edit.

* Validar que están instaladas y funcionando.

* Usar correctamente esas herramientas en un proyecto existente.

✅ Actividades detalladas
1. 🔄 Actualizar tu toolchain con rustup

    rustup update
   
    rustup show

Verifica que estás usando la versión más reciente de stable.

2. 🌙 Instalar y probar toolchain nightly

    rustup install nightly
    rustup show

✔ Luego, entra a tu proyecto y prueba correrlo con nightly sin cambiar el global:

    cargo +nightly run

3. 🔧 Instalar herramientas comunes
Estas herramientas son muy utilizadas en el ecosistema Rust:

a) Instalar clippy (linter inteligente)
 
    rustup component add clippy
    cargo clippy
    
b) Instalar rustfmt (formateador automático)

    rustup component add rustfmt
    cargo fmt
    
c) Instalar cargo-edit (agrega/quita dependencias fácilmente)

    cargo install cargo-edit
    cargo add anyhow

💡 Esto agregará anyhow al Cargo.toml.

4. 🧪 Probar todo en tu proyecto hello_rust
* Ejecuta cargo clippy y revisa las advertencias (corrige alguna si aplica).

* Ejecuta cargo fmt y revisa si se formateó el archivo.

* Agrega una dependencia usando cargo add.

* Ejecuta el programa con cargo +nightly run como prueba.

📋 Checklist de validación
|  Ítem  |	Estado  |
| ----- | ----- |
| [ ] Ejecuté rustup update correctamente	 |  |
| [ ] Instalé y probé el toolchain nightly	 |  |
| [ ] Usé cargo +nightly run con éxito	 |  |
| [ ] Instalé clippy y ejecuté cargo clippy	 |  |
| [ ] Instalé rustfmt y ejecuté cargo fmt	 |  |
| [ ] Instalé cargo-edit y usé cargo add <crate>	 |  |
| [ ] Probé estas herramientas sobre mi proyecto hello_rust	 |  |

📝 Cierre de sesión
Para finalizar, puedes compartir conmigo:

* Salida de rustup show después de instalar nightly.

* Algún warning de clippy que hayas corregido.

* Algún cambio de formato hecho por rustfmt.

* Dependencia agregada con cargo add.

