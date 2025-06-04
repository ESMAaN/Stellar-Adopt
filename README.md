# Stellar-Adopt

<p align="center">
  <img src="assets/adopt.png" width="300" alt="StellarAdopt">
</p>

## About me:
- name: Esma Şen  
- Final-year Software Engineering student at Maltepe University   
- Passionate about blockchain, embedded systems, and digital transformation  
- Developed real-time interaction and smart contract projects  
- Participating in Stellar Bootcamp to explore Soroban and NFT use cases  
- Eager to build meaningful decentralized applications with social impact

## Project details:
StellarAdopt is a decentralized NFT-based digital pet adoption platform built on the Stellar blockchain. Every shelter animal is represented as a unique NFT. When an adoption is approved, the NFT is minted and sent to the adopter’s wallet. Only authorized shelter accounts can mint or revoke NFTs. Freeze functionality is included to temporarily disable transfer in case of dispute or fraud. This system ensures transparent, tamper-proof tracking of animal ownership, reducing fake adoptions and enabling long-term trust between shelters and adopters.

## Vision:
StellarAdopt envisions a world where every pet adoption is transparent, verifiable, and secure. By turning each shelter animal into a unique NFT, we provide digital proof of adoption and ownership. This brings accountability to animal welfare efforts and reduces paper-based or unverifiable processes. StellarAdopt empowers shelters and adopters with a trustworthy system that can be scaled globally for ethical and efficient animal protection.

## Project description:
StellarAdopt is a smart contract-based digital adoption platform on the Stellar blockchain. It transforms each animal in a shelter into a unique NFT, minted when the adoption is approved. The NFT is linked to the adopter’s wallet, serving as a verifiable proof of ownership. Only shelter-authorized addresses can mint or revoke NFTs. A freeze mechanism allows the shelter to temporarily restrict transfer if necessary. This project ensures that adoption processes are transparent, prevents fraud, and provides a secure digital record of each animal’s new home. It brings innovation to animal welfare through decentralized technology.

## Software development plan:
1. **Define data structures and variables**  
   - `animals: Map<u32, AnimalRecord>`  
   - `AnimalRecord`: contains adopter wallet, adoption status, frozen status

2. **Implement mint and adopt functionality**  
   - `mint_nft(animal_id: u32, adopter: Address)`  
   - Only callable by shelter account

3. **Add transfer and freeze control**  
   - `freeze_adoption(animal_id: u32)`  
   - `unfreeze_adoption(animal_id: u32)`

4. **Enable revoke or return NFT if adoption is canceled**  
   - `revoke_nft(animal_id: u32)`  
   - Only authorized shelter can call

5. **(Optional) Build a frontend**  
   - Display animals, adoption status, and connect with user wallet

6. **Deploy to Stellar Testnet**  
   - Use Soroban CLI to compile and deploy the contract

## Personal story:
I joined Stellar Bootcamp to learn how blockchain can solve real problems. I wanted to build a project that combines technology with social impact. With StellarAdopt, I’m creating a secure and transparent pet adoption system using NFTs. Even though I had no prior experience with Soroban, I pushed myself to understand smart contract logic. This project helped me grow as a developer and gave me the chance to contribute to a meaningful cause using decentralized tools.

## 🛠️ How to Install and Deploy StellarAdopt

### Prerequisites

Before starting, make sure you have the following tools installed:

- [Rust](https://www.rust-lang.org/tools/install)
- [Soroban CLI](https://soroban.stellar.org/docs/install/soroban-cli)
- [Docker](https://www.docker.com/) (optional, for local network testing)

### Clone the Repository

```bash
git clone https://github.com/yourusername/stellar-adopt.git
cd stellar-adopt
```
#Build the smart contract
```bash
soroban contract build
```
#Deploy to Stellar Testnet
```bash
soroban contract deploy \
  --wasm target/wasm32-unknown-unknown/release/stellar_adopt.wasm \
  --network testnet
```
#Interact with the Contract (Examples)

```bash
soroban contract invoke \
  --id <your_contract_id> \
  --fn mint_nft \
  --arg animal_id=1 \
  --arg adopter=<adopter_wallet_address>
```
```bash
soroban contract invoke \
  --id <your_contract_id> \
  --fn freeze_adoption \
  --arg animal_id=1
```
