# tendermintKVStoreBI
Tendermint provides a tutorial for getting started with built-in apps that run in the same process as Tendermint core (https://docs.tendermint.com/master/tutorials/go-built-in.html). The tutorial seems slightly out of date (some of the import paths method signature have changed). This example works locally on a Mac (Intel).

Prequisites: 
- Make sure Go is installed: (https://go.dev/doc/install)
- Make sure tendermint is installed: 
```
brew install tendermint
```

Set-up:
1. First, clone and navigate to the project :
```
 git clone https://github.com/zkmiyavi/tendermintKVStoreBI.git
 cd tendermintKVStoreBI
```


2. Create directory for the validator configs (in the project directory): 
```
mkdir -p tmp/example
```

3. Set $TMHOME: 
```
export TMHOME="/tmp/example" tendermint init validator
export GO111MODULE=on
```

4. Build the binary (no optimizations/flags): 
``` 
go build
```

5. Run the binary. This will start the app in the same process as Tendermint Core: 
```
./tendermintKVStoreBI -config "./tmp/example/config/config.toml"
```
6. Revisit the source tutorial for messages to pass to the app: https://docs.tendermint.com/master/tutorials/go-built-in.html
