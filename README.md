# solana-voting-dapp production

- [Priority fee](https://solana.com/developers/cookbook/transactions/add-priority-fees)
- [radar - A static analysis tool for anchor rust programs.](https://github.com/Auditware/radar-action)


## Deploy to mainnet

- set rpc to mainnet
```bash
solana set config --url <mainnet rpc url>
```

- deploy using solana cli
```bash
solana program deploy target/deploy/voting.so --with-compute-unit-price 80000 --use-rpc --max-sign-attempts 1000
```

- [SWQOS](https://solana.com/developers/guides/advanced/stake-weighted-qos)


## Verify the program

- solana verify
```bash
cargo install solana-verify
```
- [verfied program api](https://github.com/otter-sec/solana-verified-programs-api)

```bash
solana-verify verify-from-repo --remote -um --program-id <PROGRAM_ID> <GITHUB_REPO_URL> --library-name <LIB_NAME> --mount-path anchor
```

## IDL onchain
- [anchor cli](https://www.anchor-lang.com/docs/references/cli)

Upload DIL
```bash
anchor idl init -f target/idl/program.json <program-id>
```
Fetch IDL
```bash
anchor idl fetch -o <out-file.json> <program-id>
```

## Use multisig for upgrade authority
[squads](https://squads.so/)