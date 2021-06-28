# Linux commands & tools

## vim

### P: Sorry, the command is not available in this version...

Probably don't have the full verison of vim installed.

    readlink -f `which vi`
    sudo apt install vim

### vim plugins

**vim-plug**: git@github.com:junegunn/vim-plug.git

Install powerline fonts

    sudo apt install fonts-powerline

## git

### Show all files in a commit

    git diff-tree --no-commit-id --name-only -r 64606fcb

### Change file and directory permissions

    find . -type f -perm 777 -exec chmod 644 {} \;
    find . -type d -perm 777 -exec chmod 755 {} \;
