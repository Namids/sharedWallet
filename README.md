# sharedWallet


Real-World Use-Case for this Project¶
💡 Allowance for Children per day/week/month to be able to spend a certain amount of funds.

💡 Employers give employees an allowance for their travel expenses.

💡 Businesses give contractors an allowance to spend a certain budget.

Development-Goal¶
👛 Have an on-chain wallet smart contract.

💸 This wallet contract can store funds and let users withdraw again.

✌️ You can also give "allowance" to other, specific user-addresses.

🚫 Restrict the functions to specific user-roles (owner, user)

🔍 Re-Use existing smart contracts which are already audited to the greatest extent



Note that since Allowance is Ownable, and the SharedWallet is Allowance, therefore by commutative property, SharedWallet is also Ownable.


Remove the Renounce Ownership functionality
Now, let's remove the function to remove an owner. We simply stop this with a revert. 
contract SharedWallet is Allowance {

    //...

    function renounceOwnership() public override onlyOwner {
        revert("can't renounceOwnership here"); //not possible with this smart contract
    }

    //...
}
