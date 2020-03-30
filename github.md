## setting up ssh

```
$ ssh-keygen -t rsa -b 4096 -C "d.santos.nuno@gmail.com"
```

add to ssh config ~/.ssh/config

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```

add public key to https://github.com/settings/keys

run agent

```
$ eval "$(ssh-agent -s)"
$ ssh-add -K ~/.ssh/id_rsa
```

test 

```
$ ssh -T git@github.com
```

## links

* https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent





