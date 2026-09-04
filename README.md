# pub

Public keys for geoffrey-oongo. Everything here is public by design — no private key
material belongs in this repo.

## Files

| File | What it is |
|---|---|
| `authorized_keys` | All SSH public keys, ready to append to a server's `~/.ssh/authorized_keys` |
| `ssh_ed25519.pub` | ed25519 key (`geoffreyoongo@gmail.com`) — preferred |
| `ssh_rsa.pub` | older RSA key (`oongo@MacBookPro`) |

## Install on a server

Run this **on the server**, as the user you want to log in as:

```sh
mkdir -p ~/.ssh && chmod 700 ~/.ssh
curl -fsSL https://raw.githubusercontent.com/geoffrey-oongo/pub/main/authorized_keys \
  >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

Only the ed25519 key:

```sh
curl -fsSL https://raw.githubusercontent.com/geoffrey-oongo/pub/main/ssh_ed25519.pub \
  >> ~/.ssh/authorized_keys
```

If you can still get in with a password, you can push from your laptop instead:

```sh
ssh-copy-id -i ~/.ssh/id_ed25519.pub root@SERVER
```
