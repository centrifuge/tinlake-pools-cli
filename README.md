# tinlake-pools-cli
This repo contains the cli for managing tinlake pools along with an on chain registry.

## Setup
1) Install dependencies: `npm install`
2) Get an API key on pinata and set the env variables `PINATA_API_KEY` and `PINATA_SECRET_KEY`
3) Set the `dapp` typical env variables (`ETH_RCP_URL`, `ETH_FROM`, `ETH_KEYSTORE`, `ETH_PASSWORD`)

## Options
The following environment variables :
* POOL_REGISTRY_ADDRESS
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

   epoch-status    upload and pin file using Pinata
   help            print help about pool(1) or one of its subcommands
   ipfs            read & save files on IPFS using Pinata
   registry        command-line util to manage pool metadata

Report bugs to <https://github.com/centrifuge/tinlake-pool-config>.
```

## PoolRegistry
### Usage
The registry keeps track of a list of addresses along with their short name and pool metadata IPFS hash.

### Deployment
To create a new pool registry, deploy it with:
```
    dapp create --verify "src/registry.sol:PoolRegistry"
```

