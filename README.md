# EOS ZMQ Light API

The API is providing two fundamental functions for EOS blockchain:

* Retrieve all token balances and resources for an account:
 `http://apihost.domain/api/account/eos/ACCOUNT`

* Retrieve all accounts in all known EOS networks dependent on a public key:
 `http://apihost.domain/api/key/KEY`

* In addition, adding `?pretty=1` to the URL, you get the resulting JSON
  sorted and formatted for human viewing.

* Also a request `http://apihost.domain/api/networks` will list all
  known networks and their information.


## Installation

```
sudo apt-get install git make cpanminus gcc g++ libzmq5-dev mariadb-server \
libmysqlclient-dev libdbi-perl libjson-xs-perl libjson-perl

sudo cpanm DBD::MariaDB
sudo cpanm ZMQ::Raw
sudo cpanm Starman

cd /opt
git clone https://github.com/cc32d9/eos_zmq_light_api.git
cd eos_zmq_light_api

sudo mysql <sql/lightapi_dbcreate.sql
sh setup/add_eos_mainnet.sh

vi /etc/default/lightapi_eos
# add the ZMQ socket details:
# DBWRITE_OPTS=--pull=tcp://127.0.0.1:5556

# Optionally, edit /etc/default/lightapi_api and adjust variables
# that are predefined in systemd/lightapi_api.service

cd systemd
sh install_systemd_dbwrite.sh
sh install_systemd_api.sh

# Now Starman is serving HTTP requests and you can build your HTTP service
# with nginx or exposing Starman directly
```




## Copyright and License

Copyright 2018 cc32d9@gmail.com

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


## Donations and paid service

ETH address: `0x7137bfe007B15F05d3BF7819d28419EAFCD6501E`

EOS account: `cc32dninexxx`
