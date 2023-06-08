# arXiv4TGC

arXiv4TGC is a set of academic datasets (includes arXivAI, arXivCS, arXivMath, arXivPhy and arXivLarge) for large-scale temporal graph clustering.

This is an early version of our dataset, and we will be updating it with more information as we go along.

## Download datasets

Google Drive: https://drive.google.com/drive/folders/1-4O3V0ZcC_f8yP5ylW9CX-lE6qucbFfh?usp=sharing

Baidu Disk:

These downloaded datasets need to be placed under the "data" folder.

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

## Baseline

We implement the HTNE model for temporal graph clustering on our datasets. Please download the Baseline.zip and unzip it.

In this way, under the Baseline folder, there are three subfolders: HTNE (model code), emb (node embeddings) and Clustering (test code).

For the "HTNE" subfolder, you can:

```
python main.py
```

Note that we have two types of clustering test:

(1) Evaluated during training: we perform an evaluation of the clustering effect after each epoch is completed, and this result will be given during the model training.

(This way is not applicable to both arXivPhy and arXivLarge data sets because of the longer time required for clustering. You can freely change it in the code.)

```
if self.the_data == 'arxivLarge' or self.the_data == 'arxivPhy':
  acc, nmi, ari, f1 = 0, 0, 0, 0
else:
  acc, nmi, ari, f1 = eva(self.clusters, self.labels, self.node_emb)
```

(2) Evaluated after training, where we save node embeddings every 20 epochs, with a separate clustering code.

(This way requires you to create the folder where the emb files are stored, which we have created in the Baseline.zip.)

For the "clustering" subfolder, you can:

```
python clustering.py
```

