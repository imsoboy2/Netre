# Introduction

TRE-PRO: a new in-network TRE architecture that leverages the power and flexibility of emerging programmable switches to provide on-path detection and elimination of redundant traffic transmission in the networks. In TRE-PRO, a pair of nodes in a routing path cache packets to reduce bandwidth consumption and gain performance revenue. Each pair of cache nodes in the networks maintains per-pair synchronized cache stores to accurately encode and decode the on-the-fly traffics.

We implement TRE-PRO prototype in P4 language for BMv2 simple_switch target for proof of concepts.

NOTE: Due to the privacy issue for sharing real network traffic traces provided by UPC's Broadband Communication Research Group, in the next test scenario, we provide generated dataset (Src/Dst request distiribution: zipf dist., Payload data: Amazon food review data).
# How to run?

## Testbed setup

1. Download dataset
```bash
wget http://snap.stanford.edu/data/finefoods.txt.gz
gzip -d finefoods.txt.gz
```

2. Create files for test and compile codes
```bash
./setup.sh
```


## Run test script

### Reduction ratio

To run test, simply do:

    ./run_tests.sh


This script generates packets according to a  Zipf distribution with different skewed parameters(0.4 - 0.8) and calculates reduction ratio.

You can see the test results through this command line.

    python show_result.py


### Clean up the test

To delete all build files, and logs:

    ./clear.sh
