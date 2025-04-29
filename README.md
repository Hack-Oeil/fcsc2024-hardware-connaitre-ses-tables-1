# FCSC 2024 Connaître ses tables 1/2

Benoît Blanc pense avoir réussi à cacher sa clef AES dans des tables.

Il vous fournit le code écrit en C permettant de chiffrer des messages avec cette clef, par exemple :

```shell
$ make
$ ./wb-aes keys.bin < /dev/zero
f34789150f962bdcc56e8c585451f34d
```

Il a chiffré le flag à l’aide du SHA256 de cette clef (voir output.txt) :

```python
def encrypt(k, flag):
    import hashlib
    from Crypto.Cipher import AES
    hk = hashlib.sha256(k).digest()
    E = AES.new(hk, AES.MODE_GCM)
    iv = E.nonce
    c = E.encrypt(flag)
    return {"c": c.hex(), "iv": iv.hex()}
```

Fichiers :
- [connaitre-ses-tables-easy.tar.xz](connaitre-ses-tables-easy.tar.xz)


Auteur : Neige

Origine : [Connaître ses tables 1/2](https://hackropole.fr/fr/challenges/hardware/fcsc2024-hardware-connaitre-ses-tables-1/)


-----------


## Installation manuel
Vous n'utilisez pas l'application **les CTFs de Cyrhades** ? C'est dommage !
Mais voici comment installer ce CTF manuellement :

> git clone https://github.com/Hack-Oeil/fcsc2024-hardware-connaitre-ses-tables-1.git

> cd fcsc2024-hardware-connaitre-ses-tables-1

-----------

## Sur le site officiel hackropole.fr
> https://hackropole.fr/fr/challenges/hardware/fcsc2024-hardware-connaitre-ses-tables-1/