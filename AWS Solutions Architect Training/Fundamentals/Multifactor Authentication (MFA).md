> [!Definition] Factors
> Different pieces of evidence which prove identity
> - More factors means more security
> - Goal: achieve a balance between convenience and security

Four common factors:
- Knowledge: something you know (usernames, passwords)
- Possession: something you have (debit card, MFA device/app)
- Inherent: something you are (fingerprint, eye scan, face login)
- Location: location (physical) or network

1. AWS generates a secret key and additional information
2. AWS generates a QR code based on the secret key
3. User scans the QR code into MFA app
4. User enters the generated code in order to login to their AWS Account