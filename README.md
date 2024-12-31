# Decentralized-Voting-System-Using-Ethereum-Blockchain

The Decentralized Voting System using Ethereum Blockchain is a secure and transparent solution for conducting elections. Leveraging Ethereum's blockchain technology, this system ensures tamper-proof voting records, enabling users to cast their votes remotely while maintaining anonymity and preventing fraud. Explore this innovative project for trustworthy and decentralized voting processes.

**Note:** This project is not maintained anymore.

## Features
- Implements JWT for secure voter authentication and authorization.
- Utilizes Ethereum blockchain for tamper-proof and transparent voting records.
- Removes the need for intermediaries, ensuring a trustless voting process.
- Admin panel to manage candidates, set voting dates, and monitor results.
- Intuitive UI for voters to cast votes and view candidate information.

## Requirements
- Node.js (version – 18.14.0)
- Metamask
- Python (version – 3.9)
- FastAPI
- MySQL Database (port – 3306)

## Installation

1. Open a terminal.
2. Clone the repository by using the command:
   git clone https://github.com/Animesh-Kumar/Decentralized-Voting-System-Using-Ethereum-Blockchain.git
# Setup Instructions

## Ganache Setup
1. Create a workspace named `development` in **Ganache**.  
2. Add `truffle-config.js` to the **Truffle Projects** section by clicking the **ADD PROJECT** button.

## Metamask Setup
1. Install the **Metamask** browser extension from [here](https://metamask.io/).  
2. Create a wallet in Metamask (if you don’t already have one) and import accounts from **Ganache**.  
3. Add a custom network to Metamask:  
   - **Network Name**: Localhost 7575  
   - **RPC URL**: `http://localhost:7545`  
   - **Chain ID**: 1337  
   - **Currency Symbol**: ETH  

## Database Setup
1. Open **MySQL** and create a database named `voter_db`. (Avoid using XAMPP.)  
2. Create a new table named `voters` using the following SQL query:  
   ```sql
   CREATE TABLE voters (
       voter_id VARCHAR(36) PRIMARY KEY NOT NULL,
       role ENUM('admin', 'user') NOT NULL,
       password VARCHAR(255) NOT NULL
   );

Example table:

diff
Copy code
+--------------------------------------+-------+-----------+
| voter_id                             | role  | password  |
+--------------------------------------+-------+-----------+
|                                      |       |           |
+--------------------------------------+-------+-----------+
Install Truffle globally:

bash
Copy code
npm install -g truffle
Navigate to the root directory of the repository and install Node.js dependencies:

bash
Copy code
npm install
Install Python dependencies:

bash
Copy code
pip install fastapi mysql-connector-python pydantic python-dotenv uvicorn uvicorn[standard] PyJWT
Usage
Update the database credentials in the ./Database_API/.env file.

Open a terminal in the project directory.

Start Ganache and its development workspace.

Open another terminal and navigate to the project’s root directory. Launch the Truffle console:

bash
Copy code
truffle console
Compile the smart contracts:

bash
Copy code
compile
Exit the Truffle console.

Bundle app.js with Browserify:

bash
Copy code
browserify ./src/js/app.js -o ./src/dist/app.bundle.js
Start the Node.js server:

bash
Copy code
node index.js
Open another terminal, navigate to the Database_API folder, and start the database API server:

bash
Copy code
cd Database_API
uvicorn main:app --reload --host 127.0.0.1
In a new terminal, migrate the Truffle contract to the local blockchain:

bash
Copy code
truffle migrate
Access the voting app at http://localhost:8080/.

Code Structure
perl
Copy code
├── blockchain-voting-dapp            # Root directory of the project.
    ├── build                         # Directory containing compiled contract artifacts.
    |   └── contracts                 
    |       ├── Migrations.json       
    |       └── Voting.json           
    ├── contracts                     # Directory containing smart contract source code.
    |   ├── 2_deploy_contracts.js     
    |   ├── Migrations.sol            
    |   └── Voting.sol                
    ├── Database_API                  # API code for database communication.
    |   └── main.py                   
    ├── migrations                    # Ethereum contract deployment scripts.
    |   └── 1_initial_migration.js    
    ├── node_modules                  # Node.js modules and dependencies.
    ├── public                        # Public assets like favicon.
    |   └── favicon.ico               
    ├── src                           
    |   ├── assets                    # Project images.
    |   |   └── eth5.jpg              
    |   ├── css                       # CSS stylesheets.
    |   |   ├── admin.css             
    |   |   ├── index.css             
    |   |   └── login.css             
    |   ├── dist                      # Compiled JavaScript bundles.
    |   |   ├── app.bundle.js         
    |   |   └── login.bundle.js       
    |   ├── html                      # HTML templates.
    |   |   ├── admin.html            
    |   |   ├── index.html            
    |   |   └── login.html            
    |   └── js                        # JavaScript logic files.
    |       ├── app.js                
    |       └── login.js              
    ├── index.js                      # Main entry point for Node.js application.
    ├── package.json                  # Node.js package configuration.
    ├── package-lock.json             # Lockfile for package dependencies.
    ├── README.md                     # Project documentation.
    └── truffle-config.js             # Truffle configuration file.
