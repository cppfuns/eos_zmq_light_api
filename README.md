# EOS ZMQ Light API



## Installation

```
sudo apt-get install cpanminus gcc g++ libzmq5-dev mariadb-server \
libmysqlclient-dev libdbi-perl \
libjson-xs-perl libjson-perl

sudo cpanm DBD::MariaDB
sudo cpanm ZMQ::Raw

sudo mysql <sql/lightapi_dbcreate.sql

sudo cpanm Starman

perl /opt/eos_zmq_token_api/scripts/lightapi_dbwrite.pl --sub=tcp://10.0.0.1:6003

starman master --listen 127.0.0.1:5001 --workers 6 /opt/eos_zmq_token_api/api/token_api.psgi
```

## Public API endpoint

http://tokenapi.eoswatch.info/api/account/b1



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
