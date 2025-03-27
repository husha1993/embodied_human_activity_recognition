# Repo Structure
```
${PROJECT_PATH}
├── README.md
|
├── docs
│   ├── SETUP.md                                <- You are here
│   ├── SIMULATION.md                           
│   ├── Poster.pdf                              
|
├── scripts                                     <- Folder that contains train/test scripts
│   ├── run_main_expi.py                        <- Train script
│   ├── run_render.py                           <- Test and visualization script
|
├── configs                                     <- Folder that contains hyperparameters configurations for different experiments 
│   ├── expi
│   ├── aist
|
├── environments
|   ├── pybullet
|   	├── human_activity_sim                  <- Folder that contains the simulation environment
|   	    ├── human_activity_sim.py           <- Simulation 
|           ├── data_process                    <- Folder that contains data processing scripts
|               ├── process_expi.py
|               ├── process_aistpp.py
|           ├── utils(components)               <- Folder that contains components of simulation
|               ├── robot.py
|               ├── action.py
| 
|           ├── utils                           <- Folder that contains visualizations for simulation
|               ├── robot_pose_visualizer.py
|               ├── vis_utils.py
|  
├── algs                                        <- Folder that contains training algorithms
|   ├── base_alg.py
|   ├── on_policy_alg.py
|   ├── PPO_Human_Activity                      <- Folder that contains two-phase agent training
|   	├── ppo_human_activity.py              
|  
├── components
|   ├── agents                                  <- Implementations of agent architecture mentioned in Sec.4.1 of our paper
|   ├── buffers                                 <- Folder that contains PPO trajectories
|   ├── datasets                                <- Folder that contains IL demonstration dataset
|   ├── models                                     
|   	├── policies                            <- torch nets of different policies
|   	├── activity_recognition                <- implementations of activity recognition models
|           ├── CTR_GCN                         <- implementations of CTR-GCN
|   ├── vec_env                                 
|  
├── utils
├── common
```