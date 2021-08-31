## Reproduction

GPG for Windows installed from: https://www.gpg4win.org/

Trying to run GPG decryption in a Python script using Python library `gnupg` and executed through Git Bash on Windows.


```python
import gnupg

gnupghome = r"C:\Users\npa\AppData\Roaming\gnupg"

gpg = gnupg.GPG(gnupghome=gnupghome, verbose=True)

with open(filename, "rb") as f:
    signed_data = gpg.decrypt_file(f, always_trust=True, passphrase=passphrase)
```


When running through Git Bash it fails to decrypt the file, using the option `verbose=True` shows this error:

```python
gpg: invalid size of lockfile 'C:\Users\npa\AppData\Roaming\gnupg/pubring.kbx.lock'
gpg: cannot read lockfile
gpg: can't lock 'C:\Users\npa\AppData\Roaming\gnupg/pubring.kbx'
```

## Understanding

When running the same script under CMD.exe, it works! So the issue is with Git Bash. 
Using `gpg --version` on both terminals, I noticed they didn't have the same "home".

It appears that Git Bash brings its own version of `gpg` instead of using the one installed manually.
The Python script running in Git Bash seems to use the one from Git Bash, even when setting the `gnupghome`!


## Solution

Thanksfully, `gnupg.GPG()` also includes  a `gpgbinary` argument, so after pointing it to the GPG I installed manually, it worked!

```python
import gnupg

gnupghome = r"C:\Users\npa\AppData\Roaming\gnupg"
gpgbinary = r"D:\GnuPG\bin\gpg.exe"

gpg = gnupg.GPG(gnupghome=gnupghome, verbose=True)

gpg = gnupg.GPG(gpgbinary=gpgbinary, gnupghome=gnupghome, verbose=True)
with open(filename, "rb") as f:
    signed_data = gpg.decrypt_file(f, always_trust=True, passphrase=passphrase)
```

