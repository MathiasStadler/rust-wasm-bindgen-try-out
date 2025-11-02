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
## Install WASM crates
<!-- KtF-->
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
><!-- -->
<!-- -->
<!-- download the link sign -->
<!-- mkdir -p img && curl --create-dirs --output-dir img -O  "https://raw.githubusercontent.com/MathiasStadler/link_symbol_svg/refs/heads/main/link_symbol.svg"-->
<!-- Link sign - Don't Found a better way :-( - You know a better method? - send me a email -->
[1]: ./img/link_symbol.svg
<!-- keep the format -->