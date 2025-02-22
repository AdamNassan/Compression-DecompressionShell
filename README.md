# Shell-Scripting-Compression-and-Decompression

This project implements a simple dictionary-based compression and decompression tool using shell scripting. The tool performs lossless data compression by assigning unique binary codes to words and substituting these codes in the compressed file.

## Project Overview

The dictionary-based compression technique identifies patterns in data and replaces them with shorter codes. Key features of this implementation include:

- **Binary Codes:** Each word in the uncompressed file is assigned a unique 16-bit binary code.
- **Unicode Support:** The uncompressed file contains Unicode characters (16 bits per character).
- **Dictionary:** The dictionary is stored in a `dictionary.txt` file and evolves with repeated compression operations.
- **Case Sensitivity:** Compression and decompression are case-sensitive.
- **Special Characters:** Treated as words, with each assigned a unique code.

### Example

#### Input Text:


#### Generated Dictionary:

| Code     | Word         |
|----------|--------------|
| 0x0000   | We           |
| 0x0001   | Space ‘ ’    |
| 0x0002   | are          |
| 0x0003   | studying     |
| 0x0004   | computer     |
| 0x0005   | architecture |
| 0x0006   | .            |
| ...      | ...          |

#### Compression:

- **Uncompressed File Size:** 2560 bits (320 bytes)
- **Compressed File Size:** 784 bits (98 bytes)
- **Compression Ratio:** 3.265

## Program Features

### Dictionary Management
- Check for the existence of `dictionary.txt`.
- Load an existing dictionary or create a new one.

### Compression
- Replace words with codes from the dictionary.
- Add new words to the dictionary as encountered.
- Compute and display the compression ratio.
- Save compressed data and update the dictionary.

### Decompression
- Replace codes in the file with corresponding words from the dictionary.
- Display error messages for missing codes.
- Save decompressed data.

## Program Flow

### 1. Program Menu
- Prompt the user to indicate whether `dictionary.txt` exists.
- Load or create the dictionary.

### 2. Compression
- Accept the file path for compression.
- Compress the file using the dictionary.
- Append new words to the dictionary.
- Save the compressed file and updated dictionary.
- Display the compression ratio.

### 3. Decompression
- Accept the file path for decompression.
- Validate codes against the dictionary.
- Decompress the file and save the uncompressed data.


### Program Options
- **Compression:** Enter `c`, `compress`, or `compression`.
- **Decompression:** Enter `d`, `decompress`, or `decompression`.
- **Case-insensitive options:** Supported.

### Outputs
- **Compressed File:** Contains binary codes for words.
- **Uncompressed File:** Reconstructed text from the compressed file.
- **Updated Dictionary:** Includes new words encountered during compression.
