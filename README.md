# tinlake-pools-cli
This repo contains the cli for managing tinlake pools along with an on chain registry.

## Setup
1) Install dependencies: `npm install`
2) Get an API key on pinata and set the env variables `PINATA_API_KEY` and `PINATA_SECRET_KEY`
3) Set the `dapp` typical env variables (`ETH_RCP_URL`, `ETH_FROM`, `ETH_KEYSTORE`, `ETH_PASSWORD`)

## Options
The following environment variables should be set:
* ETH_NETWORK: `ethlive` or `kovan`
* POOL_BASE_DIR: default to `pwd`, should be a checkout of tinlake-pools-(mainnet/kovan)
* PINATA_SECRET_KEY
* PINATA_API_KEY

## `pool` CLI
```
Usage: pool <command> [<args>]
   or: pool help <command>

Manage Tinlake pools the good old fashioned way

Special commands:

   --registry-address  prints current registry address

Commands:

   data            fetch pool data from IPFS
   epoch           check epoch status and close epochs
   help            print help about pool(1) or one of its subcommands
   ipfs            read & save files on IPFS using Pinata
   registry        command-line util to manage pool metadata
   status          print a short summary for all known pools


Configuration Variables:

ETH_CHAIN
    Current active eth chain (ethlive, kovan), set
    this to avoid delay introduced by ethlive

POOL_BASE_DIR
    Path to local pool metadata. Used for the registry updates.
    Defaults to /home/lucasvo/code/tinlake-pools-mainnet

POOL_REGISTRY_ADDR
    Address of the registry contract for the specific environment

Report bugs to <https://github.com/centrifuge/tinlake-pools-cli>.
```

## PoolRegistry
### Usage
The registry keeps track of a list of addresses along with their short name and pool metadata IPFS hash.

### Deployment
To create a new pool registry, deploy it with:
```
    dapp create --verify "src/registry.sol:PoolRegistry"
```

