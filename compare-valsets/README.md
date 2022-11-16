# compare-valsets

## install

- configure via `provider` and `consumer` objects in [compare-valsets.js](./compare-valsets.js)
- to install dependencies: `npm install`
- to run script: `npm run start`

## Tracing and comparing ICS28 valsets

Documentation related to [GOC Task 9 & 10](https://github.com/hyphacoop/ics-testnets/tree/main/game-of-chains-2022#validator-sets-monitoring)

Shortly after the the first GOC consumer chain `sputnik` started producing blocks, an issue about possible deviating validator sets on the consumer chain was raised by CrowdControl, Virtual Hive and CryptoCrew (as described in [this gist]()https://gist.github.com/clemensgg/579983404afd4e906a4419fe4e81d100)

In an effort to verify/falsify this thesis we updated our compare-valset script to:
- compare (sha256 hash) every `VSC` of `consumer` against ALL historic `VSC`s of `provider`
- record every `VSC` on `provider` and `consumer` in a .csv file for visualisation
- alert and dump `VSC` states when `VSC` checks are inconsistant (validator set of `consumer` is not the last or any historic validator set of `provider`)
- live mode to be able to alert asap if inconsistencies arise

**UPDATE 2022/11/16 - published first batch of valset visualisations for `provider`, `sputnik` and `apollo`

Interactive charts:
`provider`: https://datawrapper.dwcdn.net/Cq4dt/4/
`sputnik`: https://datawrapper.dwcdn.net/93hwB/1/
`apollo`: https://datawrapper.dwcdn.net/UyhCP/2/

![provider](./export/provider-valsets_140869.png?raw=true)
![sputnik](./export/sputnik-valsets_87540.png?raw=true)
![apollo](./export/apollo-valsets_88789.png?raw=true)