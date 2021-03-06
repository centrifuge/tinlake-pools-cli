# tinlake-pools-cli
This repo contains the cli for managing tinlake pools along with an on chain registry.

## Setup
1) Install dependencies: `npm install`
2) Get an API key on pinata and set the env variables `PINATA_API_KEY` and `PINATA_SECRET_KEY`
3) Set the `dapp` typical env variables (`ETH_RCP_URL`, `ETH_FROM`, `ETH_KEYSTORE`, `ETH_PASSWORD`)

## Options
The following environment variables should be set:
* POOL_BASE_DIR: default to `pwd`, should be a checkout of tinlake-pools-(mainnet/kovan)
* PINATA_SECRET_KEY
* PINATA_API_KEY
* POOL_REGISTRY_ADDRESS
    Address of the registry contract for the specific environment
* ETH_CHAIN: defaults to `seth chain`, set to either `kovan` or `ethlive`


## `pool` CLI
```
Usage: pool <command> [<args>]
   or: pool help <command>

Manage Tinlake pools the good old fashioned way

Commands:

   data            fetch pool data from IPFS
   epoch           check epoch status and close epochs
   help            print help about pool(1) or one of its subcommands
   ipfs            read & save files on IPFS using Pinata
   registry        command-line util to manage pool metadata
   status          print a short summary for all known pools


```

## PoolRegistry
### Usage
The registry keeps track of a list of addresses along with their short name and pool metadata IPFS hash.

### Deployment
To create a new pool registry, deploy it with:
```
    dapp create --verify "src/registry.sol:PoolRegistry"
```

