# Earth data

Server data for the Vintage Story mod **Earth** (from Earth 2.0): terrain, water and ground. The Earth server fetches
these files once into `VintagestoryData/ModData/earth/data` before it builds a world, and every world and every later
version of the mod reuses them. A game client needs none of them: the climate data a client reads is inside the mod.

They used to be split over eight "data pack" mods only because an archive on the Vintage Story mod database may hold
40 MB. Earth 2.0 is one mod, and these files live here instead (decision 0066 in the Earth repository).

The full GLO-90 land heights (8.6 GB) and the lake and river outlines are in
[earth-glo90](https://github.com/Temporal-Poets-Society/earth-glo90); the 30″ ground sets are in
[earth-ground](https://github.com/Temporal-Poets-Society/earth-ground).

## Files

The data is in the release [`ed-v1`](../../releases/tag/ed-v1): 38 files, 275.7 MB, plus `manifest.json`,
`ATTRIBUTION.txt` and `eula_F.pdf`.

| File | Group | Bytes | What it is | SHA-256 |
|---|---|---|---|---|
| `terrain.bin` | terrain | 30,347,837 | the 2′ base grid every world reads: heights and sea depths, land/sea/lake flags, lake levels, ice thickness | `e733cca42ac825c13005482a87f4abf2147480bcb7c41f5c2abbc71cde1e4640` |
| `summits.bin` | terrain | 2,474,923 | how far ETOPO's 30″ peaks stand above the 2′ surface (mountain tiles) | `9fe7dfacf0ee051c0c22fd98c20d2deb88831bafc5c17e3b09e23c7014368704` |
| `peaks.json` | terrain | 6,642,227 | named peaks with surveyed heights | `a779f5a67940b797b420437e0b0f574c3161b839ef64e4c0df98ced9293e7e5f` |
| `glaciers.bin` | terrain | 1,220,181 | glacier coverage (RGI 6) | `06c854595621eacfec624ec445ad80a9da32026ec87b1a28618a3ca71b0216ab` |
| `rivers.bin` | water | 12,132,790 | the rivers on the built-in heights (HydroRIVERS) | `aaebda1d8abf95a75e740c1d21774aa360419582bf774a4fcdda21e73446a8b5` |
| `islands.bin` | water | 9,891,240 | island outlines | `2b9bc440aede37e03bc2f28219da50ec650fdf05c24caa46966d2944b4d72dc6` |
| `coasts.bin` | water | 9,477,193 | coast outlines (GSHHG) | `2d5e2ad38166113f0ad7253f699a9ca556730717f365c423738d18ad9a5dfc1f` |
| `lakes.bin` | water | 17,444 | terminal and salt lakes | `cbec2376eba342320098a7856d6ec7f62463273699ae6c3edb064e794718560d` |
| `shores.bin` | water | 126,401 | lake shores | `691673039f64ee8a85207ec8acad84ebd35b8b7b261ef99a23970b2c035cc8ce` |
| `shores-osm-1.bin` | water | 2,220,894 | what beaches are made of (OpenStreetMap's beaches by surface; Earth 2.0.0-rc.7, decision 0070; added 12 November 2026) | `3151094cc16f753550e48dd33540a3928b8bc1a31556a8904855d0893fc101de` |
| `sea-referee.bin` | water | 6,262,394 | coast and island corrections from GLO-90's water mask | `3d823a2e280fa6c12504f07f87069f81ecc8721109c89b33eab4f6d8ff1c7fe7` |
| `rivers-glo90-snap.bin` | water | 4,510,852 | river courses moved into the mask's water (courses 2-3) | `022a374374a662bdd0e015d9f37965d9a985b3fba7114000f8f949bdf375475f` |
| `rivers-glo90-snap-2.bin` | water | 8,235,212 | river courses on the mask's water with measured widths (courses 4) | `fa87c5895b6a0ff6df1def67f7908c994747d6effd51de4549b1f9a0c39c9dc1` |
| `rivers-glo90-arms.bin` | water | 185,836 | river side arms (courses 2-3) | `8748a916ead1e2fd9202e076c9ad6b53d5c2e6427f7fdd3cfca21783b9be057a` |
| `rivers-glo90-arms-2.bin` | water | 223,228 | river side arms (courses 4) | `e7f7f4408c9bb027b5e61ff1f522beadcda46ead3471986ba3baebb70b753bf7` |
| `stream-heads-1.bin` | water | 4,712,127 | real stream heads and seeps for springs | `bffcc5f7ee6f89bff423e261695f7ec1dd40449af08810c976da7143f25380ad` |
| `glo90c-index.bin` | terrain | 177,324 | index of the included GLO-90 land heights | `d55d203d436fa7b14d2d6c5de4a412090e9a0bc6f6ce0f70b969481f87926977` |
| `glo90c-1.bin` | terrain | 39,594,940 | included GLO-90 land heights, part 1 | `69edad31d3df4e66afd1f10fe52ea61e54622c41295a36d510dfaad3813c558e` |
| `glo90c-2.bin` | terrain | 39,791,138 | included GLO-90 land heights, part 2 | `1ce4ab9eab2fc57ca3f79bd8547ab0254d35dd4273989ffaa02763713a8276b4` |
| `glo90c-3.bin` | terrain | 39,796,380 | included GLO-90 land heights, part 3 | `0b98d0ef7343c86b14ef5fa127db81e3cd5ff295359e357d152c116eb26b0a22` |
| `glo90c-4.bin` | terrain | 9,984,522 | included GLO-90 land heights, part 4 | `6a669fda9a68b0c411dc7330014b2a93f401cb154823bdcbf5dc49251777e103` |
| `rivers-glo90.bin` | water | 23,976,950 | the rivers laid onto GLO-90 valleys | `461aff76afe30afd8ef4261646a7ce7e72251e0e10652274670b118ffd6baed4` |
| `baltic-emodnet-seabed.egt` | ground | 15,473 | 2′ ground set (rock, soil and cover layers) | `797adda893b22b7dfcefc2cdf68b518ec4322dc26afa51cffe6f3573e943bbc1` |
| `baltic-soilgrids.egt` | ground | 526,591 | 2′ ground set (rock, soil and cover layers) | `2e6ff10d489fb4075749cd4e481a4551ae85c02e2dbb1492b594e789725b2cd8` |
| `global-chorlton.egts` | ground | 1,519,321 | 2′ ground set (rock, soil and cover layers) | `c451fd9fab691adf4fba023d7027071906f44dfdff4e52a7046b7493d59fe57c` |
| `global-gum.egt` | ground | 32,765 | 2′ ground set (rock, soil and cover layers) | `cd7ef04a1c1f53758e4263f57f4401f1ec7cdcde41b2e2d80f617fd183e75c3f` |
| `global-permafrost.egts` | ground | 1,364,328 | 2′ ground set (rock, soil and cover layers) | `2a0cc1b3576675f15c0068a13bb0bd365bc21ca21fe9431d1b166ef5559a2f6b` |
| `global-provinces.egts` | ground | 1,576,653 | 2′ ground set (rock, soil and cover layers) | `b10ce96ad6b3d8bd29b52c6e9672d9ee8c1123aff15131e95a70b2730f805f96` |
| `global-shangguan.egts` | ground | 11,840,388 | 2′ ground set (rock, soil and cover layers) | `c728dff70954b0a01e006b088957b0120db0655f14288ded9017baea6e413387` |
| `global-soilgrids.egts` | ground | 13,199,820 | 2′ ground set (rock, soil and cover layers) | `2a940a389cc03609510e4e5b90a99f293e8ce324971b4014bbc9f05dae0b6e88` |
| `latvia-quaternary.egt` | ground | 89,493 | 2′ ground set (rock, soil and cover layers) | `4c03aa9813d49c2294fb327cda3ca1a1ae6f2c104e0f66f1ef266720f300c607` |
| `wetlands.bin` | ground | 2,288,691 | wetland shares (GLWD v2) | `644824a1e2942791dd2625034217cd6640cd2196b79cde2213ab22376c40f932` |
| `soil-site.bin` | ground | 1,618,438 | soil sites for the fire rules and the trees' soil fit | `407f6dc3657bb396f00732c694cb3b26d8d8c08cadde4a6be3f324c48f2acb25` |
| `floodplains.bin` | ground | 2,707,673 | natural flood levels of dry-season rivers in arid land | `e7b8f25ff0700548d256c20dc0dc81a6c61bb62d1cb1299e0ae52d3a910ef57f` |
| `europe-igme5000.egt` | ground | 4,139 | 2′ ground set: pre-Quaternary age and rock type in Europe (IGME 5000) | `fa64748b2573d0a24f4e9f09196182bdb6f577e606d220688060834cb2d5c11b` |
| `global-crust1.egt` | ground | 54,610 | 2′ ground set: depth to basement from sediment thickness (CRUST1.0) | `b9531d7b0d02534e380090a57a45c25a60e8b7d21566a0c07b252429030a1a5e` |
| `global-glaciation.egts` | ground | 138,764 | 2′ ground set: where Northern Hemisphere ice sheets stood (last glacial maximum and older), Batchelor et al. 2019 | `b3879efe65a0f9bd92c3022bc8eccd77bdf0b7d168d048aa027b01d2634e5dac` |
| `baltic-basement.egt` | ground | 25,178 | 2′ ground set: depth to basement in the Baltic, CRUST1.0 corrected to deep boreholes | `db62dbdcde817f9c6f79f3639dd7c33c8aef83e1000610cef87d3454df60053a` |

To install by hand (a server without internet), put the files in `VintagestoryData/ModData/earth/data/` on the server
(or the single-player machine). Earth checks each file's size and SHA-256 and uses only files that match.

### Version

`ed-v1` names this set of files, not a version of the mod. Earth versions that list these names use them as they are.
A changed file gets a new name or a new tag; files in a release are never replaced or deleted, so a world made with an
older Earth still finds the data it was made from.

### manifest.json

```json
{ "format": "earth-data", "formatVersion": 1, "release": "ed-v1", "installTo": "VintagestoryData/ModData/earth/data",
  "files": [ { "name": "terrain.bin", "group": "terrain", "bytes": 30347837, "sha256": "…" }, … ] }
```

## Licence and notices

Each file is adapted from the sources named in [ATTRIBUTION.txt](ATTRIBUTION.txt) and is distributed under those
sources' licences; see [LICENSE.md](LICENSE.md). This repository, Earth and Temporal Poets Society are not endorsed by
the data providers.