# SSH keys
## Public key
The public key is safe to share.

You upload it to GitHub or GitLab:
```
GitHub/GitLab account
    ↑
stores your PUBLIC KEY
```


## Private key
The private key stays on your computer.
```
Your laptop
    ↓
keeps PRIVATE KEY secret
```
**Never** upload the private key to GitHub, GitLab, email, Slack, etc.

A **passphrase** is an extra password that protects your private key.

If an attacker steals only the private key file, they still **cannot** use it without knowing the passphrase.



## What happens when you push?

- GitHub/GitLab sends a random **challenge** and says: Prove you are the owner of this account.

- Your computer uses the **private key** to sign the **challenge** and send back a **signature**.

- GitHub/GitLab uses your **public key** to verify that the **signature** could **only** have been created by the **matching private key**.

- If they match, access is granted.


## Why can't GitHub just derive the private key from the public key?
Because the math is deliberately designed to be **one-way**.

It's easy to do:
```
Private Key → Public Key
```

but practically impossible to do:
```
Public Key → Private Key
```

This is similar to how:
```
2 × 3 = 6 -> easy
6 = ? × ? -> hard
```




