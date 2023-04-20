# Crypto

### Ciphers

Stream cipher is when the plain text is combined with a digital stream (keystream), where each bit is encrypted one at the time, with the corresponding digit of the keystream.\
Block cipher key is used to encrypt a block of data as a group instead one bit at the time.

| Type                        | Initialization vector | Error propagation |
| --------------------------- | --------------------- | ----------------- |
| Electornic code book (ECB)  | Block                 | No                |
| Cipher block chaining (CBC) | Block                 | Yes               |
| Cipher feedback (CFB)       | Stream                | Yes               |
| Output feedback (OFB)       | Stream                | Yes               |
| Counter mode (CTR)          | Stream                | Yes               |

## Bitwise operation

I will just start with some basic bitwise operation, that is the corner stone logic for crypto operations.

### AND

The out is true only if both of the input are true.

**True table**

| and |   |   |   |
| --- | - | - | - |
|     | 0 | 1 |   |
| 0   | 0 | 0 |   |
| 1   | 0 | 1 |   |

### NOT

Not operand is and simple inverter give it a 0 it will turn it into 1 and give 1 and it will become an 0

**True table**

| not |   |   |   |
| --- | - | - | - |
| 0   | 1 |   |   |
| 1   | 0 |   |   |

### OR

The rule is that the outcome is true if either or both of the inputs are true.

**True table**

| OR |   |   |   |
| -- | - | - | - |
|    | 0 | 1 |   |
| 0  | 0 | 1 |   |
| 1  | 1 | 1 |   |

### XOR

Work very similar to _or_, it comes out as true if either one of the inputs is one. If they are both 1, it comes out as 0 which is why it called exclusive.\
Another way of putting is, the outcome is _one_ if the two input differ, otherwise it _zero_

Logic table

| XOR |   |   |   |
| --- | - | - | - |
| A   | 0 | 0 | 1 |
| B   | 0 | 1 | 0 |
| XOR | 0 | 1 | 1 |

**True table**

| XOR |   |   |
| --- | - | - |
|     | 0 | 1 |
| 0   | 0 | 1 |
| 1   | 1 | 0 |

#### Salsa20

Salsa20 uses a fixed-length key and a fixed-length nonce (a number that is used only once) to encrypt and decrypt data. The key and nonce are used to initialize a state array, which is then used to generate a keystream that is combined with the plaintext (in the case of encryption) or the ciphertext (in the case of decryption) to produce the encrypted/decrypted output.

The algorithms can be recognized based on the constant iteration with two strings.

**pseudocode**

Main component of the algoritm is the QuaterRound with takes 4 word input and produces 4 word output

```
Define QR(a, b, c, d)
( b ^= ROTL(a + d, 7)
c ^= ROTL(b + a, 9)
d ^= ROTL(c + b,13)
a ^= ROTL(d + c,18))
```

### Asymmetric algorithm

#### RSA

It every common for authors to use the WinCrypt API as it simple, reliable and secure

**Math**

```
c = ciphertext
p and q = prime numbers
n = p * q
phi = (p1)*(q1)  
d = inverse(e, phi)  
m = pow(c,d,n)
```

**Weakness**

Small e value can be a problem, the same goes for the n value if the n value is small we can figure out what the two prime number that was multiplied together to the result, sites like factordb.com can help with this problem.

#### Elliptic Curve (ECC)

Because of the difficult of writing the algorithm correctly, you are usually be able to find the open source repository that was used to implement the algorithm, e.g. [curve25519donna](https://github.com/agl/curve25519donna)
