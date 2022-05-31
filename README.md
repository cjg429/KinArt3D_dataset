# KinArt3D_dataset

![Dataset Overview](https://github.com/cjg429/KinArt3D_dataset/blob/main/images/figure1.png)

**Figure 1. The KinArt3D dataset example visualization.**

## About the Dataset

![Chain Overview](https://github.com/cjg429/KinArt3D_dataset/blob/main/images/figure2.png)

**Figure 2. The kinematic chain of an arm object visualization.**

The KinArt3D dataset provides instance-level link segmentation annotation for 91,075 shapes of 92 unique models from eight articulated object categories.
We first manually created a kinematic model for each object and prepared a mesh model of each link. Figure 2 illustrates five links of an example arm object and its tree structure. The edge of the tree means that there is a joint between the two connected links and stores three pieces of information: joint type, axis, and range. In the KinArt3D dataset, we consider 1D revolute joints and 2D universal joints. By uniformly sampling joint angles from its ranges, calculating the global 3D transformation of each link, and taking the calculated 3D transformation to each link, we can create a large number of different shapes from a single object. The remaining task is to check collisions between different links, and if there is no collision, merge all links and sample points from the merged mesh. In conclusion, by elaborately decomposing the object into a few links and generating a tree structure based on its kinematic model, we can get a large set of points with precisely labeled links without human segmentation. By using the farthest sampling method, we sample 2,048 points from the merged meshes and normalize them so that their coordinates are between $-1$ and $1$. In addition, we also voxelize the merged meshes with $64^3$ resolutions for the unsupervised baseline method.

## models & models_json
