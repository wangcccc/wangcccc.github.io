# Linux commands & tools

## vim

### P: Sorry, the command is not available in this version...

Probably don't have the full verison of vim installed.

```shell
readlink -f `which vi`
sudo apt install vim
```

### vim plugins

**vim-plug**: git@github.com:junegunn/vim-plug.git

Install powerline fonts

```shell
sudo apt install fonts-powerline
```

## git

### Show all files in a commit

```shell
git diff-tree --no-commit-id --name-only -r 64606fcb
```

### Change file and directory permissions

```shell
find . -type f -perm 777 -exec chmod 644 {} \;
find . -type d -perm 777 -exec chmod 755 {} \;
```

### Ignore file by setting git exclude

Add ignorance rules to `.git/info/exclude`

## Shadowsocks

### config on Debian and Ubuntu

```shell
wget https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh
chmod +x shadowsocks-libev-debian.sh
./shadowsocks-libev-debian.sh
```
