# jdecmc


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
