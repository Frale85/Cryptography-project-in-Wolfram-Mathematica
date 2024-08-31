Project Goals for Master (postgraduate course)

The goals of this project are:
• to write a simple ARX (Addition-Rotation-Xor network) cipher in the
Wolfram Language,
• to verify the implementation by testing on the series of given
encryption vectors.
Introduction

ARX ciphers are recently adopted at the lightweight cryptography as a
design choice for multiple reasons: they are fast, they ease
implementation at hardware level, they use mostly linear operations and
non-linear operations are given by modular addition.
Detailed Description
The goal in this challenge is to provide a cryptographic system by
programming Encryption/Decryption functions of the SPECK32/64 cipher.
Speck supports a variety of block and key sizes. A block is always two words, but the words
may be 16, 24, 32, 48 or 64 bits in size. The corresponding key is 2, 3 or 4 words. The round
function consists of two rotations, adding the right word to the left word, xoring the key into the
left word, then xoring the left word into the right word. The number of rounds depends on the
parameters selected, as follows:

The key schedule uses the same round function as the main block cipher.
Block size (bits) Key size (bits) Rounds
2×16 = 32 4×16 = 64 22
2×24 = 48

3×24 = 72 22
4×24 = 96 23

2×32 = 64

3×32 = 96 26
4×32 = 128 27

2×48 = 96

2×48 = 96 28
3×48 = 144 29

2×64 = 128

2×64 = 128 32
3×64 = 192 33
4×64 = 256 34

Separate the round function implementation by the overall application to combine the
keyschedule with the current state.
Note that the round function takes 3 input words and returns 2 words.
In the keyschedule one of the inputs is the number of the current round (it is also called counter
mode).
