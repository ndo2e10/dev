## Connecting to GitHub with SSH

```
$ ssh-keygen -t rsa -b 4096 -C "xxx@gmail.com"
```

* add to ssh config ~/.ssh/config

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```

* add public key to https://github.com/settings/keys

* run agent

```
$ eval "$(ssh-agent -s)"
$ ssh-add -K ~/.ssh/id_rsa
```

* test 

```
$ ssh -T git@github.com
```

## links

* https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line
* https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


