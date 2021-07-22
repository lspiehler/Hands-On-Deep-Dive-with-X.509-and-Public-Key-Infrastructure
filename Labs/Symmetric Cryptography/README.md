
# Symmetric Cryptography Lab

1. Launch a command prompt and change directory to the "Labs\Symmetric Cryptography" directory.

2. Also navigate to "Labs\Symmetric Cryptography" in an explorer window so that you can see the files in the directory.

2. You should see a file named plaintext.txt. Open it and customize the text.

3. Run the following command to encrypt the file. You will be prompted to enter a password.
```openssl enc -e -aes-256-cbc -in plaintext.txt -out encrypted.txt```

4. Examine the contents of the output file created by the command encrypted.txt. The contents of the original file have been encrypted using "symmetric encryption" in the form of a password.

5. Run the following command to decrypt the file you just encrypted. You will need to enter the same password you used previously.
```openssl enc -d -aes-256-cbc -in encrypted.txt -out decrypted.txt```