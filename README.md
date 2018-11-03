# Clocal Azure

![CLocal-Azure](./src/assets/clocal-logo.png)

![[CLocal-Azure](https://github.com/cloudlibz/clocal-azure)](https://img.shields.io/badge/CLocal-Azure-blue.svg)
[![Join the chat at https://gitter.im/cloudlibz/clocal-azure](https://badges.gitter.im/cloudlibz/clocal-azure.svg)](https://gitter.im/cloudlibz/clocal-azure?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Emulation engine for Azure Services 

_Clocal-azure_ provides an easy-to-use test/mocking framework for developing Cloud applications.

Currently features are under development.

# Overview

_Clocal-azure_ spins up the following core Cloud APIs on your local machine:

## Services & Ports
* **Azure Functions** at http://localhost:9574
* **Azure Storage** at http://localhost:9569 (Blobs), http://localhost:9570 (Queues), http://localhost:9571 (Tables)
* **Azure CosmosDB** (Only windows supported) port will be given by the emulator with the IP address
* **Azure API App Service** at http://localhost:9567

## Getting Started

### Requirements \*

* NodeJS (^8.9.4)
* yarn (^1.6.0)
* Docker

### Steps

Step 1: Clone the project
```
git clone https://github.com/cloudlibz/clocal-azure.git
```

Step 2: Go to the working directory
```
cd clocal-azure
```

Step 3: Install yarn and dependencies
```
yarn
```

Step 4: Run the commands via following method
```
yarn start <command> 
```
or
```
clocal <command>
```

## Commands

### All Services at once

Step 1: Go to ```compose.env``` file and specify the path to create the images for *azure functions* and *azure api app service* and *azure cosmosdb*.

Step 2: Run the shell script below.
```
sh compose.sh
```
or
```
yarn service
```
![Compose-Result](./src/assets/compose-result.png)


### Azure Functions

* **Init Functions**
```
clocal function-init <folder>
```
Azure functions working directory is located in example/azure-functions.
You can create a folder inside the location and give the folder location.
Then attach the init file where the service starting file.
Example: ```clocal function-init function-sample```

* **Start Functions**
```
clocal function-start
```
* **Stop Functions**
```
 clocal function-stop 
 ```

### Azure Storage 
Azure storage comprises of azure blobs, queues and tables. See the example/azure-storage for sample project.

* **Start Storage**
```
clocal storage-start
```
* **Stop Storage**
```
clocal storage-stop
```
* **Clear all files created**
```
clocal storage-clear
```

### Azure CosmosDB (Only Windows Supported)

* **Init CosmosDB**
```
clocal cosmosdb-init
```
This will create the in-built image of the Cosmos DB emulator and will be on ready state to start the container.

* **Start CosmosDB**
```
clocal cosmosdb-start
```
* **Stop CosmosDB**
```
clocal cosmosdb-stop
```

### Azure API App Service 

Azure API working directory is located in example/azure-api-service.
You can create a folder inside the location and give the folder location.
Then attach the init file where the service starting file.

Example: ```clocal api-start ./ api.json```

```
clocal api-start <folder> <init-file>
```

## Example Documents

* **[Azure Functions](./docs/azure-functions.md)**
* **[Azure Storage](./docs/azure-storage.md)**
* **[Azure Cosmos DB](./docs/azure-cosmosdb.md)**

## Demo Video Series

* **[Video Playlist](https://www.youtube.com/watch?v=rpUJ44D_7Tk&list=PLbd4A5tkijhDGRQp6BcrwGhRvS0TU8zhQ)**

## Testing

```
yarn test
```

## Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE.md](./LICENSE) file for details

## Acknowledgments

clocal-azure is initially developed for the Google Summer of Code 2018. Special thanks goes to my mentors [@rehrumesh](https://github.com/rehrumesh), [@lasitha-petthawadu](https://github.com/lasitha-petthawadu) and [@rajikaimal](https://github.com/rajikaimal) and [CloudLibz Organization](https://github.com/cloudlibz).


