# Encryption, decryption, and cracking

One of the earliest encryption techniques is the Caesar Cipher, invented by Julius Caesar more than two thousand years ago to communicate messages to his allies.

### Encrypting a message

Imagine Caesar wants to send this message:

    SECRET MEETING AT THE PALACE

Here's what that might look like encrypted:

    YKIXKZ SKKZOTM GZ ZNK VGRGIK


That looks an awfully lot like gobbledygook at first, but this encrypted message is actually very related to the original text.

The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount. 

# Caesar cipher

cryptography, a Caesar cipher, also known as Caesar’s cipher, the shift cipher, Caesar’s code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

The encryption step performed by a Caesar cipher is often incorporated as part of more complex schemes, such as the Vigenère cipher, and still has modern application in the ROT13 system. As with all single-alphabet substitution ciphers, the Caesar cipher is easily broken and in modern practice offers essentially no communications security.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4a/Caesar_cipher_left_shift_of_3.svg/220px-Caesar_cipher_left_shift_of_3.svg.png)


### Example

he transformation can be represented by aligning two alphabets; the cipher alphabet is the plain alphabet rotated left or right by some number of positions. For instance, here is a Caesar cipher using a left rotation of three places, equivalent to a right shift of 23 (the shift parameter is used as the key):

![](https://www9.0zz0.com/2021/06/28/15/562470362.png)

### History and usage

The Caesar cipher is named after Julius Caesar, who, according to Suetonius, used it with a shift of three (A becoming D when encrypting, and D becoming A when decrypting) to protect messages of military significance. While Caesar’s was the first recorded use of this scheme, other substitution ciphers are known to have been used earlier.

In April 2006, fugitive Mafia boss Bernardo Provenzano was captured in Sicily partly because some of his messages, clumsily written in a variation of the Caesar cipher, were broken. Provenzano’s cipher used numbers, so that “A” would be written as “4”, “B” as “5”, and so on.