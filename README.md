# Turbin3 Builders Cohort Q1 2025 by Jan Jankowski

Welcome to my **Turbin3 Builders Cohort Q1 2025** repository! Here you will find all code written by me during this program.

This cohort focuses on the foundational knowledge and prectical skills needed to navigate the evolving landscape of decentralized applications in Solana.

## Directories Overview

### airdrop

The very first challenge recieved before joining the cohort.
The tasks consisted of:

- Creating a keypair in devnet.
- Funding it with some Solana.
- Making a transfer from the generated address to our devnet wallet submitted for the cohort.
- Writing helper conversion functions for addresses from base58 to byte array and back.
- Consuming an IDL.
- Making a transaction to a program on devnet based on the IDL.

This task was written in _typescript_

### airdrop-rust

The next step still in the prerequisites phase was to repeat the process from the first task in _rust_

### solana-starter

Our first module in the world of Solana programming.

- The goal of the first class was to initialize a spl token and mint it.
- In the second lecture we learned about nft's. Which lead us to implementing minting nft's,
  uploading metadata (or files in general) to an onchain service.
- We finished the week by generating an nft and transfering it to other students.
- As an additional practice I explored the creation of nft collections and ended up writing modules
  for batch image and metadata json upload as well as a batch transfer function.

### anchor-vault

The second week of our lectures took us into anchor and rust. First we implemented a
solana vault. The main take aways were:

- macro constraints in Structure definitions
- cross program invocations with a user and with a pda as a signer

An interesting find during the lecture was that you cannot close the vault account,
which is a system account using the close constraint as it tries to destroy the underlying object account
in it's implementation and that is not possible for system accounts. The work around was to use the constraint
to close the vault state account and setup the vault itself as a mutable account and then simply transfer all the
remaining solana to the users address inside the implementation function.

## Maintainer / Contact <img src="./gears.svg">

- Jan Jankowski jan.jankowski@libar.io
