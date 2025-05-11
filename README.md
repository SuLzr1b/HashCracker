# Hash Cracker Script

## Overview
This Python script is designed to crack passwords by comparing hashed inputs against a provided wordlist. It supports three types of hashing algorithms: MD5, SHA1, and Base64 encoding. The script reads a wordlist file, hashes each entry, and checks if it matches the provided hash, displaying the results with colored output for better readability.

## Features
- **Supported Hash Types**: MD5, SHA1, and Base64.
- **Wordlist Support**: Accepts a text file containing potential passwords (one per line).
- **Colored Output**: Utilizes the `colorama` library to display success (green) and failure (red) messages.
- **Command-Line Interface**: Takes a wordlist file as an argument and prompts the user for the hash and hash type.
- **Cross-Platform**: Uses `os.system('clear')` for clearing the terminal (works on Unix-like systems; may need adjustment for Windows).

## Prerequisites
Before running the script, ensure you have the following installed:
- Python 3.x
- Required Python libraries:
  - `colorama` (for colored terminal output)
  - `hashlib` (built-in, for MD5 and SHA1 hashing)
  - `base64` (built-in, for Base64 encoding)
  - `os` and `sys` (built-in, for system operations and argument handling)

## Usage
1. **Prepare a Wordlist**: Create a text file (e.g., `wordlist.txt`) with one password per line.
2. **Run the Script**:
   ```bash
   python3 hash.py wordlist.txt
   ```
3. **Input the Hash**: Enter the hash you want to crack when prompted.
4. **Select Hash Type**:
   - `1` for MD5
   - `2` for SHA1
   - `3` for Base64
5. **View Results**: The script will iterate through the wordlist, displaying whether each password matches the provided hash.

### Example
```bash
$ python3 hash.py wordlist.txt
     .'(     /`-.     )\.--.       .'(     /`-.   .'(       /(,-.  
 ,') \  )  ,' _  \   (   ._.'  ,') \  )  ,' _  \ /_  )    ,' _   ) 
(  '-' (  (  '-' (    `-.`.   (  '-' (  (  '-' (  ) (    (  '-' (  
 ) .-.  )  )   _  )  ,_ (  \   ) .-.  )  ) ,_ .'  \  )    )  _   ) 
(  ,  ) \ (  ,' ) \ (  '.)  ) (  ,  ) \ (  ' ) \  _) \_  (  '-' /  
 )/    )/  )/    )/  '._,_.'   )/    )/  )/   )/ )__,__/  )/._.'   
 
                            By: SuLr1b
                                     CODE

DIGITE A HASH: 5f4dcc3b5aa765d61d8327deb882cf99
TIPOS DE HASHS:
[1]  MD5        [2]  SHA1
[3]  BASE64

TIPO DA HASH: 1

[!!?] PASSWORD INVALID: admin
[!!?] PASSWORD INVALID: user
[*] PASSWORD CRACKED: password
```

## Code Explanation
The script is structured as follows:

### Imports
- `hashlib`: Provides MD5 and SHA1 hashing functions.
- `base64`: Handles Base64 encoding.
- `os`: Used for clearing the terminal.
- `sys`: Processes command-line arguments.
- `time.sleep`: Adds a slight delay between checks for readability.
- `colorama`: Enables colored terminal output.

### Functions
- `Md5(text)`: Computes the MD5 hash of the input text.
- `Sha1(text)`: Computes the SHA1 hash of the input text.
- `Bas64(text)`: Encodes the input text in Base64.

### Main Logic
1. **Argument Check**: Ensures a wordlist file is provided as a command-line argument.
2. **File Reading**: Opens and reads the wordlist file line by line.
3. **User Input**:
   - Prompts for the hash to crack.
   - Asks for the hash type (1 for MD5, 2 for SHA1, 3 for Base64).
4. **Hash Comparison**:
   - Iterates through each word in the wordlist.
   - Computes the hash of the word using the selected algorithm.
   - Compares it with the provided hash.
   - Prints whether the password is valid or invalid.
   - Stops if a match is found.
5. **Base64 Handling**: Includes additional string manipulation to clean up the Base64 output for comparison.

### Error Handling
- If no wordlist is provided, it displays usage instructions.
- If an invalid hash type is selected, it prints an error message.

## Limitations
- **Base64 Comparison**: The script performs string manipulation to clean Base64 output, which may not handle all edge cases.
- **Performance**: The script is not optimized for large wordlists, as it processes each word sequentially.
- **Base64 as a Hash**: Base64 is an encoding scheme, not a cryptographic hash, so its inclusion as a "hash type" is technically inaccurate.

## Improvements
- Add support for more hash types (e.g., SHA256, bcrypt).
- Implement multithreading for faster processing of large wordlists.


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author
By **SuLr1b**
