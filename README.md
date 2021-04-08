![Miner's stats page](https://raw.githubusercontent.com/belmix/Ethereum-pool/master/pool_main.png)

# Pool server (realized the possibility of mining , automatic payments in finding a pool block for all miners , the ability to establish a pool of commission)

This software includes:
* A pool master for miner handling
* A pool controller

## Warning

The software is not well tested and it's a work in progress, use at your own risk.

## Install

* git clone https://github.com/belmix/Ethereum-pool.git
* cd Ethereum-pool
* Change IP Front-end "/usr/local/lib/python2.7/dist-packages/flask/app.py" - host = 'localhost'


## Requirements

* golang

# Python 2
* python2
* python2 flask
* python2 requests
* python2 pysqlite3
* python2 poloniex
* python2 ethhashrpc

# Python 3
* python3
* python3 flask
* python3 requests
* python3 pysqlite3
* python3 poloniex
* python3 ethhashrpc

# Python3 Solving
pip3 install --target=/usr/local/python3.7/site-packages --upgrade requests

## Configuration

For first, configure the pool master:

1. Open poolmaster/pool.go
2. Choose a secure key, and replace the one proposed in line 46
3. Set the poolPort at line 46; this will be used by pool miners
4. Set the port of your ethereum daemon at line 47
5. Enter the "Ethereum-pool" directory and run ``` ./make_poolmaster.sh ```

Now edit ethpool.py:

1. At line 15, set the previously secure key
2. At line 21, set the pool fee
3. At line 22, set your coinbase address

## Startup

1. Start geth or similar with rpc ``` geth --rpc ```
2. First run ``` ./poolmaster/pool ```
3. Start the pool server with ``` python ethpool.py start ```
4. go http://localhost:5000/

## Connect
http://IP:5082/miner/{miner}/{difficulty}/{worker}

## contact 
admin@belmix.ru
