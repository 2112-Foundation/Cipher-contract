# About

Cipher-Contract is the On-Chain Implementation of the neccessary processes to enable Solana as a Backend for a Protonmail esque service. This program is designed and intended for use within the Dark Protocol Application. Cipher is an End-To-End Encrypted Onchain Email that utilises PGP Encryption as the method for secrecy. 

## Encryption

Only the frontend is responsible for encrypting and decrypting data, while the blockchain is only used to store public information about the encryption, key exchange, and the email itself. This has been done to ensure that the user is able to verifiably build and confirm correct use of PGP on the interface. <br />

Encryption as a base uses AES-256
[Learn more about AES-256](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard "AES-256 and Counter Mode")

## Key Exchange

Cipher uses an implementation of Diffie-Hellman Key Exchange[Diffie-Hellman Key Exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) to securely create a communication channel, each unique user get both a public an private key at the moment of registration. Only the public key of the mail account is stored on the blockchain.

## Run the project

Prerequisite Checks -> open `/Anchor.toml` and make sure that it is pointing to your development/mainnet deploy key and the exact cluster that you want to run on. <br />

Run the following commands on your terminal, at the root of the project:

```bash
yarn
anchor build
anchor test
```

### Architecture

...
├─ src <br />
│  ├─ context.rs -> structs used instructions arguments <br />
│  ├─ error.rs -> error structs <br />
│  ├─ lib.rs -> entrypoint, processor, and register modules <br />
│  ├─ state.rs -> state structs <br />
│  ├─ utils.rs -> helpers functions <br />
...
