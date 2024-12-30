# PHP-Escrow as Pure-PHP-Escrow-System

PHP-Escrow is an escrow system with highly structured conditions so that buyers and sellers can agree together on a suitable exchange. 

The necessary PHP dependencies must be activated on the server (apt install php php-sqlite3 php-gd php-mbstring).

- The Authentification Token for the admin access is : ugVZGoKHaMmX1dmGM0jdMcX0390a2EnDKCXKe8ylYPbKsxIid1fuob2yarzadsZd

It also uses MoneroD and Electrum for the 2 cryptocurrencies that work with it (bitcoin and monero). The configurations for these are as follows:

- Electrum : 

{
    "blockchain_preferred_block": {
        "hash": "000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f",
        "height": 0
    },
    "config_version": 3,
    "dynamic_fees": false,
    "fee_per_kb": 70000,
    "load_wallet": "/var/www/.electrum/wallets/default_wallet",
    "rpcpassword": "yourpassword",
    "rpcport": 7777,
    "rpcuser": "user"
}

- Monero :

wallet-file=wallet
password=yourwalletpassword
rpc-login=user:yourpassword
rpc-bind-port=18080
daemon-address=node.moneroworld.com:18089

## HELP FOR WALLETS : 

- Electrum

Install latest version of Electrum.

Electrum "config" need to be in /var/www/.electrum 

config file of .electrum is in (.)electrum folder.

In /var/www :
-> chown -R www-data:www-data .electrum
-> chown -R www-data:www-data html

To run Electrum :
-> export ELECTRUMDIR=/var/www/.electrum
-> source ~/.bashrc
-> electrum daemon -d
-> electrum load_wallet

- Monero

Install latest version of monero

config file of monero is in monero folder.

To run Monero :
-> cd monero
-> nohup ./monero-wallet-rpc --config-file monero-wallet-rpc.conf

