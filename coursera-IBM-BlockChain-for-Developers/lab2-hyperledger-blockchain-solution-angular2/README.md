#Lab2 Log

Based on https://hyperledger.github.io/composer/tutorials/developer-tutorial.html  


### Step 1: Create Business Network Structure
```
yo hyperledger-composer:businessnetwork
```

```
#output
akhs-MacBook-Pro:lab2-hyperledger-blockchain-solution-angular2e? yo hyperledger-composer:businessnetwork
Welcome to the business network generator
? Business network name: anh-tutorial-network
? Description: my implementation of tutorial-network following the instructions on https://hyperledger.gi
thub.io/composer/tutorials/developer-tutorial.html
? Author name:  Anh K. Hoang
? Author email: akhoang88@gmail.com
? License: Apache-2.0
? Namespace: org.example.biznet
   create index.js
   create package.json
   create README.md
   create models/org.example.biznet.cto
   create test/logic.js
   create lib/logic.js

```

```
# create permissions access control file
touch permissions.acl
# edit the permissions as default
```


### Step 2: Defining a business network

Now update your cto and js files.  



### Step 3: Generate a business network archive

Package the files as .bna (business network archive) file.  

```
cd anh-tutorial-network
composer archive create -t dir -n .

```

```
#output
akhs-MacBook-Pro:anh-tutorial-network akh$ composer archive create -t dir -n .
Creating Business Network Archive


Looking for package.json of Business Network Definition
	Input directory: /Users/akh/sandbox/BlockChainPortfolio/coursera-IBM-BlockChain-for-Developers/lab2-hyperledger-blockchain-solution-angular2e? /anh-tutorial-network

Found:
	Description: my implementation of tutorial-network following the instructions on https://hyperledger.github.io/composer/tutorials/developer-tutorial.html
	Name: anh-tutorial-network
	Identifier: anh-tutorial-network@0.0.1

Written Business Network Definition Archive file to 
	Output file: anh-tutorial-network@0.0.1.bna

Command succeeded

```

### Step 4: Deploying the business network  

After creating the .bna file, the business network can be deployed to the instance of Hyperledger Fabric. Normally, information from the Fabric administrator is required to create a PeerAdmin identity, with privileges to deploy chaincode to the peer. However, as part of the development environment installation, a PeerAdmin identity has been created already.  

After the runtime has been installed, a business network can be deployed to the peer. For best practice, a new identity should be created to administrate the business network after deployment. This identity is referred to as a network admin.  

*The Hypercomposer Fabric needs two requirements to deploy a business network:*  
	1. The Hyperledger Composer chaincode installed on the peer, then .bna file sent to the peer. A new participant, identity, and associated card must be created to be the network administrator.  
	2. The network administrator business network card must be imported for use, and the network can then be pinged to check it is responding.  

```
# To install the composer runtime, run the following command:
# composer runtime install --card PeerAdmin@hlfv1 --businessNetworkName tutorial-network
composer runtime install --card PeerAdmin@hlfv1 --businessNetworkName anh-tutorial-network

```

```
akhs-MacBook-Pro:anh-tutorial-network akh$ composer runtime install --card PeerAdmin@hlfv1 --businessNetworkName anh-tutorial-network
✖ Installing runtime for business network anh-tutorial-network. This may take a minute...
Error: Card not found: PeerAdmin@hlfv1
Command failed

```

I didn't create a card.  Instructions here: https://hyperledger.github.io/composer/installing/development-tools.html.  Run the following three commands:
```
  cd ~/fabric-tools
  ./startFabric.sh
  ./createPeerAdminCard.sh
```

```
#output for third command to create the admin card:
akhs-MacBook-Pro:fabric-tools akh$ ./createPeerAdminCard.sh
Development only script for Hyperledger Fabric control
Running 'createPeerAdminCard.sh'
FABRIC_VERSION is unset, assuming hlfv1
FABRIC_START_TIMEOUT is unset, assuming 15 (seconds)

Need to have composer-cli installed at version 0.16
# I run npm install -g composer-cli, then ./createPeerAdminCard.sh script again ...
# see issue ticket at: https://github.com/hyperledger/composer/issues/2714

#Bug fixes for nvm step
nvm install v8.9.1
nvm use 8.9.1
cd ~/fabric-tools/
npm install -g  composer-cli  --unsafe-perm

```
You can start and stop your runtime using ~/fabric-tools/stopFabric.sh, and start it again with ~/fabric-tools/startFabric.sh.  

At the end of your development session, you run ~/fabric-tools/stopFabric.sh and then ~/fabric-tools/teardownFabric.sh. Note that if you've run the teardown script, the next time you start the runtime, you'll need to create a new PeerAdmin card just like you did on first time startup.    






