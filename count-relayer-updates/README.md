# count-relayer-updates.js
uses Tendermint RPC endpoint to walk blocks, counts ValidatorSetChangePackets for every relayer, outputs to .csv
- txs using fee-grant are assigned to the granter account

configure via config object:
```
vim app.js
```
to run:
```
npm install
npm run start
```