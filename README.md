# arXiv4TGC

arXiv4TGC is a set of academic datasets (includes arXivAI, arXivCS, arXivMath, arXivPhy and arXivLarge) for large-scale temporal graph clustering.

This is an early version of our dataset, and we will be updating it with more information as we go along.

## Download datasets

arXivAI:
arXivCS:
arXivMath:
arXivPhy:
arXivLarge:

## Dataset details

Files included in the current version：

1. a temporal graph (in adjacency list)

```
Data format: (source node, target node, timestamp)
```

2. node labels (node2label.txt)

```
Data format: (node ID, label)
```

3. features (generate by postional encoding)

```
Data format: 
The first line introduces the number of nodes N and feature dimensions d
thereafter for each line: node ID, d-dimensional vector
```

