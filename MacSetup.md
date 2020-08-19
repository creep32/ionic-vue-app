# first
1. sudo visudo
add user that is getable via `whoami`, to following

```
mac-dev        ALL=(ALL) NOPASSWD: ALL
```

2. chmod
sudo chown -R $(whoami) /usr/local

3. install homebrew
 
