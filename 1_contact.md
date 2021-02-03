---
layout: default
title: Contact
permalink: /contact/
---

Use the python script below to decrypt my email:

mail: Z6WX6Z692@4Ya2Z.8WY


-----------------------------------------------------------------------

```python:
encrypted = b"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789 "
decrypted = b"a9876543210ZYXWVUTSRQPONMLKJIHGFEDCBAzyxwvutsrqponmlkjihgfedcb "


encryption_base = bytes.maketrans(decrypted, encrypted)
decryption_base = bytes.maketrans(encrypted, decrypted)

decision = 0

while decision == 0: 

    decision = input("Type 1 to decrypt or 2 to encrypt:")
    if decision == "1":
        message = input("Type message to decrypt: ")
        print(message.translate(encryption_base))
        decision = 0

    if decision == "2":
        message = input("Type message to encrypt: ")
        print(message.translate(decryption_base))
        decision = 0
    
    if decision == "quit":
        break
```
-----------------------------------------------------------------------