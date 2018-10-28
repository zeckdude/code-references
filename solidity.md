Blockchain class notes

Gas

1. How exactly does gas prevent infinite loops
2. How do you pay for mistakes made
3. What exactly qualifies as a “mistake”?

Smart Contract Tools

1. If web3js is poorly written, why is there no alternative?

Other Blockchains

1. What’s the major differences between Ethereal and the other blockchains (EOS, Neo, Lisk)?

Solidity

1. If they create a $117000000 million bug, are people weary of still using solidity?
2. Are there alternatives?

Other

1. What’s an ERC20 token?



Notes

Types
bool: 0 or 1
uint
address: wallet or ethereum address
string: always surrounded by double-quotes	


Structures
array: Series of object that are the same size and type
mapping: Hash tables between two different types
Struct: Used to define new types
enum: Used to create a user-defined type


Functions
Fallback functions: default functions that smart contract goes to when no data is provided
Constructor: Runs once immediately after deployment

Unique keywords
msg.sender: Address of person/contract calling function
msg.value: Amount of ETH sent in the transaction
block.number: Number of block order in Ethereum
block.timestamp: Time the block was mined (~15 sec/block)

Accessibility
external: Can be called by other contracts and via transactions
internal: Can be called from within its own contract or derived contracts
public: Can be called externally or internally
private: Can be called from within its own contract

Error Handling
require: To check conditions on input, returns leftover gas
assert: To check internal errors, consumes all gas in transaction

Modifiers
Change the behavior of the function they’re attached to
Check a condition before running a function
onlyOwner: Permission control
payable: Allows for interaction with ether
view: Doesn’t modify state
pure: Doesn’t read from nor modify state

Event
Stores arguments that functions take and stores in logs
emit: Broadcasts arguments to listeners in user interface
indexed: Attribute that allows arguments to be searched for

Optimization
Each line of code that is written costs gas
Gas costs real-world money
Sloppy code becomes expensive very quickly

