
Write a program in Python with one class called Cipher.Within the constructor of this class, ask user for a string and store it. Use a static variable, key to store a randomly generated integer between 1 and 50 inclusive. Implement two methods, encrypt and decrypt within this class. Encrypt generates and prints a cipher text using the user-entered string and the key and decrypt generates decrypted string from ciphertext. The cipher only encrypts alpha and numeric (A-Z, a-z, 0-9). All Symbols, such as - , ; %, remain unencrypted. The cipher text can have special characters. Use generator expression to filter out alpha and numeric characters of the input string and to generate cipher text. Create an instance of this class, encrypt and decrypt back the user entered string.


```python
import numpy as np
class Cipher:
    L2I = dict(zip("ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789",range(62)))
    I2L = dict(zip(range(62),"ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"))
    
    def __init__(self,instr=""): 
        self.Instr=str(input("Enter the input string"))
        
    def encrypt(self,key):
        ciphertext = ""
        Instr=self.Instr
        for c in Instr:
            if c.isalnum(): 
                ciphertext += self.I2L[ (self.L2I[c] + key)%62 ]
            else: 
                ciphertext += c
        return ciphertext
    
    def decrypt(self,Enstr,key):
        plaintext2 = ""
        for c in Enstr:
            if c.isalnum(): plaintext2 += self.I2L[ (self.L2I[c] - key)%62]
            else: plaintext2 += c
        return plaintext2

k=np.random.randint(1,50,1)
key=k[0]
c=Cipher()
encryptstr=c.encrypt(key)
decryptstr=c.decrypt(encryptstr,key)
print("\n Input String is :\t"+c.Instr)
print("\nEncryption vaue of given string is :\t"+encryptstr)
print("\nDecryption vaue of given string is :\t"+decryptstr)
```

    Enter the input stringmamatha.mba26@gmail.com
    
     Input String is :	mamatha.mba26@gmail.com
    
    Encryption vaue of given string is :	G4G4NB4.G54Wa@AG4CF.6IG
    
    Decryption vaue of given string is :	mamatha.mba26@gmail.com
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
