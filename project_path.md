# project path
<!-- KtF -->
## init new project folder
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
project_name="rust-wasm-bindgen-try-out"
echo ${project_name} 
# cd && mkdir <project_name> folder> && cd $_
# command 'cd' change to home folder from logged in user
# command 'mkdir' create the DIRECTORY(ies), if they do not already exist
# command `cd` <folder>`change to the folder
# command '$_' last argument of last command
cd && mkdir ${project_name} && cd $_

```
<!-- KtF -->
## Create a new rust based project inside the previously generated folder and update the rust binary's system wide to the last stable version
<!-- KtF -->
```bash <!-- markdownlint-disable-line code-block-style -->
touch README.md \
&& ln -s README.md README \
&& cargo init "." \
&& cargo add rustfmt \
&& rustup component add rustfmt \
&& mkdir examples \
&& cp src/main.rs examples/example.rs \
&& sed -i -e 's/world/example/g' examples/example.rs \
&& rustup show \
&& rustup check \
&& rustup toolchain uninstall stable \
&& rustup toolchain install stable \
&& rustup update  --force \
&& rustup show \
&& mkdir tests
```
<!-- KtF-->
## Install WASM binary

[![alt text][1]](https://crates.io/crates/wasm-bindgen-cli)

<!-- KtF-->
Install for Running the above command will globally install these binaries: wasm-bindgen, wasm-bindgen-test-runnerand wasm2es6js
<!-- KtF -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo install wasm-bindgen-cli
```
<!-- KtF -->
## Install WASM **crates** [![alt text][1]](https://crates.io/crates/wasm-bindgen-cli)

<!-- KtF -->
- [![alt text][1]](https://stackoverflow.com/questions/58895030/exclude-hidden-files-and-folders-in-linux-find)

```bash <!-- markdownlint-disable-line code-block-style -->
cargo add wasm-bindgen
cargo add wasm-bindgen-cli
```
<!-- KtF-->
## Add crate-type to Cargo.toml
<!-- KtF -->
```bash <!-- markdownlint-disable-line code-block-style -->

[lib]
crate-type = ["cdylib"]


https://stackoverflow.com/questions/65012484/is-it-possible-to-override-the-crate-type-specified-in-cargo-toml-from-the-comma
cargo install cargo-crate-type

<!-- -->
<!-- keep the format -->
>&nbsp;[!TIP] Exclude hidden files and folders in linux find [![alt text][1]](https://stackoverflow.com/questions/58895030/exclude-hidden-files-and-folders-in-linux-find)
><!-- keep the format -->
>```bash <!-- markdownlint-disable-line code-block-style -->
>find . -name "*.md" -not -path '*/[@.]*' -exec grep -nH  "EOF" {} \;
>```
><!-- keep the format -->
<!-- keep the format -->
>&nbsp;[!TIP] How does "cat << EOF" work in bash? [![alt text][1]](https://stackoverflow.com/questions/2500436/how-does-cat-eof-work-in-bash)
> <!-- -->
> ```bash
>cat <<EOF > print.sh
>#!/bin/bash
>echo \$PWD
>echo $PWD
>EOF
>```
<!-- -->


[1]: ./img/link_symbol.svg
