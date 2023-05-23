# Basic Blockchain knowledge

### Ledger :

it's open book that anyone can add a line to it or see everything.
line would be added by a transaction.
every line or transaction has a Digital signature and the signature must be unique.

### Signature:

it's a combination of the message and the Private key .
every person has private and public key.
signature = message + private_key
verify_signature = message + signature + public_key

### Hash function:

sha256 is function that can take any kind of input and make it a hash with the length of 256( it a 0,1 phrase).

### Proof Of Work:

every one have a ledger > the ledger should be turned to a hash > for doing this we need the hash function like SHA256 > with the help of sha256 , we need to find the best hash, the one with more zero at the first of the hash > for finding something like this the only way is to guess the number and require a lot of work or computation > after finding such hash , it can be verified very easily. > all of this computation is depend on transaction and the ledger list if it change the hash would change. > all this is proof of work.

### Blockchain:

as a transaction is valid when it signed by it's owner , a block is valid when it has a proof of work.
each block has the hash of previous block.
so that's the main reason of calling it blockchain it's because blocks are chain together with their hashes.

### Miner:

block creator,
it means his/her listen to transaction and gather them in a block and try to make a hash (Proof Of Work), a hash with 60 zero for example and once they find it, they would broadcast the block they found.
there is a reward for creating new block and it called block reward.
for miner it's just like mini lottery that everyone guessing number as fast as they can until one lucky individual find a number that makes the hash of the block start with many zero and a reward for doing this.
miners get paid with transaction fee .

in bitcoin a block can contain 2400 transactions.<br/>
as miners increase finding block with many zero would be harder than before.

### Decentralized:

all the computers are connected to each other instead of central server.

### Two vital Data Structures:

_Pointers_ - variables that keep information about the location of another variable. Specifically, this is pointing to the position of another variable.

_Linked lists_ - a sequence of blocks where each block has specific data and links to the following block with the help of a pointer.

### Two kind of node:

_member node :_<br/>
only can initiate/receive transaction<br/>
_validator node :_<br/>
can initiate/ receive and validate transactions.

### All blockchain structures fall into three categories:

1. Public blockchain architecture
2. Private blockchain architecture
3. Consortium blockchain architecture

<strong>_Node:_</strong><br/>
user or computer within the blockchain architecture (each has an independent copy of the whole blockchain ledger).

<strong>_Transaction:_</strong><br/>
smallest building block of a blockchain system (records, information, etc.) that serves as the purpose of blockchain.

<strong>_Block:_</strong><br/>
a data structure used for keeping a set of transactions which is distributed to all nodes in the network

<strong>_Chain:_</strong> a sequence of blocks in a specific order

<strong>_Miners:_</strong><br/>
specific nodes which perform the block verification process before adding anything to the blockchain structure.

<strong>_Consensus (consensus protocol):_</strong><br/>
a set of rules and arrangements to carry out blockchain operations.
