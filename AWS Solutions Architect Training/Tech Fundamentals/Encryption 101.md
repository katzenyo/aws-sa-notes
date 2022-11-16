## Definitions

- Encryption at rest: data that is encrypted in storage (e.g. resting)
- Encryption in transit: data that is encrypted while being transmitted from one location to another using a secure, encrypted tunnel
- Plaintext: data that is unencrypted
- Algorithm: encrypts data using an encryption key
- Ciphertext: encrypted data output from an algorithm

## Symmetric Encryption

- Uses the same key to both encrypt and decrypt data
- Can be compromised if a third party possesses the key

## Asymmetric encryption

1. Decide on an encryption algorithm to use
2. Create keys for the algorithm
	1. Two keys are generated: public and private
3. Public key is used to generate ciphertext, which then only the private key can decrypt

## Signing

- Proof that the party that encrypted data is who they say they are (nonrepudiation)

## Steganography

- Hiding information inside another piece of information (e.g. hiding data inside an image)
- Can be used for plausible deniability or transferring certain information without clueing others in that you're transferring that information
