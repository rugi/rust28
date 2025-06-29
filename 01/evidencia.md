## Semana 1. Validación.
    [rugi@bigoze semana01]$ rustc --version
                        rustc 1.87.0 (17067e9ac 2025-05-09)

    [rugi@bigoze semana01]$ cargo --version
        cargo 1.87.0 (99624be96 2025-05-06)

```
[rugi@bigoze semana01]$ rustup show
Default host: x86_64-unknown-linux-gnu
rustup home:  /home/rugi/.rustup

installed toolchains
--------------------
stable-x86_64-unknown-linux-gnu (active, default)

active toolchain
----------------
name: stable-x86_64-unknown-linux-gnu
active because: it's the default toolchain
installed targets:
  x86_64-unknown-linux-gnu
```

## Dudas.
### Pregunta:
¿Qué es el toolchain? qué significa que exista y que esté estable?

### Respuesta:
¡Qué buena pregunta, Isaac! Me alegra mucho que vayas profundizando, porque eso marca la diferencia entre “solo usar Rust” y entender bien lo que pasa detrás.
Déjame explicártelo de forma clara y práctica:

🚀 ¿Qué es un toolchain en Rust?

➡ Un toolchain es el conjunto de herramientas que necesitas para escribir, compilar y manejar programas en Rust.

Cuando instalas Rust con rustup, lo que realmente estás instalando es un toolchain que incluye:
✅ rustc → El compilador de Rust (convierte tu código fuente en un binario).

✅ cargo → El build system y package manager (gestiona proyectos, dependencias, compilación).

✅ Estándar libraries → Los archivos que definen las librerías base que todo programa Rust usa (por ejemplo std::io, std::fs).

✅ Otras herramientas opcionales → Ej. clippy, rustfmt, rustdoc.

Entonces, el toolchain es el paquete completo de herramientas que forman el entorno de trabajo Rust para un cierto propósito o versión.

🔑 ¿Por qué hablamos de un toolchain “estable”?

👉 Rust tiene varias “versiones” de toolchains que puedes usar según tu necesidad:

| Toolchain    |	Uso principal    |	Ejemplo    |
| -------- | ------- | ------- |
| stable    | 	Código de producción. Probado, con soporte, sin cambios experimentales.    | 	rustc 1.87.0 que tú tienes ahora.    | 
| beta    | 	Versión previa a la próxima stable. Para testing anticipado.    | 	Ej: rustc 1.88.0-beta    
| nightly    | 	Donde se prueban nuevas características experimentales. Permite usar features no estables.    | 	Ej: rustc 1.89.0-nightly | 

Cuando rustup show dice:

    stable-x86_64-unknown-linux-gnu (active, default)
    
➡ Significa que:

✅ Tu toolchain activo es stable, o sea el recomendado para producción y aprendizaje.

✅ Estás usando un Rust “seguro” (sin features experimentales).

✅ El toolchain corresponde a tu arquitectura x86_64-unknown-linux-gnu (64 bits en Linux en tu caso).

📝 ¿Por qué existe el concepto de toolchain?

Porque Rust permite tener varias versiones instaladas al mismo tiempo, y decidir cuál usar proyecto por proyecto.
Por ejemplo:

Un proyecto podría necesitar nightly para usar const generics.

Otro podría requerir stable para deployar en producción.

👉 rustup es lo que facilita ese manejo de toolchains y sus versiones.

⚡ En resumen

🔹 El toolchain es el conjunto completo de herramientas de una versión de Rust.

🔹 Que sea estable significa que es confiable, listo para producción y aprendizaje, sin features experimentales.

🔹 rustup te deja cambiar de toolchain y administrar distintas versiones fácilmente.


# Tarea
#### Preguntas:
Explica con tus propias palabras:
* rustc
* cargo
* rustup

#### Respuestas:
✅ rustc
es el compilador, es decir, es la herramienta que convierte el codigo fuente en binario, dado que rust no es multiplataforma, este binario resultante es propio de la plataforma donde se compila

✔ Correctísimo.
Solo agrego: Rust sí es multiplataforma en el sentido de que puedes compilar para otros targets (cross-compiling), pero por default el binario es para la plataforma donde se genera, como bien dices.

💡 Dato clave: En cross-compiling puedes generar binarios para Windows desde Linux, o para ARM desde x86, pero requiere configuración adicional.

✅ cargo
es la herramienta de gestión de ciclo de vida de un proyecto de rust, entiendo que es el equivalente de maven en java, puedo construir/build , iniciar / init, documentar/doc, etc

✔ Perfecta analogía.

👉 Sí, es el “Maven” o “Gradle” de Rust:

Gestiona dependencias (crates).

Construye y compila (build).

Documenta (doc).

Ejecuta tests (test).

Publica crates (publish).

✅ rustup
es una herramienta que me permite saber si el toolchain ( es decir el conjunto de herramientas para programar en rust) està OK, y/o me da el status actual.

✔ Muy bien explicado.

💡 Agrego:
Además de mostrar el estado, rustup también:

Instala y actualiza toolchains.

Cambia entre versiones (stable, beta, nightly).

Permite configurar toolchain por proyecto (con rust-toolchain).
