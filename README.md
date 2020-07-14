# Iroha_steps
Steps to install and use Blockchain Iroha Network
Iroha
docker network create srcmake-iroha-network

docker run --name some-postgres \
-e POSTGRES_USER=postgres \
-e POSTGRES_PASSWORD=mysecretpassword \
-p 5432:5432 \
--network=srcmake-iroha-network \
-d postgres:9.5

docker volume create blockstore

git clone -b master https://github.com/hyperledger/iroha --depth=1
— depth 1 will pull only the latest code.

docker run -it --name iroha1 \
-p 50052:50052 \
-v /tmp/iroha/example:/opt/iroha_data \
-v blockstore:/tmp/block_store \
--network=srcmake-iroha-network \
--entrypoint=/bin/bash \
hyperledger/iroha1:latest

Once connected to the docker run the below command to start the node
irohad --config config.docker --genesis_block genesis.block --keypair_name node0

Interacting with Iroha
docker exec -it iroha /bin/bash

iroha-cli -account_name admin@test

New transaction
Create an asset
Add one more command to transaction
Add asset quantity
Add one more command to transaction
Transfer Assets
Send to Iroha Peer
New query
Get Accounts Assets
Send to Iroha Peer

https://www.youtube.com/watch?v=OsiFXY7ShuQ
