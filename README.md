# Core cryptographic libraries
pip install pynacl                   # For Ed25519 signatures
pip install cryptography        # For encryption and key management
pip install base58                   # For base58 encoding
pip install python-dotenv       # For loading .env files


Hash Functions (SHA-256)

SHA-256 is the primary hashing algorithm in ILP. It produces a 256-bit (32-by) hash that's:
- Deterministic: Same input always produces same output
- One-way**: Cannot reverse a hash to find the input
- Collision-resistant: Extremely unlikely two inputs produce same hash


Hashlocks are the simplest form of crypto-conditions. 
- A sender creates a **condition** by hashing a random secret (preimage). The payment is released only when someone provides the original secret.

Ed25519 Signatures and Key Management

-ILP wallets use Ed25519 keypairs. The private key signs transactions, while the public key verifies signatures. This provides non-repudiation and authentication.

Multi-Signature Conditions

- Multi-signature conditions require multiple parties to sign before funds can be released. This is crucial for high-value accounts and organizational wallets. A threshold scheme (e.g., 2-of-3) provides security through distributed trust.

Secure Key Storage

-In production, private keys must never be hardcoded. They should be stored in environment variables, encrypted files, or hardware security modules (HSMs). The goal is to separate key material from code.
