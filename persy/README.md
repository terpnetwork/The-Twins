# INSTALLATION

## Dependencies

1. Python dependencies:
   
```
The-Twins/terpy$ python -m venv .env
The-Twins/terpy$ source .env/bin/activate
The-Twins/terpy$ pip install -r requirements.txt
```

2. Add the bot token to `config.toml`
3. Modify the nodes, faucet addresses, amount to send, etc. in `config.toml`

### Stand-alone

```
python cosmos_discord_faucet.py
```

- This can be run inside a `tmux` session.

### Service

1. Modify the `cosmos-discord-faucet.service` file as appropriate.
2. Make a copy of `cosmos-discord-faucet.service` or create a link to it in `/etc/systemd/system/`.
3. Enable and start the service:
```
systemctl daemon-reload
systemctl enable cosmos-discord-faucet.service
systemctl start cosmos-discord-faucet.service
systemctl status cosmos-discord-faucet.service
```


### Analytics Usage

The analytics script can be run stand-alone (mostly for testing), or as a service.

- Modify the log paths and logging period in `config_analytics.toml` as required. 

### Analytics Stand-alone

```
python cosmos_faucet_analytics.py
```

- This can be run inside a `tmux` session.

### Analytics Service

1. Modify the `cosmos-faucet-analytics.service` file as appropriate.
2. Make a copy of `cosmos-faucet-analytics.service` or create a link to it in `/etc/systemd/system/`.
3. Enable and start the service:
```
systemctl daemon-reload
systemctl enable cosmos-faucet-analytics.service
systemctl start cosmos-faucet-analytics.service
systemctl status cosmos-faucet-analytics.service
```
