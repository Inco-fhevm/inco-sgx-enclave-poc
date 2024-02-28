### Build `incod` to run the node

To build `incod` binary, which can be used to run node and interact with SGX-dependent functionality, use the following command:
```sh
make build
```

This command will build binary with SGX in hardware mode (your hardware should support SGX to run binary in this mode) and will put enclave file (`enclave.signed.so`) to `$HOME/.incod-enclave` directory. 

If you want to setup local node for testing purposes without possibility to connect to Inco testnet as full node, you can build `incod` in simulation mode using the following command:
```sh
SGX_MODE=SW make build
```

Also, if you want to put enclave file (`enclave.signed.so`) to other directory, you can specify `ENCLAVE_HOME` env variable. For example:
```sh
ENCLAVE_HOME=/tmp/enclave-directory make build
```
### Build `incodcli`

If your OS / hardware doesn't support SGX even in simulation mode, you can build CLI which will allow you:
- sending queries
- transactions
- manage your keys 
- debug commands, such as address conversion 

Below you can see table with build commands for each OS / CPU

| OS / arch             | command                     |
|-----------------------|-----------------------------|
| linux amd64           | `make build-linux-cli-amd`  |
| linux arm64           | `make build-macos-cli-arm`  |
| macos with M1 chip    | `make build-macos-cli-arm`  |
| macos with Intel chip | `make build-macos-cli-amd`  |
| windows               | `make build-windows-cli`    |

### License Terms
This software is based in full or partially on  https://github.com/SigmaGmbH/swisstronik-chain.
Please see https://github.com/SigmaGmbH/swisstronik-chain/blob/master/LICENSE for details
