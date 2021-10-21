# RC4-Algorithm
A Python implementation of the RC4 Algorithm


RC4 is a symmetric stream cipher and variable key length algorithm
RC4 generates a pseudo-random stream of bits (a key-stream).
As with any stream cipher, these can be used for encryption by combining it with the plaintext using bit-wise exclusive-or.
Decryption is performed the same way (since exclusive-or is asymmetric operation).


** Used in popular protocols like Secure Sockets Layer (SSL) (to protect Internet traffic) and WEP (to secure wireless networks)

** important to note it's not reccomended now due to vulnerabilities

** Stream Cipher: encryption algorithm that uses a symmetric key to encrypt and decrypt a given amount of data

** XOR: takes two boolean operands and returns true if and only if the operands are different


This algorithm encrypts one byte at a time (or larger units at a time).


A key input is pseudorandom bit generator that produces a stream 8-bit number that is unpredictable without knowledge of input key, The output of the generator is called key-stream, is combined one byte at a time with the plaintext stream cipher using X-OR operation.


****** SIMPLIFIED HOW RC4 WORKS ******

** PART 1: Key-Generation Algorithm **

.. A variable-length key from 1 to 256 bytes is used to initialize a 256-byte state vector S, with elements S[0] to S[255]

.. For encryption and decryption, a byte k is generated from S by selecting one of the 255 entries in a systematic fashion, then the entries in S are permuted again.

** PART 2: Key-Scheduling Algorithm Initialisation **

.. The entries of S are set equal to the values from 0 to 255 in ascending order, a temporary vector T, is created.

.. If the length of the key k is 256 bytes, then k is assigned to T.

.. Otherwise, for a key with length(k-len) bytes, the first k-len elements of T as copied from K, and then K is repeated as many times as necessary to fill T.

.. we use T to produce the initial permutation of S. Starting with S[0] to S[255], and for each S[i] algorithm swap it with another byte in S according to a scheme dictated by T[i], but S will still contain values from 0 to 255

** PART 3: Pseudo Random Generation Algorithm (Stream Generation) **

.. Once the vector S is initialized, the input key will not be used. 

.. In this step, for each S[i] algorithm swap it with another byte in S according to a scheme dictated by the current configuration of S.

.. After reaching S[255] the process continues, starting from S[0]

  

