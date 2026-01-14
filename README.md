# OpenRCX Calibration Using Open Source Tools

This repository includes scripts used to generate OpenRCX technology files using [Magic VLSI](http://opencircuitdesign.com/magic/index.html).

The following PDKs are currently supported: sky130, gf180mcu and ihp-sg13.

## Start Here

```
git clone https://github.com/efabless/openrcx-calibration.git
cd openrcx-calibration
./calibrate-magic.sh
```

## Setup

[Install Nix](https://librelane.readthedocs.io/en/latest/installation/nix_installation/index.html) to enable OpenROAD (for pattern and rule generation) and magic for extraction.

```
nix-shell
```

If you want to install the tools manually, the following versions were tested:

- openroad: edf00dff99f6c40d67a30c0e22a8191c5d2ed9d6
- magic: 8.3.581

## Run Calibration With Magic

### For sky130

First, export the PDK and PDK_ROOT variable:

```
export PDK=sky130A
export PDK_ROOT=/path/to/pdk_root/
```

Next, run the calibration for each corner:

```
./scripts/run-magic.sh nom
./scripts/run-magic.sh min
./scripts/run-magic.sh max
```

### For gf180mcu

First, export the PDK and PDK_ROOT variable:

```
export PDK=gf180mcuD
export PDK_ROOT=/path/to/pdk_root/
```

Next, run the calibration for each corner:

```
./scripts/run-magic.sh nom
./scripts/run-magic.sh min
./scripts/run-magic.sh max
```

### For ihp-sg13

First, export the PDK and PDK_ROOT variable:

```
export PDK=ihp-sg13g2
export PDK_ROOT=/path/to/pdk_root/
```

Next, run the calibration for each corner:

```
./scripts/run-magic.sh nom
./scripts/run-magic.sh min
./scripts/run-magic.sh max
```

## Run Calibration With SPEF Extractor

TODO: Needs a clean-up.

```
export PDK=sky130A
```

```
./scripts/run-spef_extractor.sh $PDK nom"
./scripts/run-spef_extractor.sh $PDK min"
./scripts/run-spef_extractor.sh $PDK max"
```
