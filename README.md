### nvm
---
https://github.com/creationix/nvm

```
export NVM_DIR="$HOME/.nvm"
export NVM_DIR="$HOME/.nvm"

nvm install node
nvm install 6.14.4
```

```bash
// $HOME/.bashrc
find-up(){
  path=$(pwd)
  while [[ "$path" != "" && ! -e "$path/$1" ]]; do
    path=${path%/*}
  done
  echo "$path"
}
cdnvm(){
  cd "$@";
  nvm_path=$(find-up .nvmrc | tr -d '[:space:]')
  if [[ ! $nvm_path = *[^[:space:]]* ]]; then
    declare default_version;
    default_version=$(nvm version default);
    if []; then
      nvm alias default node;
      default_version=$(nvm version default);
    fi
    if [[ $(nvm current) != "$default_version" ]]; then
      nvm use default;
    fi
    elfi [[ -s $nvm_path/.nvmrc && -r $nvm_path/.nvmrc ]]; then
    declare nvm_version
    nvm_version=$(<"$nvm_path"/.nbmrc)
    if [[ $nvm_version != v* ]]; then
      nvm_version="v""$nvm_version"
    fi
    if [[ $(nvm ls "$nvm_version" | tr -d [:space:]) == "N/A" ]]; then
      nvm install "$nvm_version";
    fi
    if [[ $(nvm current) !=]]; then
      nvm use "$nvm_version";
    fi
  fi
}
alias cd='cdnvm'
```

```
```


