# ETH-AVAX-Module-3-Contract

In this project, we are suggested to create our own token on local HardHat. After that, the contract creator should be able to mint tokens to a provided address. Any user should be able to burn and transfer tokens.

# Process of Connecting Hardhat Network with Remix

Step 1: Visit the Project Directory
Open your terminal and navigate to the project directory where my Solidity contract is written.

Step 2: Run npm install @remix-project/remixd Command
In the terminal, run the following command to start the remixd service:
```bash
npx remixd -s <project_directory> --remix-ide https://remix.ethereum.org
```
Replace `<project_directory>` with the absolute path of your project directory. This will create a connection between Remix IDE and your local project directory.

Step 3: Open Remix IDE
Open Remix IDE on your browser.

Step 4: Connect with Localhost Workspaces
In your Remix IDE, connect to Localhost Workspaces by selecting the "default_workspace" and switching to the "Localhost" button in the top-right "Workspaces" corner. This will connect your project directory to Remix IDE.

Step 5: Compile the Contract
After writing your contract successfully, compile the contract in Remix IDE. Find and open your ".sol" file in your contract folder and switch to the "Solidity Compiler" tab on the left-hand side of IDE. Click on the "Compile" button to compile the contract.

The following is your contract:
```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyToken is ERC20, Ownable {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) Ownable(msg.sender) {
        // Initial owner is set by the Ownable constructor
    }

    function mint(address account, uint256 amount) public onlyOwner {
        _mint(account, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}
```

Step 6: Deploy and Interact with the Contract
In the top-left corner, in the "Environment" dropdown, select "Injected Web3" to connect to the local Hardhat.

To interact with the contract effectively, follow these steps:

1. Go to the "Deployed Contracts" section and select the contract name.
2. Observe the available functions and variables of the contract.
3. Click the "Deploy" button to deploy the contract.
4. Once the contract is successfully deployed, interact with its functions as follows:
   - Provide the required parameters for the function you want to use.
   - Click the corresponding function button to execute the function.

Congratulations! You have now connected your local Hardhat network with Remix, and you have deployed and interacted with a contract.

To ensure everything works smoothly, make sure that your local Hardhat network is running using `npx hardhat node` and that you have installed all necessary dependencies with `npm install`.

To customize the contract to suit your specific requirements, refer to the provided code and add relevant information and code in a well-structured manner within the Token contract.

## Authors
Abhigyan Pushkar

## License
This project is licensed under the MIT License
