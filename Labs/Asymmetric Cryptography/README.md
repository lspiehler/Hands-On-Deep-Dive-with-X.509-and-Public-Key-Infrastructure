
# Asymmetric Cryptography Lab

### Objectives  
- Explore the capabilities of OpenSSL to generate encrypted and unencrypted key pairs of various sizes and formats.
- Use OpenSSL to convert between different private key formats.
- Encrypt a plaintext file using a public key, and decrypt it with a private key.

### Procedure  
1. Launch a command prompt and change directory to the "Labs\Asymmetric Cryptography" directory.

2. Navigate to "Labs\Asymmetric Cryptography" in an explorer window so that you can see the files in the directory.

3. You should see a file named plaintext.txt. Open it and customize the text.

4. Run the following command in the command prompt to generate a 4096-bit PKCS#1 unencrypted key pair.
```
openssl genrsa -out pkcs1.pem 4096
```

5. Examine the contents of pkcs1.pem.

6. Run the following command in the command prompt to generate a 2048-bit PKCS#1 encrypted key pair, overwriting the one previously created. You will be prompted to create a password for the private key.
```
openssl genrsa -out pkcs1.pem -aes256 2048
```

7. Examine the contents of pkcs1.pem.

8. Run the following command to convert the PKCS#1 private key to PKCS#8 format. You will be prompted to enter the password you created earlier for pkcs1.pem and again to create a new password for pkcs8.pem.
```
openssl pkcs8 -topk8 -inform PEM -outform PEM -in pkcs1.pem -out pkcs8.pem
```

9. Examine the contents of pkcs8.pem. 

10. Run the following command to extract the public key from your PKCS#8 private key into a file named public.pem. Because the private key is encrypted, you will be prompted to enter the password.
```
openssl rsa -in pkcs8.pem -pubout -out public.pem
```

11. Examine the contents of public.pem.

12. Run the following command to encrypt the contents of the plaintext.txt file into a new file named encrypted.txt using the public key you extracted from the encrypted private key.
```
openssl rsautl -encrypt -pubin -inkey public.pem -in plaintext.txt -out encrypted.txt
```

13. Examine the contents of encrypted.txt.

14. Finally, run the following command to decrypt the contents of the encrypted.txt file into a new file named decrypted.txt using the private key. You will be prompted to enter a password because the private key is encrypted.
```
openssl rsautl -decrypt -inkey pkcs8.pem -in encrypted.txt -out decrypted.txt
```

15. Examine the contents of decrypted.txt.

16. Modify the command above to decrypt encrypted.txt using pkcs1.pem. Notice that you are able to decrypt because the private keys are the same, but stored in different formats.

17. Share your public key with a friend and ask them to encrypt a message and send it to you. Decrypt their message with your private key.