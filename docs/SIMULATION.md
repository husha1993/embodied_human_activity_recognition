# Our Simulation 
## Implementation Framework
1. Environment

2. Human activity scenarios

3. Robot
    * Observation $o_{t}\in \mathcal{O}$
    * Action $a_{t}$
    * Spawning position $p_{0}$ 

## Episodes Dataset Preparation
We use real-world motion capture datasaets to simulate an embodied agent which can move and perceive realistic human activities in 3D space.\
Belows are the instructions for downloading and processing the two MoCAP datasets to construct our task episodes.

1. Download data from [`ExPI Page`](https://team.inria.fr/robotlearn/research/expi-dataset/) and from [`AIST++ Page`](https://google.github.io/aistplusplus_dataset/download.html)
2. Process data as mentioned in Section 5.1 in our paper.
      ```
      # preprocess ExPI: given 
      python ./environments/pybullet/human_activity_sim/data_process/process_expi.py
      
      # preprocess AIST++: 
      python ./environments/pybullet/human_activity_sim/data_process/process_aist.py
      ```
            
2. Episodes statistics summarizations could be found in Section 5.1 of the [Paper](https://openaccess.thecvf.com/content/WACV2024/papers/Hu_Embodied_Human_Activity_Recognition_WACV_2024_paper.pdf) and in [Supplementary](https://openaccess.thecvf.com/content/WACV2024/supplemental/Hu_Embodied_Human_Activity_WACV_2024_supplemental.pdf).
 
   