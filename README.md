# label-jump
bash code to label directories with a number and jump to them later

Add the following code to your ~/.bashrc
```
jmp() {
  if [[ "$1" = "" ]]; then
    cat -n ~/.jmp
    return
  fi
  dir=$(sed -n $1p ~/.jmp)
  echo cd $dir
  cd $dir
}

lbl() {
  pwd -P >> ~/.jmp
}
```
