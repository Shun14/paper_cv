# Shape Robust Text Detection with Progressive Scale Expansion Network

##### KeyPoints

- Using **kernel** to detect the text region for different shapes like curved or quadrangle
  - Kernel means minimum area of the text region which is benefit for separating the adjacent areas of the text
  - From minimum kernel , the paper use a progressive scale expansion algorithm to combine the pixels closed to the minimum kernel
- Backbone
  - resnet 101 and FPN
- Architecture
  - ![](./Segmentation_1_nets_architecture.PNG)
  - How to concatenate and up-sample the feature maps?
    - ![](./Segmentation_1_nets_architecture_details_1.PNG)
  - After the concatenating , *F* is fed into Conv(3x3)-BN-ReLU layers and is reduced into 256 channels. Next, it passes through multiple Conv(1, 1)-Up-Sigmoid layers and produces **n** segmentation results S1, S2, ..., Sn.**So the segmentation results are generated by every conv(1,1) layer respectively**
- The progressive scale expansion algorithm

