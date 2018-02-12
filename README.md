
# INFORMATION

List keys
```bash
$ gpg --list-keys
```

List all signatures
```bash
$ gpg --list-sigs
```

List fingerprints
```bash
$ gpg --fingerprint
```

List secret keys
```bash
$ gpg --list-secret-keys
```

How to prevent SHA1 usage?
https://www.apache.org/dev/openpgp.html#sha1

# EXPORT / IMPORT

Export public keys
```bash
# export all to cli
$ gpg --export --armor

# export single to cli
$ gpg --export --armor E43F742E

# export all to file
$ gpg --export --output export.asc --armor
```

Export all secret keys to file
```bash
$ gpg --export-secret-keys --armor --output ~/gpgroy/backup.sec
```

Import secret keys from file
```bash
$ gpg --import ~/gpgroy/backup.sec
```

# SIGNING

Edit a public key
```bash
$ gpg --edit-key rlenferink@apache.org
```

In the terminal, enter
```bash
gpg> fpr
```

Check the fingerprint and sign the key
```bash
gpg> sign
```

The key is signed, to check this execute
```bash
gpg> check
```

Quit gpg
```bash
gpg> q
```

# UPLOADING

To upload a key to a keyserver, execute
```bash
$ gpg --send-keys E43F742E
$ gpg --keyserver <keyserver here> --send-key E43F742E
```

# VALIDATING

```bash
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys <fingerprint without spaces here>

# e.g.
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 2F8B75551BAF4A693C1A7F9A8C7B8F00E43F742E
```

# DECRYPTING

```bash
$ gpg --output doc --decrypt doc.gpg
```
