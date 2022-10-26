SSH configuration with keys -> (public/private)

1. Generate keys on client host (generate passphrase and save it to bitwarden)
```
> ssh-keygen -t ed25519
```

2. Send public key to server (will be delete afterwards)
```
> scp ~./ssh/id_amun.pub admin@amun:/home/admin/
```

2. On server (will be delete afterwards)
```
> chmod -R 700 ~/.ssh
> cat ~/id_amun.pub >> ~/.ssh/authorized_keys
> rm  ~/id_amun.pub
```

3. Debug it
```
> ssh -v admin@amun
```
