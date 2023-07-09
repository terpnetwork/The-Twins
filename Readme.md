# THE TWINS
A custom Cosmos Discord Bot's for dispensing testnet tokens.

## Features

- Responds to requests for tokens on multiple testnets
- Response includes a link to the transaction detail in the appropriate block explorer
- Limits the tokens a user can get within a time period for a given testnet
- Limits the tokens an address can get within a time period for a given testnet
- Daily cap for each testnet token
- Requests are saved in local csv file: date, cosmos address, amount, and testnet
- Errors are logged to systemd journal

## Requirements

- python 3.8.12+
- terpd 1.0.0+
- Initialized terpd instance
- Faucet keys in terpd keyring

## Bot Token Configuration.

1. [Create a Discord token](https://github.com/reactiflux/discord-irc/wiki/Creating-a-discord-bot-&-getting-a-token)
2. Add the bot token to `config.toml`

## Stand-alone

This bot can be run stand-alone (mostly for testing), or as a service.

- This can be run inside a `tmux` session.

## Discord Commands

1. Request tokens through the faucet:  
`$request [cosmos address] theta`
   - The response will include a ✅ and the transaction hash if it was successful.

2. Request the faucet and node status:  
`$faucet_status theta`

3. Request the faucet address:  
`$faucet_address theta`

4. Request information for a specific transaction:  
`$tx_info [transaction hash ID] theta`

5. Request the address balance:  
`$balance [cosmos address] theta`  


## Analytics

The `transactions.csv` file can be parsed using `cosmos_faucet_analytics.py` to output faucet usage analytics to a Node Exporter-compatible file.


## Acknowledgements

This repo is based on [cosmos-discord-faucet](https://github.com/c29r3/cosmos-discord-faucet):
- The cosmospy library calls have been replaced by calls to `terpd` to avoid deprecated endpoints and messages.
- The address prefix has been switched to `terp`.
