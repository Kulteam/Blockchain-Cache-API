# MONCoin® Blockchain Cache API

## Prerequisites

* MariaDB/MySQL with InnoDB support
* [RabbitMQ](https://www.rabbitmq.com/)
* [MONCoin®: Blockchain Data Collection Agent](https://github.com/Kulteam/Blockchain-data-collection-agent)
* [MONCoin®: Blockchain Relay Agent](https://github.com/Kulteam/Blockchain-relay-agent)
* [Node.js](https://nodejs.org/) LTS

## Foreword

We know that this documentation needs cleaned up and made easier to read. We'll compile it as part of the full documentation as the project moves forward.

## Setup

1) Clone this repository to wherever you'd like the API to run:

```bash
git clone https://github.com/Kulteam/Blockchain-Cache-API.git
```

2) Install the required Node.js modules

```bash
cd Blockchain-Cache-API && npm install
```

3) Use your favorite text editor to change the values as necessary in `config.json`

**Note:** Make sure you use a read-only database user for security reasons

```javascript
{
  "bindIp": "0.0.0.0",
  "httpPort": 80,
  "corsHeader": "*"
}
```

4) Fire up the script

```bash
export RABBIT_PUBLIC_SERVER=localhost
export RABBIT_PUBLIC_USERNAME=yourrabbitmqusername
export RABBIT_PUBLIC_PASSWORD=yourrabbitmqpassword
export MYSQL_HOST=localhost
export MYSQL_PORT=3306
export MYSQL_USERNAME=yourdbusername
export MYSQL_PASSWORD=yourdbpassword
export MYSQL_DATABASE=yourdbname
node index.js
```

5) Optionally, install PM2 or another process manager to keep the service running.

```bash
npm install -g pm2@latest
pm2 startup
pm2 start index.js --name Blockchain-Cache-API -i max
pm2 save
```

## API

See https://docs.turtlepay.io/blockapi/ for the full REST API provided by this package.

###### (c) 2018-2019 TurtlePay® Development Team
