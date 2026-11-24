
# Classical Ciphers in Java

A Java console application implementing two classical cipher techniques: **Single Letter Grilles** and **Tap Code**.

Developed as part of a Data Security course, this project demonstrates fundamental concepts of text encoding, decoding, and classical cryptography using Java.

## Features

- Encode and decode messages using Tap Code.
- Encrypt and decrypt text using a spiral-based Single Letter Grilles algorithm.
- Interactive command-line interface.
- Automatic conversion of input text to uppercase.
- Demonstration of the original message and its reconstructed form.
- No external libraries required.

## Technologies Used

- Java
- Object-Oriented Programming (OOP)
- Two-dimensional arrays
- HashMap and Map collections
- String manipulation
- IntelliJ IDEA

## Algorithms

### 1. Single Letter Grilles

Single Letter Grilles is implemented as a spiral-based transposition technique.

The algorithm places characters into a square matrix, following a clockwise spiral pattern.

**Encryption process:**

1. Calculate the required square matrix size based on the message length.
2. Initialize the matrix with underscore (`_`) characters.
3. Insert the message characters following a clockwise spiral.
4. Read the matrix row by row to produce the encrypted text.

**Decryption process:**

1. Reconstruct the square matrix from the encrypted message.
2. Read the characters following the original spiral pattern.
3. Remove padding characters to recover the message.

This algorithm demonstrates how changing character positions can transform a message without changing the characters themselves.

### 2. Tap Code

Tap Code is a classical communication and encoding technique based on a **5 × 5 alphabet grid**.

Each letter is represented by two groups of dots:

- The first group represents the row.
- The second group represents the column.

**Example:**

The letter `A`, located in row 1, column 1, is represented as:

`"." "."`

The letter `H`, located in row 2, column 3, is represented as:

`".." "..."`

**Special rule:** The letters `C` and `K` share the same position in the grid. During encoding, `K` is converted to `C`.

The implementation uses Java HashMaps to map letters to dot sequences and decode them back into text.

## Project Structure

```text
src/
└── cipher/
    ├── Main.java
    ├── SingleLetterGrilles.java
    └── TapCode.java
```

**Main.java**

Provides the command-line interface, accepts user input, and allows users to select an algorithm.

**SingleLetterGrilles.java**

Implements spiral matrix encryption and decryption.

**TapCode.java**

Implements Tap Code encoding and decoding using a 5 × 5 matrix and HashMaps.

## Requirements

- Java JDK 11 or newer
- IntelliJ IDEA or another Java IDE (optional)
- Terminal or command prompt

No external dependencies are required.

## How to Run

### Option 1: IntelliJ IDEA

1. Open the project in IntelliJ IDEA.
2. Locate `Main.java`.
3. Right-click the file.
4. Select **Run 'Main.main()'**.
5. Follow the instructions in the console.

### Option 2: Command Line

Open a terminal in the project root directory.

**Compile:**

```bash
javac src/cipher/*.java
```

On Windows PowerShell, you can use:

```powershell
javac src/cipher/Main.java src/cipher/SingleLetterGrilles.java src/cipher/TapCode.java
```

**Run:**

```bash
java -cp src cipher.Main
```

## Example Usage

### Example 1: Single Letter Grilles

**Input:**

```text
Select algorithm: 1
Enter text: HELLO
```

**Output:**

```text
Encrypted:
HEL_LO___

Decrypted:
HELLO
```

### Example 2: Tap Code

**Input:**

```text
Select algorithm: 2
Enter text: HELLO
```

**Output:**

```text
Encoded:
.. ... . ..... ... . ... . ... ....

Decoded:
HELLO
```

*Note: The current Java console interface displays its prompts in Albanian. The English prompts above illustrate the same workflow.*

## Educational Purpose

This project was developed to explore foundational concepts in classical cryptography and data security.

It demonstrates:

- Character substitution and transposition techniques.
- Matrix-based text transformations.
- Encoding and decoding algorithms.
- Data structures for mapping characters.
- Basic Java application development.

**Security note:** These are historical and educational techniques. They do not provide modern cryptographic security and should not be used to protect sensitive information.

## Known Limitations

- The program operates through a command-line interface.
- The Single Letter Grilles implementation uses underscores as padding and removes them during decryption, so original underscores are not preserved.
- Tap Code removes spaces, digits, and punctuation from input.
- Tap Code represents both `C` and `K` using the same code.
- The implementation is intended for educational demonstrations rather than secure communication.

## Author

**Dalina Baraliu**

Computer Science student interested in cybersecurity, networking, digital forensics, and software development.

[GitHub Profile](https://github.com/dalina-baraliu)

## License

No license has been specified for this project.
