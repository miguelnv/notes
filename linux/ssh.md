SSH configuration with keys -> (public/private)

1. Generate keys on client host (generate passphrase and save it to bitwarden)
```
> ssh-keygen -t ed25519
```

2. Send public key to server (will be delete afterwards)
```
> scp ~./ssh/id_amun.pub admin@amun:/home/admin/
```

3. Server side
```
> chmod -R 700 ~/.ssh
> cat ~/id_amun.pub >> ~/.ssh/authorized_keys
> rm  ~/id_amun.pub


---Permit only key login---
> sudo vi /etc/init.d/sshd_config
PasswordAuthentication no
ChallengeResponseAuthentication no
```

4. Client side
```
> vi ~/.ssh/config
Host amun
User admin
IdentityFile ~/.ssh/id_amun

> ssh -v admin@amun (should ask for the passphrase)

```
