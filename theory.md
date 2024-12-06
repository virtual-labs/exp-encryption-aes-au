### Theory

### AES Encryption Process
AES (Advanced Encryption Standard) is a symmetric encryption algorithm widely used for securing sensitive data. It operates on fixed-size blocks of data and supports key sizes of 128, 192, or 256 bits. Here's a detailed explanation of the AES encryption process.

### Key Expansion
The first step in AES encryption is key expansion. The original key is expanded into a key schedule, which is an array of round keys. Each round key is derived from the previous one through a series of transformations. The number of rounds depends on the key size: 10 rounds for 128-bit keys, 12 rounds for 192-bit keys, and 14 rounds for 256-bit keys.

### Initial Round Key Addition
The input plaintext is divided into blocks, and the first round key is added to the plaintext using bitwise XOR (exclusive OR) operation. This provides an initial mixing of the key with the plaintext.

### Rounds
AES operates on data in a series of rounds. Each round consists of four transformations: SubBytes, ShiftRows, MixColumns, and AddRoundKey.

#### SubBytes
SubBytes is a byte substitution step where each byte of the block is replaced with a corresponding byte from the S-box, a pre-defined substitution table.

#### ShiftRows
In the ShiftRows step, the rows of the block are shifted by varying offsets. For a 128-bit block, the first row remains unchanged, the second row is shifted one position to the left, the third row is shifted two positions, and the fourth row is shifted three positions.

#### MixColumns
MixColumns is a column-wise mixing operation that provides diffusion in the data. Each column of the block is multiplied with a fixed polynomial, and the result is XORed to obtain the new column values.

#### AddRoundKey
AddRoundKey XORs each byte of the block with the corresponding byte of the round key. This step introduces the current round key into the state.

#### Final Round
The final round omits the MixColumns step to simplify the decryption process. It includes SubBytes, ShiftRows, and AddRoundKey.
