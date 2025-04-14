# Bitcoin BIP39 Seed Generator (Dice Method)

A secure, offline web tool for generating Bitcoin BIP39 seed phrases using physical dice rolls as an entropy source. This tool allows you to create cryptographically secure seed phrases for Bitcoin and other cryptocurrency wallets while maintaining full transparency of the generation process.

## Features

- Generate 12, 18, or 24-word BIP39 seed phrases
- Uses physical dice rolls as entropy source
- Full transparency of the entropy-to-seed conversion process
- Detailed checksum calculation display
- Real-time binary conversion visualization
- Comprehensive BIP39 compliance verification
- Offline capable - can be downloaded and run locally

## Security Features

- All calculations performed client-side
- No external dependencies or API calls
- Can be used on an air-gapped computer
- Source code is fully readable and verifiable
- Complete transparency of the seed generation process
- Implements BIP39 specification exactly

## How It Works

1. **Entropy Generation**
   - 12 words: 128 bits (121 from dice + 7 checksum)
   - 18 words: 192 bits (186 from dice + 6 checksum)
   - 24 words: 256 bits (253 from dice + 3 checksum)

2. **Dice to Binary Conversion**
   - Each die roll provides 1 bit of entropy
   - Rolls 1-3 → binary 0
   - Rolls 4-6 → binary 1

3. **Checksum Process**
   - SHA256 hash of entropy bits
   - First N bits used as checksum (where N = entropy_length ÷ 32)
   - Checksum appended to entropy bits

4. **Word Generation**
   - Combined bits split into 11-bit segments
   - Each 11-bit segment maps to a word from BIP39 word list
   - Final word includes checksum bits

## Why Use Dice?

Physical dice provide true random entropy, unlike computer-generated random numbers which are technically pseudo-random. Benefits include:

1. **True Randomness**: Physical dice provide genuine randomness from the real world
2. **No Digital Trace**: The entropy source never touches a computer's memory
3. **Visual Verification**: You can see and verify each source of entropy
4. **Immune to Software Bugs**: No reliance on computer random number generators
5. **Offline Security**: Complete air-gap capability

## Entropy Requirements

| Seed Length | Total Bits | Entropy Bits | Checksum Bits | Dice Rolls Needed |
|-------------|------------|--------------|---------------|-------------------|
| 12 words    | 128 bits   | 121 bits     | 7 bits        | 121 rolls        |
| 18 words    | 192 bits   | 186 bits     | 6 bits        | 186 rolls        |
| 24 words    | 256 bits   | 253 bits     | 3 bits        | 253 rolls        |

## Usage

1. Select desired seed length (12, 18, or 24 words)
2. Roll physical dice and enter values (1-6) in each box
3. Values auto-advance as you type
4. Click "Generate" when all rolls are entered
5. Verify the generated seed phrase
6. Save your seed phrase securely

## Security Recommendations

1. Use on an air-gapped computer
2. Clear browser cache after use
3. Use a clean/secure environment
4. Never share your seed phrase
5. Make secure backups of generated seeds
6. Verify the seed works before using it with real funds

## Technical Details

- Implements BIP39 specification
- Uses SHA256 for checksum generation
- Includes full BIP39 word list
- Performs comprehensive seed verification
- Shows detailed entropy and checksum calculations

## Important Links

- [BIP39 Specification](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)
- [Official BIP39 Word List](https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt)
- [BIP39 Test Vectors](https://github.com/trezor/python-mnemonic/blob/master/vectors.json)
- [Bitcoin Improvement Proposals (BIPs)](https://github.com/bitcoin/bips)

## Verification Process

The tool verifies:
1. Correct seed length (12/18/24 words)
2. All words present in BIP39 word list
3. Valid checksum matching entropy
4. Proper entropy-to-binary conversion
5. Correct word mapping from binary

## Local Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/bitcoin-bip39-dice-generator.git
   ```

2. Open `index.html` in a web browser
   - No server required
   - No build process needed
   - Works completely offline

## Files

- `index.html` - Main application file
- `bip39.js` - BIP39 wordlist and SHA256 implementation
- `README.md` - This documentation

## License

MIT License - See LICENSE file for details

## Disclaimer

This tool is provided as-is. Always verify generated seeds with a small test amount before using them with significant funds. The authors are not responsible for any lost funds.