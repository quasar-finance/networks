# Quasar genesis ceremony.

If you are going to participate in the Genesis , please proceed as following:

1. Provide your public key[^1] (e.g.: `quasar190....`) to Quasar Team before the defined date to be included in the initial token allocation.
2. Download the pre-genesis file, to be generated and uploaded to `quasar-1/pre-genesis.json`
3. Issue and sign genesis transacion. You should use the key that you provided to have enough tokens for self delegation. Example command:\
   `quasarnoded gentx < validator_key_name > 100000000uqsr --chain-id quasar-1 --keyring-backend test`
4. Upload the signed transaction to this repository with a PR in the `quasar-1/gentx/` folder (please name it `gentx-<your_moniker>.json`)
5. Edit the persistent_peers.txt file in `quasar-1/persistent_peers.txt` and add the corresponding row of your node with node_id and IP:PORT.
6. Wait for the definitive genesis transaction to be provided by Quasar Team.
7. Adjust the `persistent_peers` parameter in `.quasarnode/config/config.toml`. It should have the different nodes that will seed the initial chain, e.g.:
   `c1b4262debfebc228e20f17f12102bb0740290c6@191.122.12.83:26656"`\
   Pick the nodes from `quasar-1/persistent_peers.txt` file in this repo
8. Launch the daemon with `sudo systemctl start quasard` before the genesis time defined in `genesis_time`.

[^1]: To obtain the public key named `validator_key` in the keyring in your node you can use: `quasarnoded keys show validator_key -a --keyring-backend test`
