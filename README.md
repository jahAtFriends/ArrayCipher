# ArrayCipher

In this project, you will use your new-found knowledge of **arrays** and **loops** to build a
(really low quality) _Enigma Machine_ that will encode or decode a secret message. This poject
will use a _simple substitution cipher_.

## Simple Substitution Cipher

Every cipher has three components:
1. _Plaintext_: The actual secret message to be encoded into a cipher.
2. _Ciphertext_: The plaintext written in some code.
3. _Key_: The mechanism for encoding/decoding the plaintext into the cipher text and vice-versa.

In the simple substitution cipher, each letter is systematically swapped out for another letter.
Here is an example of a _key_ which translates a letter from plaintext to the cipher text:

| Plaintext  | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z |
|------------|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Ciphertext | H | U | D | Q | E | N | O | A | V | X | J | S | Z | L | W | Y | R | G | F | P | B | C | I | T | M | K |

Using this key, the phrase "IT WAS THE BEST OF TIMES" becomes "VP IHF PAE UEFP WN PVZEF." This is
done by looking up each letter of the plaintext in the key table and replacing it with the corresponging
encoded letter. To _decode_ simply reverse the process: find the encoded letter in the ciphertext row
and replace it with the corresponding plaintext letter above it.

## Project Synopsis

Write _two_ programs called `Encrypt.java`and `Decrypt.java` with the following specifications 

### Encryption
The program `Encrypt.java` should read a String of plaintext from the commandline and encode it
into a cipher text using a key read in from a text file (see below). Finally it should print the
cipher text to the command line in all-caps.

### Decryption
Similarly, the program `Decrypt.java` should read a String of ciphertext from the command line and
decode it into plaintext using a key read in from a text file (see below). Finally it should print
the cipher text to the command line in all-caps.

### Key Generation (optional)
Write a program called `Keygen.java` which prints out a random shuffling of the 26 characters of the
English alphabet which will serve as the key for a cipher.

Upload you assignment to CodePost by the due date (see CodePost for details).

## Specs and Helpful How-Tos
You will need to follow particular specifications and use some commands which we did not discuss in
class in order to complete this project. Please read each of the sections below for additional
information.

### Convert a String to an all-UPPERCASE String
For this assignment, you do not need to treat upper- and lower-case letters differently. You may
simply print the result in all-caps. The following String method will be helpful:

```java
String message = "Hello World";
message = message.toUpperCase();
```

This will result in the value "HELLO WORLD" being stored in the String variable `message.`

### Convert a String to an array of Chars
It may be helpful to store each letter of a String of chars so that you can access and 
edit them one-by-one. Here's some helpful code to make that conversion:

```java
String message = "Hello World";
char[] plaintext = message.toCharArray();
```
This will result in the array `{'H','e','l','l','o',' ','W','o','r','l','d'}`.

### Store a Cipher's Key as a Text File
You can store a substitution cipher's key as 26 letters (separated by a space). This
should be interpreted to mean the first letter as an encoding for 'A', the second as
an encoding for 'B' and so on. A text file (say "key.txt") version of the example key
shown above would be "H U D Q E N N O A V X J S Z L W Y R G F P B C I T M K".

### Read in data from a text file.
To use a text file as input through StdIn ("standard input" usually the same as
`System.in`), save the text file in the same directory as the .java file you are
intending to compile and run. From the command line type:

```bash
javac Encrypt.java
java Encrypt < key.txt
```

This will allow the content of key.txt to be read by the program `Encrypt`.

### Reading data from a text file through StdIn
If a text file is fed into a program using the commandline as shown above, your program
can use a ```Scanner``` to access it in the following manner.

```java
Scanner input = new Scanner(System.in);
char[] key = new char[26];
for (int i = 0; i < key.length; i++) {
    key[i] = input.nextChar();
} ```
