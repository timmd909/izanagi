# Client Installation instructions

## TLDR What To Do

Before doing anything else, set a `borg_passphrase` in the
client's `host_vars/` config file.

Once the new passphrase has been noted, do the following:

```bash
mount -t sshfs alexandria:/media/repositories/$HOSTNAME /mnt
borg init --encryption=repokey /mnt
```

## History Note

The old passphrases weren't that great. Do not be lazy again.
