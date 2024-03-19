# jdecmc

#### Our JDECMC method's overall architecture
![JDECMC pd](https://github.com/Melikamuliyih/jdecmc/assets/57220094/55104928-9689-4e90-a560-d0f756d9fcee)



# Abstract 
Jointly Detection and Embedding (JDE) based approaches estimate bounding boxes and
embedding features of objects with a single network in multi-object tracking. Due to
the crowded scenarios or non-rigid camera motion, the bounding box location in the
image can shift dramatically, which affects the performance of the trackers. In addition,
JDE-based approaches fuse the target appearance information and location information
by applying the same rule, which could fail to associate when the target is lost or occluded.
To address these issues, we propose a simple yet effective architecture based
on JDE, called JDECMC. Our approach incorporates the embedding and location distance
of the object, which combines embedding cosine distance and location distance
of objects, as well as Camera Motion Compensation (CMC) to predict the correct location
of the bounding box. This is especially useful in scenarios where dynamic camera
motion can cause the bounding box to shift significantly. By enhancing the accuracy of
the tracking system, JDECMC achieves a MOTA of 74.2%, 72.0%, and 90.5% on the
MOT17, MOT20, and DanceTrack benchmark datasets, respectively, while also scoring
an IDF1 of 72.5%, 72.4%, and 79.8% on those benchmarks. The experimental results
demonstrate our effectiveness and advantages over the other one-shot trackers.

## News
(2024.03.26) Our paper is accepted by Displays!


## Highlights
* We effectively address the tracking and speed issues inherent in one-shot trackers,
particularly in crowded and dynamic scenes.
* We use camera motion compensation to address crowded and dynamic scenes by
employing image registration to reveal background objects.
* We introduce embedding and location distance matrix for efficient data association to
improve tracking speed.
* We propose a simple and efficient online one-shot tracker called JDECMC for multiobject
tracking.

## Installation
* Clone this repo, and we'll call the directory that you cloned as ${JDECMC}
* Install dependencies. We use python 3.8 and pytorch >= 1.7.0

```
conda create -n JDECMC
conda activate JDECMC
conda install pytorch==1.7.0 torchvision==0.8.0 cudatoolkit=10.2 -c pytorch
cd ${JDECMC}
pip install cython
pip install -r requirements.txt
```
* We use DCNv2_pytorch_1.7 in our backbone network (pytorch_1.7 branch). Previous versions can be found in DCNv2
## Data preparation
## Training
## Tracking
## Demo
## Acknowledgement
## Citation
