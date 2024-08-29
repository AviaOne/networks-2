<!-- generated file - do not edit -->
# 🔗 `axone-dentrite-1`

![chain-id](https://img.shields.io/badge/chain%20id-axone--dentrite--1-blue?style=for-the-badge)
[![stability-beta](https://img.shields.io/badge/stability-beta-33bbff.svg?style=for-the-badge)](https://github.com/mkenney/software-guides/blob/master/STABILITY-BADGES.md#beta)
![audience](https://img.shields.io/badge/audience-public-white.svg?style=for-the-badge)
![incentivized-✖️](https://img.shields.io/badge/incentivized-✖️-29220A.svg?style=for-the-badge)
![genesis-time](https://img.shields.io/badge/%E2%8F%B0%20genesis%20time-2024--09--10T12%3A00%3A00Z-red?style=for-the-badge)

## Register in the Genesis

To register your validator node in the `genesis.json` you just need to provide a signed `gentx` with an initial delegation of `1000000000000uaxone` in a [⚖️ Register Validator issue](https://github.com/axone-protocol/networks/issues).

The gentx generation can be done as follow (this is an example script, adapt it to your needs) with the [axoned](https://github.com/axone-protocol/axoned/releases) binary matching the [network's version](/chains/dentrite-1/version.txt):

```sh
# Init node
axoned --home mynode init your-moniker --chain-id axone-dentrite-1

# Create keys, be careful with the mnemonic 👀
axoned --home mynode keys add your-key-name

# Set account necessary balance
axoned --home mynode genesis add-genesis-account your-key-name 1000000000000uaxone
```

Then create your own genesis transaction (`gentx`). You will have to choose the following parameters for your validator: `commission-rate`, `commission-max-rate`, `commission-max-change-rate`, `min-self-delegation` (>=1), `website` (optional), `details` (optional), `identity` ([keybase](https://keybase.io) key hash, used to get validator logos in block explorers - optional), `security-contact` (email - optional).

```sh
# Create the gentx
axoned --home mynode genesis gentx your-key-name 1000000000000uaxone \
  --node-id $(axoned --home mynode comet show-node-id) \
  --chain-id axone-dentrite-1 \
  --commission-rate 0.05 \
  --commission-max-rate 0.2 \
  --commission-max-change-rate 0.01 \
  --min-self-delegation 1 \
  --website "https://foo.network" \
  --details "My validator" \
  --identity "6C36E7C076BFDCE4" \
  --security-contact "validator@foo.network"
```

## Genesis validators

<table>
  <tr>
    <th>Moniker</th>
    <th>Details</th>
    <th>Identity</th>
    <th>Site</th>
  </tr>
  <tr>
    <td><pre>NodeStake</pre></td>
    <td>NodeStake is the professional validator, infrastructure provider and IBC relayer. ⚛️7*24h Services | https://twitter.com/Nodestake_top</td>
    <td>
      <p align="center"><img width="80px" src="https://s3.amazonaws.com/keybase_processed_uploads/5912a329316356b98611c807d0c11e05_200_200.jpg"/></p>
      <a href="https://keybase.io/nodestake">94EFE192B2C52424</a></td>
    <td><a href="https://nodestake.org">https://nodestake.org</a></tr>
  <tr>
    <td><pre>HSS</pre></td>
    <td></td>
    <td>
      <p align="center"><img width="80px" src="https://s3.amazonaws.com/keybase_processed_uploads/53b008f12f37e3ffa0dec3676d375a05_200_200.jpg"/></p>
      <a href="https://keybase.io/highstakes">2CB281A714F6133B</a></td>
    <td><a href="https://highstakes.ch">https://highstakes.ch</a></tr>
</table>