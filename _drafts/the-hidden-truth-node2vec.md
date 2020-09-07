# The Hidden Truth: A Recommender System with Node2Vec

Recently I tried to use Node2Vec in a recommender systems context. 

Node2Vec is a network representation algorithm presented by [reference] which is based on the Word2Vec model by [reference]. Word2Vec has been used before in recommender systems: Item2Vec and Cust2Vec are two examples of such previous research efforts. In Item2Vec orders are considered 'sentences' and products coincide with 'words'. Customer2vec uses trace logs of website. Such trace logs contain all events related to a specific customer, which enable Doc2Vec (a variant of Word2Vec) to learn customer specific profiles. (see: [link](https://opensource.com/article/17/9/representation-learning?utm_campaign=intrel) )

However, my goal was different: given a database with all orders for all clients of a firm, is a model based on Node2Vec able to make relevant recommendations for the clients? If we consider clients and products to be nodes of a network. Then every order is a set of links connecting a client to a set of products. This way a network of sales orders emerges on which Node2Vec can be applied. 

The idea is simple: Node2Vec can learn a vector representation for every node in the network (a node embedding). These embeddings are the result of applying Word2Vec on a set of Random Walks. A Random Walk is a collection of nodes sampled from the network/graph as if you were walking from node to node. Random walks form the equivalent of 'sentences' and a single node is a 'word'. When two nodes have a high probability of co-occuring on a random walk --> is this what is optimized?

