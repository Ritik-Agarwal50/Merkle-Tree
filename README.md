# Merkle-Tree

A Merkle Tree is a tree data structure (typically a binary tree) of hashes, where each leaf node contains the hash of a block of data (eg: the transaction hash in a blockchain), and each parent node contains the hash resulting from the concatenation and hashing of its children node’s hashes.

This tree is used to verify and demonstrate that the hash of a leaf node is part of the hash of the root node in an efficient way, since we only need a small set of the hashes of the tree to carry out this verification.

This data structure is often used in distributed systems, like in Bitcoin and other blockchains, to verify if a transaction hash belongs to the Merkle root of a block header, in a lightweight, efficient and fast way.

The use of Merkle Tree/Root/Proof in Bitcoin allows the implementation of Simple Payment Verification (SPV), which is a way for lightweight clients to check if a transaction is actually part of a block, without the client having to download the whole block or the whole blockchain.
By only having the block header with the Merkle root, the transaction it wants to verify, and the Merkle proof structure obtained from a trusted Bitcoin node, it can try to reconstruct the Merkle root hash and validate the transaction.


# Example of a Merkle Tree

![image](https://user-images.githubusercontent.com/76695769/207103018-96c0761a-840e-486c-b100-1e7bcf67ae85.png)




Notice how the last hash, 3ebc, was copied and added to the end of the list. This is needed to be able to concatenate it with itself and hash it, since we hash in pair and if the hash list length is odd, then we copy it and add it to the end of the list to make the hash list even. The same happens with fcc1.
Each of the tree levels is called a hash list.


# Merkle Root

The Merkle root is the root node of the tree. In our example above, it’s the node with the da07 hash.


# For More details About Merkle Tree Visit -
https://medium.com/coinmonks/merkle-tree-a-simple-explanation-and-implementation-48903442bc08
