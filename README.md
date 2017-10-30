# btcgpu-build
WIP: Testnet is not up yet, you can only run local "regtests"

## How to use
### Turbo Mode
Pull the slim image

    docker pull oxide/btcgpu-docker:master-regtest

Run the bitcon gold node in a detached container in the background.

    ./run.sh
    
You can then play with this node on bash with something like:

    docker exec -it <container_id> /bin/bash -l
    bitcoin-cli -regtest generate 101
    bitcoin-cli -regtest getbalance

### Dev and Test Mode
You can get the huge full build environment if you want to compile, test, or debug.

    docker pull oxide/btcgpu-docker:master-regtest-dev
    
Then you could do something like run tests. This will drop you into bash in the container, in the bitcoin gold source directory.

    ./run-dev.sh
    make check
    
### Building
Note that this can rebuild all the dependencies from source, which can take quite some time...

To build the development image with all the build and test dependencies

    ./build-dev.sh
    
To build the slim run image

    ./build.sh
