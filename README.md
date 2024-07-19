# ORE

**ORE is a fair launch, proof of work, digital currency everyone can mine.**


## API
- [`Consts`](api/src/consts.rs) – Program constants.
- [`Entrypoint`](api/src/lib.rs) – The program entrypoint.
- [`Error`](api/src/error.rs) – Custom program errors.
- [`Event`](api/src/error.rs) – Custom program events.
- [`Instruction`](api/src/instruction.rs) – Declared instructions and arguments.

## Instructions
- [`Claim`](program/src/claim.rs) – Distributes claimable rewards as tokens from the treasury to a miner.
- [`Close`](program/src/close.rs) – Closes a proof account returns the rent to the owner.
- [`Crown`](program/src/crown.rs) – Flags a proof account as the top staker on the network.
- [`Open`](program/src/open.rs) – Creates a new proof account for a prospective miner.
- [`Mine`](program/src/mine.rs) – Verifies a hash provided by a miner and issues claimable rewards.
- [`Stake`](program/src/stake.rs) – Stakes ORE with a miner to increase their multiplier.
- [`Reset`](program/src/reset.rs) – Resets the program for a new epoch.
- [`Update`](program/src/update.rs) – Updates a proof account's miner authority.
- [`Upgrade`](program/src/upgrade.rs) – Migrates ORE v1 tokens to ORE v2, one-for-one.
- [`Initialize`](program/src/initialize.rs) – Initializes the Ore program, creating the bus, mint, and treasury accounts.

## State
 - [`Bus`](api/src/state/bus.rs) - An account (8 total) which tracks and limits the amount ORE mined each epoch.
 - [`Config`](api/src/state/config.rs) – A singleton account which manages program-wide variables.
 - [`Proof`](api/src/state/proof.rs) - An account (1 per user) which tracks a miner's current hash and current stake.
 - [`Treasury`](api/src/state/treasury.rs) – A singleton account which has authority to mint ORE and holds onto user stake.


## Tests

To run the test suite, use the Solana toolchain: 

```
cargo test-sbf
```

For line coverage, use llvm-cov:

```
cargo llvm-cov
```
