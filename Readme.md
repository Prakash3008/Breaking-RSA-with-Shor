# Breaking RSA using Shor’s Algorithm

This repository contains an **experimental** implementation of Shor's Algorithm to factor large integers, which can be used to break the RSA encryption system using quantum computing. The current implementation may require modifications  to accommodate all cases effectively.

# Overview 

RSA encryption relies on the hardness of factoring large integers, specifically the product of two prime numbers. Classical algorithms for factoring require super-polynomial time, making RSA secure for large key sizes. However, Shor's algorithm, running on a quantum computer, can factor integers in polynomial time, potentially breaking RSA encryption.

# Dependencies

To run this notebook, install the following dependencies:
``` pip install qiskit numpy sympy ```

# Implementation Details 

    1. RSA Key Generation : 
        Generate two large prime numbers `p` and `q`.
        Compute `N = p * q` and Euler’s totient function `φ = (p - 1) * (q - 1)`.
        Choose a public key exponent `e` such that `gcd(e, φ) = 1`.
        Compute the private key `d` using the modular inverse of `e` modulo `φ`.
         

    2. Encryption & Decryption : 
        Convert the plaintext message into a numerical representation.
        Encrypt using `ciphertext = message^e mod N`.
        Decrypt using `plaintext = ciphertext^d mod N`.
         

    3. Shor’s Algorithm (Experimental) : 
        Utilizing quantum computation principles such as quantum Fourier transform (QFT) to factor `N`.
        Finding the order `r` of a function using modular exponentiation.
        Extracting the prime factors of `N` efficiently using periodicity detection.

# Running the Notebook 

    1. Clone this repository: 
        ``` 
        git clone https://github.com/Prakash3008/Breaking-RSA-with-Shor.git
        cd Breaking-RSA-with-Shor
        ```
    2. Open Jupyter Notebook:
        ```
        jupyter notebook Shor_s Algorithm to Break RSA.ipynb
        ```
    3. Execute the cells to generate RSA keys, encrypt a message, and attempt to factor `N` using Shor’s Algorithm.

# Important Notes 

    1. ⚠ This implementation is experimental and the success of factorization depends on the ability of a quantum computer to handle large inputs.  
    2. Shor’s Algorithm requires a quantum computer to run efficiently. The notebook provides a simulation using Qiskit.
     