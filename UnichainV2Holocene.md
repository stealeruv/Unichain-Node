## update node before 18th Dec 22 UTC

```
nano $HOME/unichain/.env.sepolia
```

Save the RPC URL 

CTRL + X then Y and Press ENTER

### Save nodekey 
```
cat ~/unichain/geth-data/geth/nodekey
```

Save it safe

---

```
cd unichain
```
### Update node 
```
git stash
git pull
```
### Change rpc
```
nano .env.sepolia
```

**Change RPC to before value for OP_NODE_L1_ETH_RPC= | OP_NODE_L1_BEACON=**

CTRL + X then Y and Press ENTER

```
nano .env
```

### Change the host dir 
```
HOST_DATA_DIR=/$HOME/root/unichain/geth-data
HOST_NODE_DATA_DIR=/$HOME/root/unichain/opnode-data
```

CTRL + X then Y and Press ENTER

### Start Node
```
docker-compose up -d
```

### Check logs
```
docker compose logs -f unichain-execution-client-1
```

### Health Check
```
curl -X POST -H "Content-Type: application/json" --data '{"id":1,"jsonrpc":"2.0","method":"eth_blockNumber","params":[]}' http://localhost:8545
```

**Output should be : {"jsonrpc":"2.0","id":1,"result":"0x0"}**


**Follow** : https://x.com/cryptoconsol

