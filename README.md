# [Book cipher](https://fun840.github.io/book-cipher)

A small site for decoding a specific type of book cipher. Given a block of text and a sequence of number pairs in the format `#/# #/# #/# [...]`, the cipher works by using the first number to pick the nth word, and the second number to pick the nth letter in the word.

## Example

Book text:

```raw
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```

Cipher text:

```raw
42/6 5/3 8/2 17/3 6/2
```

This decodes to the word `hello`.