# JDECMC

#### Our JDECMC method's overall architecture
![JDECMC pd](https://github.com/Melikamuliyih/jdecmc/assets/57220094/55104928-9689-4e90-a560-d0f756d9fcee)

> [**M.L. Sinishaw and S. Liu, JDECMC: Improving JDE based multi-object
tracking with Camera Motion Compensation**](https://www.sciencedirect.com/science/article/pii/S0141938224000465), 
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

## Highlights
* We effectively address the tracking and speed issues inherent in one-shot trackers,
particularly in crowded and dynamic scenes.
* We use camera motion compensation to address crowded and dynamic scenes by
employing image registration to reveal background objects.
* We introduce embedding and location distance matrix for efficient data association to
improve tracking speed.
* We propose a simple and efficient online one-shot tracker called JDECMC for multiobject
tracking.

## Tracking performance
### Results on MOT Datasets
| Dataset    |  MOTA | IDF1  | MT | ML | FPS |
|--------------|-----------|-------|----------|----------|--------|
|MOT17       | 74.2% | 72.5% | 43.4% | 12.1% | 24.1 |
|MOT20       | 72.0% | 72.4% |72.0% | 7.5% | 13.3 |

### Results on DanceTrack Dataset
| Dataset    |  MOTA | IDF1  | DetA |AssA |
|--------------|-----------|-------|----------|----------|
|DanceTrack  | 90.5% | 79.8% |84.1% | 64.9 |

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
After downloading, you could prepare the data in the following structure:
```
MOT17
   |——————images
           └——————train
           └——————val
           └——————test
   
MOT20
   |——————images
           └——————train
           └——————test
           └——————test
DanceTrack
   |——————images
           └——————train
           └——————val
           └——————test
   
```
## Training

```
We follow the training procedure of FairMOT, if you want to train the model on your custom dataset follow the FairMOT.
```

## Tracking
#### Tracking on MOT17
```
cd src
python track.py mot --load_model ../models/your_pretrained_model --conf_thres 0.4 --val_mot17 True
```
#### Tracking on MOT20
```
cd src
python track.py mot --load_model ../models/your_pretrained_model --conf_thres 0.3 --val_mot20 True
```
#### Tracking on DanceTrack
```
cd src
python track.py mot --load_model ../models/your_pretrained_model --conf_thres 0.5 --val_dance True
```

## Demo
```
cd src
python demo.py mot --load_model ../models/your_pretrained_model --conf_thres 0.4
```

### Demo results
![mot17-06-245](https://github.com/Melikamuliyih/JDECMC/assets/57220094/a688908e-9a4c-4708-af05-06a23f1fa45b)
![mot17-06-240](https://github.com/Melikamuliyih/JDECMC/assets/57220094/2e4693a7-fc3a-429b-bd36-0513ccf77d24)
![mot17-06-235](https://github.com/Melikamuliyih/JDECMC/assets/57220094/9f35b654-ceb3-4adb-ad29-1fc2f088b010)


## Acknowledgement
A large part of the code is borrowed from Zhongdao/Towards-Realtime-MOT, ifzhang/FairMOT, xingyizhou/CenterNet, ByteTrack, and BoT-SORT. Thanks for their wonderful works.
## Citation
```
@article{SINISHAW2024102682,
title = {JDECMC: Improving JDE based multi-object tracking with Camera Motion Compensation},
author = {Melikamu Liyih Sinishaw and Shu Liu},
journal = {Displays},
volume = {83},
pages = {102682},
year = {2024},
issn = {0141-9382},
publisher={Elsevier}
}
```
