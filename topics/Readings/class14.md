# Class 14 reading: Hashing, bcrypt and jBCrypt
# Understanding Hashing

**Hashing** is a process used in computer security and data storage. It's like a special recipe that turns any piece of information, like a password, into a unique code. This code is called a "hash." Think of it as a secret code that represents your password.

# Explanation for a Non-Technical Friend:
Now, imagine you have a secret recipe for your favorite cookie. When you bake those cookies, you get a unique taste that's specific to that recipe. In the same way, a hash function takes your password and transforms it into a unique code, just like your cookie recipe creates a unique taste.

So, when you create an account on a website and set a password, instead of storing your actual password, the website uses a hash function to turn your password into this secret code. This is super important for security because it means that even if someone manages to peek at the stored codes (like cookie recipes), they can't easily figure out your original password. It's like trying to recreate your delicious cookies just by tasting them – it's almost impossible!

So, hashing is like making a secret code for your password to keep it safe and secure. It's a way to protect your information online.

# Salting Passwords

To "salt" a password means to add a random string of characters to the password before hashing it. This random string is called a "salt." The purpose of salting is to enhance the security of hashed passwords, particularly in the context of storing them in databases.

The salt is typically generated randomly for each user and then combined with their password before hashing. This means that even if two users have the same password, their hashed passwords will be different because they have different salts. Salting prevents attackers from using precomputed tables (like rainbow tables) to crack passwords because each password hash has a unique salt.

## Accessing the Salt

In order to find the salt string for passwords, a hacker would need access to the source code or the database where the salts are stored. If the salts are stored alongside the hashed passwords in the same database, a breach of the database could expose both the hashed passwords and their corresponding salts. However, the idea behind salting is that even if a hacker gets access to the hashed passwords and salts, it would be computationally infeasible to crack them all due to the uniqueness of the salts.

So, while it's important to keep salts secret, their primary purpose is to defend against attacks even if they are known to attackers. The real security lies in the uniqueness of each salt combined with each user's password.

# Blowfish Block Cipher and jBCrypt

jBCrypt is a Java™ implementation of OpenBSD's Blowfish password hashing code, as described in "A Future-Adaptable Password Scheme" by Niels Provos and David Mazières.

## Handling Increased Computation Speed

The Blowfish block cipher, as implemented in jBCrypt, handles the increased computation speed of new computers by allowing the computation cost of the algorithm to be parameterized. In other words, you can adjust the "cost" of the hashing algorithm. The cost is determined by a parameter called "log_rounds." The higher the log_rounds value, the more computational work is required to calculate the hash. As computers become faster, you can increase the log_rounds value to make the hashing process more computationally intensive, slowing down the speed at which hashes are computed.

This approach ensures that as computers become more powerful, the password hashing process remains sufficiently slow and resource-intensive, making it much more difficult and time-consuming for attackers to perform offline password cracking attacks.

## Issues with Common Password Hashes in Java

Regarding the issues with the two most common password hashes for Java:

1. **Unsalted Hash**: One of the issues with some Java password hashing implementations is that they use unsalted hashes. Unsalted hashes are vulnerable to various types of attacks, including rainbow table attacks and dictionary attacks. Without a unique salt for each password, identical passwords will produce the same hash, making it easier for attackers to crack passwords through precomputed tables.

2. **Reversible Encryption**: Another issue is the recommendation of reversible encryption for password storage. Reversible encryption means that it's possible to decrypt and recover the original password from the stored hash. This is highly insecure because if the encryption key is compromised, all passwords can be easily decrypted. Passwords should never be stored in a reversible form, and encryption should only be used in specific, well-justified scenarios.

jBCrypt, on the other hand, addresses these issues by providing a secure password hashing mechanism that includes salting and allows you to adjust the computational cost, making it resistant to both unsalted hash vulnerabilities and rapid advancements in computer speed.
