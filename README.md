FundMe Smart Contract 💸
Welcome to the FundMe project! This is a decentralized crowdfunding smart contract built using the Foundry framework.

Users can send ETH to this contract, but there's a catch: they have to send at least $5 USD worth of ETH. To figure out the real-time conversion rates, the contract taps into Chainlink Data Feeds. Once the contract is funded, only the contract owner (the address that deployed it) can withdraw the funds.

(Huge shoutout to Patrick Collins for the amazing educational content that inspired this build!)

🚀 Features
Minimum Funding Limit: Requires a minimum deposit of $5 USD (calculated dynamically using Chainlink Oracles).

Funder Tracking: Keeps a secure record of who funded the contract and how much they contributed.

Owner-Only Withdrawals: Only the deployer of the contract can withdraw the accumulated funds.

Gas Optimized: Includes a cheaperWithdraw function that caches state variables in memory to save on gas costs during loop executions.

🛠️ Prerequisites
Before you start, make sure you have the following installed on your machine:

Git

Foundry (which includes forge, cast, anvil, and chisel)

💻 Getting Started
Here's how to get this running on your local environment.

1. Clone the repository

Bash
git clone <YOUR_GITHUB_REPO_URL>
cd <YOUR_PROJECT_DIRECTORY>
2. Install dependencies
Because this project uses Chainlink, you'll need to make sure your Foundry environment has the right dependencies. Run:

Bash
forge install smartcontractkit/chainlink-brownie-contracts@0.6.1 --no-commit
(Note: You might need to set up your foundry.toml to remap the @chainlink imports depending on your setup!)

3. Build the project
Compile the smart contracts to make sure everything is working cleanly:

Bash
forge build
🧪 Testing
Foundry makes testing incredibly fast. To run the test suite (assuming you've written some in your test folder):

Bash
forge test
To see how much gas your contract functions are using:

Bash
forge test --gas-report
🚢 Deployment
To deploy this to a local test network (Anvil), first spin up your local node:

Bash
anvil
Then, deploy the contract using Forge scripts (you'll need to create a deployment script in your script folder):

Bash
forge script script/DeployFundMe.s.sol --rpc-url http://localhost:8545 --private-key <YOUR_ANVIL_PRIVATE_KEY> --broadcast
🤝 Contributing
If you want to poke around, optimize the gas even further, or add new features, feel free to fork this repo and submit a PR!

📜 License
This project is licensed under the MIT License.
