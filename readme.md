## ECDSA Node

A client-server architecture based project setup to understand basic working of blockchain.  Since there is just a single server on the back-end handling transfers, this is clearly very centralized. We won't worry about distributed consensus for this project.

Incoporated Public Key Cryptography. Used Elliptic Curve Digital Signatures so the server only allows transfers that have been signed for by the person who owns the associated address.
 
### Client

The client folder contains a [react app](https://reactjs.org/) using [vite](https://vitejs.dev/). To get started, follow these steps:

1. Open up a terminal in the `/client` folder
2. Run `npm install` to install all the depedencies
3. Run `npm run dev` to start the application 
4. Now you should be able to visit the app at http://127.0.0.1:5173/

### Server

The server folder contains a node.js server using [express](https://expressjs.com/). To run the server, follow these steps:

1. Open a terminal within the `/server` folder 
2. Run `npm install` to install all the depedencies 
3. Run `node index` to start the server 

The application should connect to the default server port (3042) automatically! 
To edit initial balances you can modify 'balances' object in index.js

### Signature Generation
To generate signature run sign.js.
Enter amount (must be same as to be transferred) and private key (of sender) as input.
Copy the signature generated and paste it in the input field for signature (as shown in below images).

![image](https://github.com/IshanKarn/ecdsa-node/assets/58829422/929135ca-a87a-4682-beec-6890b969f198)

### Transactions

##### Valid Transaction
Note: *Use Ethereum type address for sender and recipient (last 20 bytes of the hash of the public key)*
![image](https://github.com/IshanKarn/ecdsa-node/assets/58829422/4c57e9cd-891d-4cbe-b624-35952a8b76c0)

##### Transaction With Invalid Sender's Address
![image](https://github.com/IshanKarn/ecdsa-node/assets/58829422/6ce74b8c-f907-40f2-b69b-89868424e2cb)

##### Transaction With Invalid Signature (Or Amount Different From Amount Used While Signature Generation)
![image](https://github.com/IshanKarn/ecdsa-node/assets/58829422/7b975fc2-bea7-40f0-8ec2-048b448ef000)

##### Transaction When Sender Has Insufficient Balance
![image](https://github.com/IshanKarn/ecdsa-node/assets/58829422/20380cf2-972f-4e58-8a59-c4cc3147a74b)
