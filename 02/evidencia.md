# Evidencia.

## 1. Actualizar tu toolchain con rustup

```console
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

## 3.Instalar herramientas comunes
Estas herramientas son muy utilizadas en el ecosistema Rust:

### Instalar clippy (linter inteligente)
```console
[rugi@bigoze hello_rust]$ echo "Carpeta actual"
Carpeta actual

[rugi@bigoze hello_rust]$ pwd
/home/rugi/labs/rust/hello_rust

[rugi@bigoze hello_rust]$ rustup component add clippy
info: component 'clippy' for target 'x86_64-unknown-linux-gnu' is up to date

[rugi@bigoze hello_rust]$ cargo clippy
    Checking hello_rust v0.1.0 (/home/rugi/labs/rust/hello_rust)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.46s

[rugi@bigoze hello_rust]$ 
```

### Instalar rustfmt (formateador automático)
```console
[rugi@bigoze hello_rust]$ echo "Carpeta actual"
Carpeta actual

[rugi@bigoze hello_rust]$ pwd
/home/rugi/labs/rust/hello_rust

[rugi@bigoze hello_rust]$ rustup component add rustfmt
info: component 'rustfmt' for target 'x86_64-unknown-linux-gnu' is up to date

[rugi@bigoze hello_rust]$ cargo fmt

[rugi@bigoze hello_rust]$ 
```

###  Instalar cargo-edit (agrega/quita dependencias fácilmente)

```console
[rugi@bigoze hello_rust]$ echo "Carpeta actual"
Carpeta actual
[rugi@bigoze hello_rust]$ pwd
/home/rugi/labs/rust/hello_rust
[rugi@bigoze hello_rust]$ cargo install cargo-edit
    Updating crates.io index
  Downloaded cargo-edit v0.13.6
  Downloaded 1 crate (72.9KiB) in 0.07s
  Installing cargo-edit v0.13.6
    Updating crates.io index
     Locking 242 packages to latest compatible versions
      Adding cargo_metadata v0.19.2 (available: v0.20.0)
      Adding tame-index v0.17.0 (available: v0.22.0)
  Downloaded anstream v0.6.19
  Downloaded potential_utf v0.1.2
  Downloaded pin-project-lite v0.2.16
  Downloaded sync_wrapper v1.0.2
  Downloaded zerofrom v0.1.6
  Downloaded zerovec-derive v0.11.1
  Downloaded yoke v0.8.0
  Downloaded tracing-core v0.1.34
  Downloaded zerotrie v0.2.2
  Downloaded tame-index v0.17.0
  Downloaded tower v0.5.2
  Downloaded zerovec v0.11.2
  Downloaded tower-http v0.6.6
  Downloaded tokio-util v0.7.15
  Downloaded winnow v0.7.11
  Downloaded reqwest v0.12.20
  Downloaded regex v1.11.1
  Downloaded zerocopy v0.8.26
  Downloaded webpki-roots v1.0.1
  Downloaded syn v2.0.104
  Downloaded quinn-proto v0.11.12
  Downloaded rustls v0.23.28
  Downloaded rayon v1.10.0
  Downloaded regex-syntax v0.8.5
  Downloaded serde_json v1.0.140
  Downloaded rustix v1.0.7
  Downloaded hyper v1.6.0
  Downloaded rand v0.9.1
  Downloaded idna v1.0.3
  Downloaded icu_properties_data v2.0.1
  Downloaded hashbrown v0.15.4
  Downloaded h2 v0.4.10
  Downloaded futures-util v0.3.31
  Downloaded clap_builder v4.5.40
  Downloaded url v2.5.4
  Downloaded typenum v1.18.0
  Downloaded tracing v0.1.41
  Downloaded toml_edit v0.22.27
  Downloaded regex-automata v0.4.9
  Downloaded serde v1.0.219
  Downloaded jiff v0.2.15
  Downloaded iri-string v0.7.8
  Downloaded toml v0.8.23
  Downloaded libc v0.2.174
  Downloaded tinyvec v1.9.0
  Downloaded serde_derive v1.0.219
  Downloaded tokio v1.45.1
  Downloaded rustls-webpki v0.103.3
  Downloaded rayon-core v1.12.1
  Downloaded http v1.3.1
  Downloaded cc v1.2.27
  Downloaded writeable v0.6.1
  Downloaded unicode-ident v1.0.18
  Downloaded toml-span v0.4.1
  Downloaded thiserror v2.0.12
  Downloaded socket2 v0.5.10
  Downloaded ryu v1.0.20
  Downloaded rustls-pki-types v1.12.0
  Downloaded quinn v0.11.8
  Downloaded memchr v2.7.5
  Downloaded indexmap v2.10.0
  Downloaded hyper-util v0.1.14
  Downloaded flate2 v1.1.2
  Downloaded crossbeam-channel v0.5.15
  Downloaded bytes v1.10.1
  Downloaded async-compression v0.4.25
  Downloaded zeroize v1.8.1
  Downloaded zerofrom-derive v0.1.6
  Downloaded version_check v0.9.5
  Downloaded utf8parse v0.2.2
  Downloaded utf8_iter v1.0.4
  Downloaded twox-hash v2.1.1
  Downloaded toml_write v0.1.2
  Downloaded toml_datetime v0.6.11
  Downloaded tokio-rustls v0.26.2
  Downloaded tinyvec_macros v0.1.1
  Downloaded thiserror-impl v2.0.12
  Downloaded terminal_size v0.4.2
  Downloaded termcolor v1.4.1
  Downloaded synstructure v0.13.2
  Downloaded smol_str v0.3.2
  Downloaded smallvec v1.15.1
  Downloaded shlex v1.3.0
  Downloaded ring v0.17.14
  Downloaded sha2 v0.10.9
  Downloaded serde_spanned v0.6.9
  Downloaded semver v1.0.26
  Downloaded rustls-native-certs v0.8.1
  Downloaded rand_core v0.9.3
  Downloaded rand_chacha v0.9.0
  Downloaded quote v1.0.40
  Downloaded quinn-udp v0.5.13
  Downloaded mio v1.0.4
  Downloaded icu_properties v2.0.1
  Downloaded icu_normalizer_data v2.0.0
  Downloaded icu_normalizer v2.0.0
  Downloaded icu_locale_core v2.0.0
  Downloaded icu_collections v2.0.0
  Downloaded clap v4.5.40
  Downloaded borsh v1.5.7
  Downloaded base64 v0.22.1
  Downloaded aho-corasick v1.1.3
  Downloaded yoke-derive v0.8.0
  Downloaded want v0.3.1
  Downloaded untrusted v0.9.0
  Downloaded try-lock v0.2.5
  Downloaded tower-service v0.3.3
  Downloaded tower-layer v0.3.3
  Downloaded tinystr v0.8.1
  Downloaded subtle v2.6.1
  Downloaded strsim v0.11.1
  Downloaded stable_deref_trait v1.2.0
  Downloaded rustc-hash v2.1.1
  Downloaded ppv-lite86 v0.2.21
  Downloaded miniz_oxide v0.8.9
  Downloaded httparse v1.10.1
  Downloaded getrandom v0.3.3
  Downloaded slab v0.4.10
  Downloaded serde_urlencoded v0.7.1
  Downloaded proc-macro2 v1.0.95
  Downloaded log v0.4.27
  Downloaded icu_provider v2.0.0
  Downloaded getrandom v0.2.16
  Downloaded env_logger v0.11.8
  Downloaded crossbeam-utils v0.8.21
  Downloaded crossbeam-epoch v0.9.18
  Downloaded clap_derive v4.5.40
  Downloaded cargo_metadata v0.19.2
  Downloaded camino v1.1.10
  Downloaded bitflags v2.9.1
  Downloaded linux-raw-sys v0.9.4
  Downloaded anyhow v1.0.98
  Downloaded once_cell v1.21.3
  Downloaded lru-slab v0.1.2
  Downloaded litemap v0.8.0
  Downloaded itoa v1.0.15
  Downloaded is_terminal_polyfill v1.70.1
  Downloaded ipnet v2.11.0
  Downloaded idna_adapter v1.2.1
  Downloaded hyper-rustls v0.27.7
  Downloaded http-body-util v0.1.3
  Downloaded home v0.5.11
  Downloaded hex v0.4.3
  Downloaded heck v0.5.0
  Downloaded generic-array v0.14.7
  Downloaded futures-task v0.3.31
  Downloaded futures-sink v0.3.31
  Downloaded futures-io v0.3.31
  Downloaded futures-core v0.3.31
  Downloaded futures-channel v0.3.31
  Downloaded form_urlencoded v1.2.1
  Downloaded fnv v1.0.7
  Downloaded errno v0.3.13
  Downloaded env_filter v0.1.3
  Downloaded either v1.15.0
  Downloaded dunce v1.0.5
  Downloaded displaydoc v0.2.5
  Downloaded digest v0.10.7
  Downloaded crypto-common v0.1.6
  Downloaded crossbeam-deque v0.8.6
  Downloaded crc32fast v1.4.2
  Downloaded cpufeatures v0.2.17
  Downloaded concolor-query v0.0.4
  Downloaded colorchoice v1.0.4
  Downloaded clap_lex v0.7.5
  Downloaded clap-verbosity-flag v3.0.3
  Downloaded clap-cargo v0.15.2
  Downloaded cfg-if v1.0.1
  Downloaded cargo-platform v0.1.9
  Downloaded block-buffer v0.10.4
  Downloaded bitflags v1.3.2
  Downloaded atomic-waker v1.1.2
  Downloaded anstyle-query v1.1.3
  Downloaded anstyle-parse v0.2.7
  Downloaded anstyle v1.0.11
  Downloaded pin-utils v0.1.0
  Downloaded percent-encoding v2.3.1
  Downloaded pathdiff v0.2.3
  Downloaded openssl-probe v0.1.6
  Downloaded http-body v1.0.1
  Downloaded equivalent v1.0.2
  Downloaded concolor-control v0.0.7
  Downloaded cfg_aliases v0.2.1
  Downloaded atty v0.2.14
  Downloaded adler2 v2.0.1
  Downloaded 185 crates (16.2MiB) in 1.72s (largest was `linux-raw-sys` at 2.2MiB)
   Compiling proc-macro2 v1.0.95
   Compiling unicode-ident v1.0.18
   Compiling libc v0.2.174
   Compiling memchr v2.7.5
   Compiling serde v1.0.219
   Compiling stable_deref_trait v1.2.0
   Compiling bytes v1.10.1
   Compiling quote v1.0.40
   Compiling syn v2.0.104
   Compiling pin-project-lite v0.2.16
   Compiling futures-core v0.3.31
   Compiling itoa v1.0.15
   Compiling socket2 v0.5.10
   Compiling mio v1.0.4
   Compiling cfg-if v1.0.1
   Compiling futures-sink v0.3.31
   Compiling shlex v1.3.0
   Compiling cc v1.2.27
   Compiling tokio v1.45.1
   Compiling smallvec v1.15.1
   Compiling once_cell v1.21.3
   Compiling fnv v1.0.7
   Compiling http v1.3.1
   Compiling ring v0.17.14
   Compiling litemap v0.8.0
   Compiling equivalent v1.0.2
   Compiling hashbrown v0.15.4
   Compiling zeroize v1.8.1
   Compiling bitflags v2.9.1
   Compiling slab v0.4.10
   Compiling writeable v0.6.1
   Compiling indexmap v2.10.0
   Compiling synstructure v0.13.2
   Compiling rustls-pki-types v1.12.0
   Compiling futures-task v0.3.31
   Compiling futures-io v0.3.31
   Compiling crossbeam-utils v0.8.21
   Compiling zerofrom-derive v0.1.6
   Compiling yoke-derive v0.8.0
   Compiling serde_derive v1.0.219
   Compiling zerofrom v0.1.6
   Compiling yoke v0.8.0
   Compiling zerovec-derive v0.11.1
   Compiling displaydoc v0.2.5
   Compiling zerovec v0.11.2
   Compiling zerotrie v0.2.2
   Compiling icu_normalizer_data v2.0.0
   Compiling pin-utils v0.1.0
   Compiling version_check v0.9.5
   Compiling tinystr v0.8.1
   Compiling potential_utf v0.1.2
   Compiling typenum v1.18.0
   Compiling icu_locale_core v2.0.0
   Compiling icu_properties_data v2.0.1
   Compiling icu_collections v2.0.0
   Compiling icu_provider v2.0.0
   Compiling generic-array v0.14.7
   Compiling futures-util v0.3.31
   Compiling http-body v1.0.1
   Compiling tracing-core v0.1.34
   Compiling getrandom v0.2.16
   Compiling percent-encoding v2.3.1
   Compiling httparse v1.10.1
   Compiling untrusted v0.9.0
   Compiling utf8parse v0.2.2
   Compiling rustix v1.0.7
   Compiling anstyle-parse v0.2.7
   Compiling tracing v0.1.41
   Compiling tokio-util v0.7.15
   Compiling anstyle v1.0.11
   Compiling try-lock v0.2.5
   Compiling is_terminal_polyfill v1.70.1
   Compiling rustls v0.23.28
   Compiling linux-raw-sys v0.9.4
   Compiling atomic-waker v1.1.2
   Compiling tower-service v0.3.3
   Compiling colorchoice v1.0.4
   Compiling anstyle-query v1.1.3
   Compiling rustls-webpki v0.103.3
   Compiling anstream v0.6.19
   Compiling h2 v0.4.10
   Compiling want v0.3.1
   Compiling icu_properties v2.0.1
   Compiling icu_normalizer v2.0.0
   Compiling futures-channel v0.3.31
   Compiling ryu v1.0.20
   Compiling subtle v2.6.1
   Compiling adler2 v2.0.1
   Compiling log v0.4.27
   Compiling miniz_oxide v0.8.9
   Compiling idna_adapter v1.2.1
   Compiling terminal_size v0.4.2
   Compiling crossbeam-epoch v0.9.18
   Compiling hyper v1.6.0
   Compiling form_urlencoded v1.2.1
   Compiling crc32fast v1.4.2
   Compiling sync_wrapper v1.0.2
   Compiling aho-corasick v1.1.3
   Compiling base64 v0.22.1
   Compiling camino v1.1.10
   Compiling semver v1.0.26
   Compiling serde_json v1.0.140
   Compiling tower-layer v0.3.3
   Compiling rayon-core v1.12.1
   Compiling strsim v0.11.1
   Compiling openssl-probe v0.1.6
   Compiling regex-syntax v0.8.5
   Compiling ipnet v2.11.0
   Compiling clap_lex v0.7.5
   Compiling thiserror v2.0.12
   Compiling heck v0.5.0
   Compiling utf8_iter v1.0.4
   Compiling clap_derive v4.5.40
   Compiling idna v1.0.3
   Compiling regex-automata v0.4.9
   Compiling clap_builder v4.5.40
   Compiling hyper-util v0.1.14
   Compiling tokio-rustls v0.26.2
   Compiling rustls-native-certs v0.8.1
   Compiling tower v0.5.2
   Compiling flate2 v1.1.2
   Compiling crossbeam-deque v0.8.6
   Compiling crypto-common v0.1.6
   Compiling block-buffer v0.10.4
   Compiling thiserror-impl v2.0.12
   Compiling webpki-roots v1.0.1
   Compiling iri-string v0.7.8
   Compiling hyper-rustls v0.27.7
   Compiling tower-http v0.6.6
   Compiling digest v0.10.7
   Compiling async-compression v0.4.25
   Compiling clap v4.5.40
   Compiling regex v1.11.1
   Compiling url v2.5.4
   Compiling serde_urlencoded v0.7.1
   Compiling toml_datetime v0.6.11
   Compiling serde_spanned v0.6.9
   Compiling http-body-util v0.1.3
   Compiling cpufeatures v0.2.17
   Compiling either v1.15.0
   Compiling anyhow v1.0.98
   Compiling toml_write v0.1.2
   Compiling winnow v0.7.11
   Compiling rayon v1.10.0
   Compiling reqwest v0.12.20
   Compiling sha2 v0.10.9
   Compiling env_filter v0.1.3
   Compiling crossbeam-channel v0.5.15
   Compiling toml_edit v0.22.27
   Compiling cargo-platform v0.1.9
   Compiling smol_str v0.3.2
   Compiling toml-span v0.4.1
   Compiling atty v0.2.14
   Compiling jiff v0.2.15
   Compiling home v0.5.11
   Compiling bitflags v1.3.2
   Compiling twox-hash v2.1.1
   Compiling concolor-query v0.0.4
   Compiling concolor-control v0.0.7
   Compiling tame-index v0.17.0
   Compiling env_logger v0.11.8
   Compiling toml v0.8.23
   Compiling cargo_metadata v0.19.2
   Compiling clap-verbosity-flag v3.0.3
   Compiling clap-cargo v0.15.2
   Compiling hex v0.4.3
   Compiling termcolor v1.4.1
   Compiling dunce v1.0.5
   Compiling pathdiff v0.2.3
   Compiling cargo-edit v0.13.6
    Finished `release` profile [optimized] target(s) in 2m 43s
  Installing /home/rugi/.cargo/bin/cargo-add
  Installing /home/rugi/.cargo/bin/cargo-rm
  Installing /home/rugi/.cargo/bin/cargo-set-version
  Installing /home/rugi/.cargo/bin/cargo-upgrade
   Installed package `cargo-edit v0.13.6` (executables `cargo-add`, `cargo-rm`, `cargo-set-version`, `cargo-upgrade`)

[rugi@bigoze hello_rust]$ cargo add anyhow
    Updating crates.io index
      Adding anyhow v1.0.98 to dependencies
             Features:
             + std
             - backtrace
    Updating crates.io index
     Locking 1 package to latest Rust 1.88.0 compatible version
      Adding anyhow v1.0.98

[rugi@bigoze hello_rust]$ 
```

Esto agregará anyhow al Cargo.toml.
### Validar Cargo.toml
#### Archivo original
```file
[package]
name = "hello_rust"
version = "0.1.0"
edition = "2024"

[dependencies]
```

#### Despues
```file
[package]
name = "hello_rust"
version = "0.1.0"
edition = "2024"

[dependencies]
anyhow = "1.0.98"
```

## 4.Probar todo en tu proyecto hello_rust
```console
[rugi@bigoze hello_rust]$ echo "carpeta actual"
carpeta actual

[rugi@bigoze hello_rust]$ pwd
/home/rugi/labs/rust/hello_rust

[rugi@bigoze hello_rust]$ cargo clippy
   Compiling anyhow v1.0.98
    Checking hello_rust v0.1.0 (/home/rugi/labs/rust/hello_rust)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.83s

[rugi@bigoze hello_rust]$ cargo fmt

[rugi@bigoze hello_rust]$ cargo add anyhow
    Updating crates.io index
      Adding anyhow v1.0.98 to dependencies
             Features:
             + std
             - backtrace

[rugi@bigoze hello_rust]$ cargo +nightly run
   Compiling anyhow v1.0.98
   Compiling hello_rust v0.1.0 (/home/rugi/labs/rust/hello_rust)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 2.12s
     Running `target/debug/hello_rust`
Hello, world!

[rugi@bigoze hello_rust]$ 
```
## Extra. Cierre de session.
### Salida de rustup show después de instalar nightly.
```console
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
```

Ya se ve el toolchain: nightly-x86_64-unknown-linux-gnu                   ✅

Se puede ejecutar el proyecto sin problemas usando : cargo +nightly run   ✅
  
### Algún warning de clippy que hayas corregido.
Ningun warging
### Algún cambio de formato hecho por rustfmt.
Ningun cambio
### Dependencia agregada con cargo add.

    anyhow

Se ve la dependencia agregada en el archivo Cargo.toml                    ✅


Lista la validación de la session 02.
