# Evidencia.

## 1. Actualizar tu toolchain con rustup

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


## 2. Instalar y probar toolchain nightly
```console
[rugi@bigoze hello_rust]$ rustup install nightly
info: syncing channel updates for 'nightly-x86_64-unknown-linux-gnu'
info: latest update on 2025-06-29, rust version 1.90.0-nightly (11ad40bb8 2025-06-28)
info: downloading component 'cargo'
info: downloading component 'clippy'
info: downloading component 'rust-docs'
info: downloading component 'rust-std'
info: downloading component 'rustc'
info: downloading component 'rustfmt'
info: installing component 'cargo'
  9.7 MiB /   9.7 MiB (100 %)   9.2 MiB/s in  1s         
info: installing component 'clippy'
info: installing component 'rust-docs'
 20.4 MiB /  20.4 MiB (100 %)   4.8 MiB/s in  4s         
info: installing component 'rust-std'
 27.7 MiB /  27.7 MiB (100 %)   8.3 MiB/s in  3s         
info: installing component 'rustc'
 77.6 MiB /  77.6 MiB (100 %)   9.0 MiB/s in  8s         
info: installing component 'rustfmt'

  nightly-x86_64-unknown-linux-gnu installed - rustc 1.90.0-nightly (11ad40bb8 2025-06-28)

info: checking for self-update


[rugi@bigoze hello_rust]$ rustup show
Default host: x86_64-unknown-linux-gnu
rustup home:  /home/rugi/.rustup

installed toolchains
--------------------
stable-x86_64-unknown-linux-gnu (active, default)
nightly-x86_64-unknown-linux-gnu

active toolchain
----------------
name: stable-x86_64-unknown-linux-gnu
active because: it's the default toolchain
installed targets:
  x86_64-unknown-linux-gnu
[rugi@bigoze hello_rust]$ 
```
 Luego, entra a tu proyecto y prueba correrlo con nightly sin cambiar el global:
 
```console
 /home/rugi/labs/rust/hello_rust
[rugi@bigoze hello_rust]$ cargo +nightly run
   Compiling hello_rust v0.1.0 (/home/rugi/labs/rust/hello_rust)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.25s
     Running `target/debug/hello_rust`
Hello, world!
[rugi@bigoze hello_rust]$
```


 
