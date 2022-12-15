# Simple-wallet-smart-contract
A very simple smart contract wallet implementation using solidity.

#description
assuming that only the owner can set allowances for other addresses to withdraw funds from the balances. 

#Actors 
guardians: a minimum of three guardians approve the new owner. 
owner: can set new guardians and transfer funds. 

#functions

proposeNewOwner(address payable _newOwner) : 

callers: guardians
condition: 3 confirmations minimum are needed.
confirmation: the newOwner(address) becomes the new owner.
Desc: new owner is set via a voting process.


setAllowance(address _for, uint256 _amount): 

callers: owner
condition: caller should be the owner.
confirmation: allowance is set for the given address.
Desc: Allowance is set by the owner for an address to withdraw funds. 


setGuardian(address _guardian, bool _isguardian): 

callers: owner
condition: caller should be the owner.
confirmation: a new guardian is set by the owner.
Desc:a new guardian is set by the owner.  


transfer(address payable _to,  uint _amount, bytes memory _payload):

callers: owner/allowed address
condition: caller should be the owner or the address that is allowed.
           amount to be withdrawn shoud exist in the address's respective balance. 
confirmation: funds are transferred to the requestee.
Desc: a function that allows the owner or the allowed address to transfer funds.   
