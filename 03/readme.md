# Session 3. Actividades.

🎯 Objetivos.
Configurar correctamente VSCode como entorno de desarrollo Rust productivo, con:

Soporte para análisis estático (rust-analyzer)

Autocompletado, navegación, y diagnóstico en tiempo real

Ejecución directa desde el editor

Integración con clippy y fmt

✅ Actividades detalladas
1. 🧰 Instalar Visual Studio Code
Si no lo tienes, instálalo desde:
👉 https://code.visualstudio.com/

💡 Ya que estás en Linux, puedes usar el gestor de paquetes de tu distro si prefieres.

2. 🧩 Instalar la extensión rust-analyzer
Abre VSCode

Ve a la barra izquierda (extensiones) → busca rust-analyzer

Instálala (de la editorial rust-lang)

Reinicia VSCode si es necesario

3. 📂 Abrir el proyecto hello_rust desde VSCode
Abre la carpeta /home/rugi/labs/rust/hello_rust como un proyecto.

Espera a que rust-analyzer cargue (verás un aviso de análisis en progreso abajo a la derecha)

4. 🧪 Validar funcionalidades básicas
Dentro del archivo main.rs, verifica que puedes:

Función	Cómo probar
Autocompletado	Escribe pri y espera que sugiera println!
Go to Definition	Ctrl + click sobre println!
Hover Info	Pasa el mouse sobre println! o sobre una variable
Errores en línea	Escribe un código incorrecto (por ejemplo: let x = ;) y observa la advertencia

5. ▶ Ejecutar desde el terminal del editor
Abre la terminal integrada (Ctrl + ñ o Ctrl + Shift + ~) y ejecuta:

bash
Copy
Edit
cargo run
💡 También puedes instalar la extensión Code Runner si deseas ejecutar con botón, pero no es obligatorio.

6. 🎯 Ejecutar cargo fmt y cargo clippy desde VSCode
Desde la terminal integrada de VSCode:

bash
Copy
Edit
cargo fmt
cargo clippy
📋 Checklist de validación – Semana 3
Ítem	Estado
[ ] VSCode instalado correctamente	
[ ] rust-analyzer instalado y activo	
[ ] Proyecto hello_rust abierto como workspace	
[ ] Autocompletado funciona (println!)	
[ ] "Go to definition" y "hover info" funcionan	
[ ] Se detecta un error sintáctico al escribir código incorrecto	
[ ] Ejecuté cargo run desde la terminal integrada	
[ ] Ejecuté cargo fmt y cargo clippy desde el editor
