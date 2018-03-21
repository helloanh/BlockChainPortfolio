# BlockChainPortfolio
applications using IBM blockchain based on Coursera course  

### What is Block Chain ? 

"A trusted, distributed ledger which has a shared set of pbusiness processes across all members of the business netowrk."    

+ Blockchain is a shared ledger technology that allows any participant in a business network to access *one* system of the record, or a ledger.  

+ Why adopt blockchain? Currently, most business networks are often inefficient when dealing with multiple transactions across multiple parties.  The process is costly, and many duplication of work happens when the record moves around parties.  

### Notes  

+ The current system is inefficient, expensive, and vulnerable.  

+ How is this related to Bitcoin?   Bitcoin is an unregulated shadow-currency with the interesting property of anonymity.  It's also the biggest, first live use of blockchain.  However, blockchain for business differs from Bitcoin in three important areas:  
		1. prioritize identity over anonymity.  prioritize selective endorsements over proof of which - we get to choose who in the business network validates a particular trasnaciton  
		2. much more computationally efficient  
		3. the technology is for very broad set of assets, and not just cryptocurrency  

#### Requirements for a blockchain in a business environment:    

	1. shared ledger - append-only distributed system of record shared across business network      

	2. smart contract - business terms embedded in transaction database and executed with transactions    

	3. privacy - ensuring appropriate visiblity; transactions are secure, authenticated and verifiable     

	4. trust - transactions are endorsed by relevant participants  

## Linux Foundation Hyperledger Project 

Q: How can IBM help you apply blockchain? IBM is a premier member of the Linux Foundation Hyperledger Project, which is an open source, collaborative effort that seeks to advance blockchain technologies. IBM also offers the IBM Blockchain Platform that can help you build and operate a complete business network. The Platform also provides tools to help you align the needs of developers and business leaders in your organization.  

+ IBM is one of the founding members of the Linux Foundation Hyperledger Project  

+ One of the major project is the Fabric composer, a middleware for blockchain for customers adn business  

+ Originally, we have to render the smart contracts and block chain in the Go language.  This is an inhibitor of time and value, so creating a fabric composer to allow people to think about blockchain in high level of abstraction such as assets, transactions, participants in the business network.  Then to model the operation of the business netowrk and smart contracts using JavaScript.  

### Hyperledger Composer   

	+ What is it? an application development framework that helps you create Hperledger Fabric applications.  It has components such as APIs, a modeling language, and a programming model.  

	+ Instead of using chaincode to render smart contracts and other blockchain components, the Hyperledger Composer allows you to model, build, adn deploy business netowrks and applications much faster.  

	+ Composer defines JavaScript APIs to submit transactions and to create, retrieve, update, and delete assets within asset registries.  


#### Benefits of Hyperledger Composer  

	+ Increases understanding - bridges simply from business concepts to blockchain  
	+ Saves time - develop blockchain apps more quickly and cheaply  
	+ Reduces risk - well tested, efficient design conforms to best practice. easy to test with traditinoal devOps tool.   
	+ Increases flexibility - higher level abstraction makes it easier to iterate    


#### Deploying Business Network Application in Fabric  

```
# the enrollmentID and secret key are what you will receive on the Fabric, from someone who configured the identify for you

composer network deploy -a path/of/bna/file -i EnrollmentIdHere -s enrollementsecretkey

# to see our container on docker
docker ps -a  

# getting rest-api  
```

### Demo Labs fro IBM Blockchain Hyperledger coursework 

#### [Lab 1 - Blockchain Car Auction Instructions](coursera-IBM-BlockChain-for-Developers/lab1-my-car-auction-network/lab1_blockchain_car_auction.pdf) 
+ [Lab 1 - Hyper Composer Playground for Car Auction Network](coursera-IBM-BlockChain-for-Developers/lab1-my-car-auction-network/README.md)   

#### [Lab 2 Instructions](https://hyperledger.github.io/composer/tutorials/developer-tutorial.html)
+ [Lab 2 - Hyperledger Composer blockchain with Angular 2](coursera-IBM-BlockChain-for-Developers/lab2-hyperledger-blockchain-solution-angular2/README.md)



  














	
