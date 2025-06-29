# Evidencia.

## Actualizar tu toolchain con rustup

```bash
[rugi@bigoze hello_rust]$ echo "carpeta actual"
carpeta actual

[rugi@bigoze hello_rust]$ pwd
/home/rugi/labs/rust/hello_rust

[rugi@bigoze hello_rust]$ rustup update
info: syncing channel updates for 'stable-x86_64-unknown-linux-gnu'
info: latest update on 2025-06-26, rust version 1.88.0 (6b00bc388 2025-06-23)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
info: downloading component 'rust-std'
info: downloading component 'rustc'
info: downloading component 'rustfmt'
info: removing previous version of component 'cargo'
info: removing previous version of component 'clippy'
info: removing previous version of component 'rust-docs'
info: removing previous version of component 'rust-std'
info: removing previous version of component 'rustc'
info: removing previous version of component 'rustfmt'
info: installing component 'cargo'
info: installing component 'clippy'
info: installing component 'rust-docs'
 20.1 MiB /  20.1 MiB (100 %)   4.7 MiB/s in  4s         
info: installing component 'rust-std'
 29.5 MiB /  29.5 MiB (100 %)   8.8 MiB/s in  3s         
info: installing component 'rustc'
 76.3 MiB /  76.3 MiB (100 %)   9.2 MiB/s in  8s         
info: installing component 'rustfmt'
info: checking for self-update

  stable-x86_64-unknown-linux-gnu updated - rustc 1.88.0 (6b00bc388 2025-06-23) (from rustc 1.87.0 (17067e9ac 2025-05-09))

info: cleaning up downloads & tmp directories

[rugi@bigoze hello_rust]$ rustup show
Default host: x86_64-unknown-linux-gnu
rustup home:  /home/rugi/.rustup
```
