- Run the following step to see whether you have exisitng gpg keys in terminal

```
gpg --list-secret-keys --keyid-format=long
```

If it exists, you would get result shown below:

```
[keyboxd]
---------
sec   ed25519/key_id [SC] [expires: 2026-12-19]
      number_id
uid                 [ unknown] name (cooment) <email>
```
- Then you can export the public gpg key which we need to copy to gitub personal setting

```
gpg --armor --export  key_id
```
You would get the result shown below

```
-----BEGIN PGP PUBLIC KEY BLOCK-----
mDMEZYKs+hYJKwYBBAHaRw8BAQdA/+2y/p...
Abg4BGWCrPoSCisGAQQBl1UBBQEBB0BUI/bkZgFCEzJqT1Nw6dr6p7PDj+Bt5GCB
U7Se0MmCO1bQAP9+dsFkbuEBkgYHC45IuTmUdHrBMDS75ixyh10b3YuuBg==
=6+rP
-----END PGP PUBLIC KEY BLOCK-----
```
- copy it to your gitub account gpg keys
- edit your local github files
- `ggp --sign files` or `git commit -s -m "your commit message"` after adding them into the stage

if you meet the following errors:
```
error: gpg failed to sign the data
fatal: failed to write commit object
```
You might want to try running `export GPG_TTY=$(tty)`. If it works,  you can add it to '~/.bashrc'.
- after sign it andd commit it, you can push it.
- navigate to the github commit then check whether the commit is shown as 'verified'

## Help Doc
<a href='https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification'> Commit signature verification </a>

