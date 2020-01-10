Creating a Few `ProfitSplitter` Contracts

Building three smart contracts with the purpose to  automate paying associate-level employees, distributing profits to different tiers of employees, and distributing company shares in a "deferred equity incentive plan." One smart contract for each purpose.

The code and logic of the code was tested first on the localhost 8545, after that on the kovan test network.

How the contracts work:

    First Smart Contract:

    This smart contract to pay associate-level employees, AssociateProfitSplitter.sol, is deployed for the contract owner that gives the address account of each employee, nobody else could do this. 
    The contract deposits the payment of the employees to their address account using a deposit function that can only be called through a function() external payable (fallback). That fallback function can only be called for someone that send a value (msg.value) to the  contract, so only the owner of the contract has the motivation for sending ethers to the contract for paying its employees (attached the completed starter code AssociateProfitSplitter.sol). Inside the deposit function the value is divided by 3 and any remainder generated due the whole numbers of the quotient of this division is transfered back to the msg.sender. 
    Pictures of deployed contract on localhost 8545 and kovantest network are attached.
    Pictures are attached about the blocks that created the contract, and blocks mined where the fallback function is called activating the deposit function that make the payments to the employees.

    The addres of the smart contract AssociateProfitSplitter address of the contract is 0x3A5E3B83F141489703F37d49E9ADE918b33a088B (Kovan Testnet)

    Pictures when fallback function is activated using the kovan testnet are attached.

    Second Smart Contract:

    This smart contract that splits the profit among associate employees, TieredProfitSplitter.sol, is deployed for the contract owner that gives the address account of each employee. So nobody else could do this, but the owner. 
    The same that the first contract the owner send the value, profits, for being splitted and distributted to their address account of its employees using a deposit function. That deposit function can only be called through a function() external payable (fallback). The fallback function can only be called for someone that send a value (msg.value) to the  contract, so only the owner of the contract has the motivation for sending ethers to the contract for being splitted among its employees.
    Into the deposit function the contract splits the value or profit using a simple algorithm that divides the value by 100 points getting the value of one point. Then multiply the value of each point by the porcentage assigned to each employee (60, 25, 15) to get the amount to be transfered to the address of each employee. In this contract the remainders are transferred to the associate with the greatest porcentage.

    Pictures of deployed contract on the localhost 8545 and kovantest network are attached. Also are attached pictures when the external payable function (fallback) is called activating on this way the deposit function that distributes the profits to its employees.

    The address of the smart contract TierredProfitSplitter is 0x3A7032A8e71AC66a9Acd25dF80A07A0394952406, Kovan Testnet.


    Third Smart Contract:

    This third smart contract that distribute 1000 shares to one employee in a period of 4 years, DeferredEquityPlan.sol, checked the vested period, no overcome the 1000 shares, only human resources call the distribute function that vested the shares to the employee, the employee should be active etc. This contract is deployed for the contract owner in this case human resources stablishing the address of the human resources and giving the address account of the active employee. 
    The contract uses a distribute function that requires being called only for human resources, existence of vested period, employee be active, distributed shares less than the total shares, checking even if the employee has not cash out after 5 or more years making sure the 1000 shares only.
    The contract has a function that deactivate the contract that only human resources can do it through a require condition. Also the contract has an external payable function that revert any payment to the contract because this contract does not envolve ethers. 

    The completed start code has been attached to the present.
    Also a completed test code has been attached to this note. The test code includes the fast-forward function in order to test the smart contract. I decided to create  a new file to avoid any mistake.

    Pictures of the deployed contract on the localhost 8545 and kovantest network are attached. 
    Pictures of the deployed test contract on the kovantest network are attached.

    The addres of the smart contract DeferredEquityPlan.sol is 0xBEa6Cd451cF975c0EABB991536a00366B3418658, Kovan Testnet
   
     
    
    
     