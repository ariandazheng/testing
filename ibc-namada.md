# Details
```
Namada channel: 918
Osmosis channel: 6358
```

**IBC:** 
```
2024-03-15T19:01:37.293084Z  INFO ThreadId(01) running Hermes v1.7.4+38f41c6
2024-03-15T19:01:37.544254Z  INFO ThreadId(01) Creating new clients, new connection, and a new channel with order ORDER_UNORDERED2024-03-15T19:01:58.498322Z  INFO ThreadId(01) foreign_client.create{client=osmo-test-5->shielded-expedition.88f17d1d14:07-tendermint-0}: 🍭 client was created successfully id=07-tendermint-2932
2024-03-15T19:02:02.104533Z  INFO ThreadId(01) foreign_client.create{client=shielded-expedition.88f17d1d14->osmo-test-5:07-tendermint-0}: 🍭 client was created successfully id=07-tendermint-2919
2024-03-15T19:02:19.966897Z  INFO ThreadId(01) 🥂 shielded-expedition.88f17d1d14 => OpenInitConnection(OpenInit { Attributes { connection_id: connection-1435, client_id: 07-tendermint-2932, counterparty_connection_id: None, counterparty_client_id: 07-tendermint-2919 } }) at height 0-145599
2024-03-15T19:02:58.740411Z  INFO ThreadId(01) 🥂 osmo-test-5 => OpenTryConnection(OpenTry { Attributes { connection_id: connection-2650, client_id: 07-tendermint-2919, counterparty_connection_id: connection-1435, counterparty_client_id: 07-tendermint-2932 } }) at height 5-6033596
2024-03-15T19:03:03.027191Z  WARN ThreadId(01) client consensus proof height too high, waiting for destination chain to advance beyond 0-145602
2024-03-15T19:03:25.503405Z  INFO ThreadId(01) 🥂 shielded-expedition.88f17d1d14 => OpenAckConnection(OpenAck { Attributes { connection_id: connection-1435, client_id: 07-tendermint-2932, counterparty_connection_id: connection-2650, counterparty_client_id: 07-tendermint-2919 } }) at height 0-145605
2024-03-15T19:03:42.624437Z  INFO ThreadId(01) 🥂 osmo-test-5 => OpenConfirmConnection(OpenConfirm { Attributes { connection_id: connection-2650, client_id: 07-tendermint-2919, counterparty_connection_id: connection-1435, counterparty_client_id: 07-tendermint-2932 } }) at height 5-6033607
2024-03-15T19:03:45.682502Z  INFO ThreadId(01) connection handshake already finished for Connection { delay_period: 0ns, a_side: ConnectionSide { chain: BaseChainHandle { chain_id: shielded-expedition.88f17d1d14 }, client_id: 07-tendermint-2932, connection_id: connection-1435 }, b_side: ConnectionSide { chain: BaseChainHandle { chain_id: osmo-test-5 }, client_id: 07-tendermint-2919, connection_id: connection-2650 } }
2024-03-15T19:04:08.795808Z  INFO ThreadId(01) 🎊  shielded-expedition.88f17d1d14 => OpenInitChannel(OpenInit { port_id: transfer, channel_id: channel-918, connection_id: None, counterparty_port_id: transfer, counterparty_channel_id: None }) at height 0-145609
2024-03-15T19:04:27.048633Z  INFO ThreadId(01) 🎊  osmo-test-5 => OpenTryChannel(OpenTry { port_id: transfer, channel_id: channel-6358, connection_id: connection-2650, counterparty_port_id: transfer, counterparty_channel_id: channel-918 }) at height 5-6033618
2024-03-15T19:04:52.173883Z  INFO ThreadId(01) 🎊  shielded-expedition.88f17d1d14 => OpenAckChannel(OpenAck { port_id: transfer, channel_id: channel-918, connection_id: connection-1435, counterparty_port_id: transfer, counterparty_channel_id: channel-6358 }) at height 0-145613
2024-03-15T19:05:11.304382Z  INFO ThreadId(01) 🎊  osmo-test-5 => OpenConfirmChannel(OpenConfirm { port_id: transfer, channel_id: channel-6358, connection_id: connection-2650, counterparty_port_id: transfer, counterparty_channel_id: channel-918 }) at height 5-6033629
2024-03-15T19:05:14.398169Z  INFO ThreadId(01) channel handshake already finished for Channel { ordering: ORDER_UNORDERED, a_side: ChannelSide { chain: BaseChainHandle { chain_id: shielded-expedition.88f17d1d14 }, client_id: 07-tendermint-2932, connection_id: connection-1435, port_id: transfer, channel_id: channel-918, version: None }, b_side: ChannelSide { chain: BaseChainHandle { chain_id: osmo-test-5 }, client_id: 07-tendermint-2919, connection_id: connection-2650, port_id: transfer, channel_id: channel-6358, version: None }, connection_delay: 0ns }
SUCCESS Channel {
    ordering: Unordered,
    a_side: ChannelSide {
        chain: BaseChainHandle {
            chain_id: ChainId {
                id: "shielded-expedition.88f17d1d14",
                version: 0,
            },
            runtime_sender: Sender { .. },
        },
        client_id: ClientId(
            "07-tendermint-2932",
        ),
        connection_id: ConnectionId(
            "connection-1435",
        ),
        port_id: PortId(
            "transfer",
        ),
        channel_id: Some(
            ChannelId(
                "channel-918",
            ),
        ),
        version: None,
    },
    b_side: ChannelSide {
        chain: BaseChainHandle {
            chain_id: ChainId {
                id: "osmo-test-5",
                version: 5,
            },
            runtime_sender: Sender { .. },
        },
        client_id: ClientId(
            "07-tendermint-2919",
        ),
        connection_id: ConnectionId(
            "connection-2650",
        ),
        port_id: PortId(
            "transfer",
        ),
        channel_id: Some(
            ChannelId(
                "channel-6358",
            ),
        ),
        version: None,
    },
    connection_delay: 0ns,
}
```

**From Namada to Osmosis:** 
```
namadac --base-dir $BASE_DIR \
    ibc-transfer \
    --amount 2 \
    --source misspb1337_namada \
    --receiver osmo1690p0q6kcdwkwnu92342c4jc9xy33d6t4gh7fv \
    --token naan \
    --channel-id channel-918 \
    --node https://namada.rpc.liveraven.net/
Enter your decryption password: 
Transaction added to mempool.
Wrapper transaction hash: 69CA1E5D17D9F55B204DA58FA0CCF9078BE6CC500061116605E8F648A0D603D0
Inner transaction hash: 95BB016F3BB6EA871702463580696E81122FBCAF78982005D6C884D6B8CD38B5
Wrapper transaction accepted at height 145717. Used 24 gas.
Waiting for inner transaction result...
Transaction was successfully applied at height 145718. Used 6193 gas
```

**From Osmosis to Namada:** 
```
osmosisd tx ibc-transfer transfer \
  transfer \
  channel-6358 \
  tnam1qp6tys3d84r3nk6efwjr33g6gql9s4artcmu9ylg \
  1000000uosmo \
  --from misspb1337_osmosis \
  --gas auto \
  --gas-prices 0.04uosmo \
  --gas-adjustment 1.2 \
  --node "http://127.0.0.1:26657" \
  --home "$HOME/.osmosisd" \
  --chain-id osmo-test-5 \
  --yes
Enter keyring passphrase (attempt 1/3):
gas estimate: 131244
code: 0
codespace: ""
data: ""
events: []
gas_used: "0"
gas_wanted: "0"
height: "0"
info: ""
logs: []
raw_log: '[]'
timestamp: ""
tx: null
txhash: 708B429BE7472FA799DDF57072B6EC359B571EADEF38E0B582A7A0FBAE8353B8 /
```
txhash: https://www.mintscan.io/osmosis-testnet/tx/708B429BE7472FA799DDF57072B6EC359B571EADEF38E0B582A7A0FBAE8353B8?height=6033749


**Balance Namada:** 
```
namadac balance --owner misspb1337_namada --node https://namada.rpc.liveraven.net/
naan: 270
transfer/channel-918/uosmo: 1000000
```

**Balance Osmosis:** 
```
osmosisd query bank balances osmo1690p0q6kcdwkwnu92342c4jc9xy33d6t4gh7fv"
balances:
- amount: "23982253"
  denom: uosmo
pagination:
  next_key: null
  total: "0"
```

