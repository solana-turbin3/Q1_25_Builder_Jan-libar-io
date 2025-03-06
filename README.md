# Turbin3 Builders Cohort Q1 2025 by Jan Jankowski

Welcome to my **Turbin3 Builders Cohort Q1 2025** repository! Here you will find all code written by me during this program.

This cohort focuses on the foundational knowledge and prectical skills needed to navigate the evolving landscape of decentralized applications in Solana.

## Directories Overview

### airdrop <img src="./assets/typescript-icon.svg">

The very first challenge recieved before joining the cohort.
The tasks consisted of:

- Creating a keypair in devnet.
- Funding it with some Solana.
- Making a transfer from the generated address to our devnet wallet submitted for the cohort.
- Writing helper conversion functions for addresses from base58 to byte array and back.
- Consuming an IDL.
- Making a transaction to a program on devnet based on the IDL.

This task was written in _typescript_

### airdrop-rust <img src="./assets/rust-icon.svg">

The next step still in the prerequisites phase was to repeat the process from the first task in _rust_

### solana-starter <img src="./assets/typescript-icon.svg">

Our first module in the world of Solana programming.

- The goal of the first class was to initialize a spl token and mint it.
- In the second lecture we learned about nft's. Which lead us to implementing minting nft's,
  uploading metadata (or files in general) to an onchain service.
- We finished the week by generating an nft and transfering it to other students.
- As an additional practice I explored the creation of nft collections and ended up writing modules
  for batch image and metadata json upload as well as a batch transfer function.

### anchor-vault <img src="./assets/rust-icon.svg">

The second week of our lectures took us into anchor and rust. First we implemented a
solana vault. The main take aways were:

- macro constraints in Structure definitions
- cross program invocations with a user and with a pda as a signer

An interesting find during the lecture was that you cannot close the vault account,
which is a system account using the close constraint as it tries to destroy the underlying object account
in it's implementation and that is not possible for system accounts. The work around was to use the constraint
to close the vault state account and setup the vault itself as a mutable account and then simply transfer all the
remaining solana to the users address inside the implementation function.

### anchor-escrow <img src="./assets/rust-icon.svg">

After learning how to create a vault, we expanded our knowledge to one of if not the most important program pattern in web3 - the escrow.

The goal of the escrow program is to allow a swap of tokens between two parties with the program taking care of securing the swap, so making sure that the conditions for the swap are met on both sides.

This escrow example works as follows:

- The maker initalizes an escrow and deposits a certain amount of token_a into the escrow's vault. During the initialization they also define the amount of token_b they want to receive in order to execute the swap.

- The taker then deposits set amount of token_b in the escrow.

- Finally the escrow sends the token_a it stored in its vault to the taker and is closed.

- Upon it's closure the escrow transfers the token_b that it recieved from the taker to the maker.

### anchor-marketplace <img src="./assets/rust-icon.svg">

An NFT marketplace is an online platform where users can buy, sell, and trade Non-Fungible Tokens (NFTs), which are unique digital assets stored on a blockchain. These marketplaces operate similarly to e-commerce sites but are tailored for digital collectibles, artwork, music, virtual real estate, and other tokenized items that certify ownership and authenticity.

This is an example of implementation of a marketplace on Solana.

- The admin can initialize a marketplace and set a fee for it.

- The maker can list or delist items on the marketplace.

- The taker can purchase listed nft's.

## Maintainer / Contact <img src="./assets/gears-icon.svg">

- Jan Jankowski jan.jankowski@libar.io
