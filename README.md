# dotfiles
Set up a new machine with a single command

You can install your dotfiles on new machine with a single command:
```
$ chezmoi init --apply https://github.com/$GITHUB_USERNAME/dotfiles.git
```

A better way that installs the chezmoi cli as well
```
export GITHUB_USERNAME=tsweets
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply $GITHUB_USERNAME
```

Create encrypted archive of dot ssh and decrypt
``` 
tar -cvzf - ~/.ssh | gpg -c > /tmp/dot-ssh.tar.gz.gpg
gpg -d dot-ssh.tar.gz.gpg | tar -xvzf -
```
Note: Above cmd presents a directory issue that needs to cleaned up

Debian Notes:

- Need to Add user to sudo
```
sudo usermod -aG sudo username
````

