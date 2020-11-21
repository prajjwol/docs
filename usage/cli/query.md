# Query network

**Usage**

```text
$ akashctl query [command]
```

**Example**

```text
$ akashctl query help

Querying subcommands

Usage:
  akashctl query [command]

Aliases:
  query, q

Available Commands:
  account                  Query account balance
  auth                     Querying commands for the auth module
  block                    Get verified data for a the block at given height
  deployment               Deployment query commands
  distribution             Querying commands for the distribution module
  mint                     Querying commands for the minting module
  provider                 Provider query commands
  slashing                 Querying commands for the slashing module
  staking                  Querying commands for the staking module
  supply                   Querying commands for the supply module
  tendermint-validator-set Get the full tendermint validator set at given height
  tx                       Query for a transaction by hash in a committed block
  txs                      Query for paginated transactions that match a set of events

Flags:
  -h, --help          help for query

Global Flags:
  -e, --encoding string   Binary encoding (hex/b64/btc) (default "hex")
      --home string       directory for config and data (default "/home/ubuntu/.akashctl")
  -o, --output string     Output format (text/json) (default "text")
      --trace             print out full stack trace on errors

Use "akashctl query [command] --help" for more information about a command.
```

Use `akashctl query` to query all the things that need querying.

**Available Commands**

| Command | Description |
| :--- | :--- |
| account | Query account balance. |
| auth | Querying commands for the auth module. |
| block | Get verified data for a the block at given height. |
| deployment | Deployment query commands. |
| distribution | Querying commands for the distribution module |
| mint | Querying commands for the minting module. |
| provider | Provider query commands. |
| slashing | Querying commands for the slashing module. |
| staking | Querying commands for the staking module. |
| supply | Querying commands for the supply module. |
| tendermint-validator-set | Get the full tendermint validator set at given height. |
| tx | Query for a transaction by hash in a committed block. |
| txs | Query for paginated transactions that match a set of events |

