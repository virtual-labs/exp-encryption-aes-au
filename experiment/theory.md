### Theory

### AES Encryption Process

The Advanced Encryption Standard (AES) is a symmetric block cipher widely used for securing digital data. It operates on fixed-size blocks of 128 bits and supports key sizes of 128, 192, and 256 bits, commonly referred to as AES-128, AES-192, and AES-256. 

AES uses a substitution–permutation network (SPN) structure, which provides strong security through multiple rounds of nonlinear and linear transformations.

The number of rounds depends on the key size:

- 128-bit keys: 10 rounds
- 192-bit keys: 12 rounds
- 256-bit keys: 14 rounds

The AES encryption process begins with key expansion, which derives round keys from the original key. 

These round keys are used in each round to ensure that even small changes in the key or input result in completely different ciphertext, enhancing security.

The encryption process consists of the following five main steps:

1. **Initial AddRoundKey**: The plaintext is XORed with the first round key
2. **SubBytes**: Each byte of the state is replaced with a value from the S-box (substitution box), introducing nonlinearity into the cipher
3. **ShiftRows**: Rows of the state are shifted by different offsets, providing diffusion across columns
4. **MixColumns**: Columns of the state are mixed using matrix multiplication in the finite field GF(2⁸), further enhancing diffusion
5. **AddRoundKey**: The state is XORed with the current round key

These five steps are repeated for each round. In the final round, the MixColumns operation is omitted to ensure that encryption and decryption operations can use the same structure, with only the key schedule applied in reverse order.

#### Final Round
The final round omits the MixColumns step to simplify the decryption process. It includes SubBytes, ShiftRows, and AddRoundKey.
