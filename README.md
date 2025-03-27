# Embodied Human Activity Recognition
**[`Paper`](https://openaccess.thecvf.com/content/WACV2024/papers/Hu_Embodied_Human_Activity_Recognition_WACV_2024_paper.pdf) | [`Poster`](/docs/Poster-Embodied%20Human%20Activity%20Recognition-WACV%202024.pdf)**

This is an official implementation for\
**Embodied Human Activity Recognition**
<br>
<a href="https://husha1993.github.io/">Sha Hu</a>,
<a href="https://yugongg.github.io/">Yu Gong</a>,
<a href="https://www.cs.sfu.ca/~mori/">Greg Mori</a>, WACV 2024
<br>

## Preparation
0. Refer to [REPO.md](docs/REPO.md) for our repo structure overview.
1. Refer to [SETUP.md](docs/SETUP.md) for Python environment setup details.
2. Refer to [SIMULATION.md](docs/SIMULATION.md) for information on our simulation, including episode data preparation and the implementation framework.

## Run Experiments
Below are the instructions for training and testing agents for the Embodied Human Activity Recognition task.\
We track experiments with [Weights & Biases](https://wandb.ai/).
#### ExPI
1. Activity recognition network training.
    ```
    python run_main_expi.py --cfg multiFixed_init_no_act_pretrainVision 
    ```
2. Two-phase policy training.
    ```
    # Below are the commands to run agent training as mentioned in Section 4.2 in our paper,
   
    # 1. collect a demonstration dataset from ORACLE
    python run_main_expi.py --cfg random_init_oracle1_act_w_pretrain_vision --cd --cd_num 10000 
    # 2. imitation learning phase
    python run_main_expi.py --cfg il_random_init_mlp_act_mlp_visual_model_encoder_w_pretrain_vision --il 
    # 3. reinforcement learning phase
    python run_main_expi.py --cfg random_init_mlp_act_mlp_visual_model_encoder_w_pretrain_vision 
    ```
   
3. Test agents.
   
   To obtain the numbers reported in Table.1 and Table.2 in our paper, please first download the  
   model checkpoints and then run the following commands.

   ##### Model Checkpoints Links:

   |   |ExPI|AIST++|
   |---|---|---|
   |Activity recognition network | [Here](https://drive.google.com/file/d/1d_kutSeckVyEZCLIJpRAWpsxcPZ0ErD8/view?usp=drive_link) | [Here](https://drive.google.com/file/d/1BVvnt4wW6JIEc45y4Izii8PaXfyTmAON/view?usp=drive_link)|
   |PPO-only policy |  [Here](https://drive.google.com/drive/folders/1i5te-3mWs6l3vLaRCapGMnrdu-mDzIGD?usp=drive_link) | [Here](https://drive.google.com/drive/folders/1gdg46dSiuTIX7J9DVFcpNkUKl0Lp2ABq?usp=drive_link)|
   |IL-only policy| [Here](https://drive.google.com/drive/folders/1a6ocCFiFSBhWvvLPXdEKa6IZlog2xSxI?usp=drive_link) | [Here](https://drive.google.com/drive/folders/15sqbnSYpcTEycgEtfGIhmS1iE-zJtKKA?usp=drive_link)|
   |Ours| [Here](https://drive.google.com/drive/folders/1ppSG4sySwZV7zO80YHL9flzigCgJKH6R?usp=drive_link) | [Here](https://drive.google.com/drive/folders/1hj3xzVSchRqNpXyv285NF6nj7-bPjLDQ?usp=drive_link) |

   ##### Below are the commands to obtain the numbers in Table.1 and Table.2 in our paper.
   ```   
   # test a learned agent with the path to a saved model checkpoint
   python run_render_visualizations_expi.py --method mlp
   
   # test an ORACLE agent
   python run_render_visualizations_expi.py --method o 
   
   # test a PASSIVE agent
   python run_render_visualizations_expi.py --method f 
   
   # test a RANDOM/TOWARDS/H-ROTATE/V-ROTATE agent 
   python run_render_visualizations_expi.py --method rd   
   python run_render_visualizations_expi.py --method t 
   python run_render_visualizations_expi.py --method hro
   python run_render_visualizations_expi.py --method vro
   ```
   
4. visualize episodes with videos.
   ```
   python run_render_visualizations_expi.py --method mlp --vis   
   ```

#### AIST++
To run experiments on AIST++, replace '_expi' in the above commands with '_aist'.


## Citation

If you find this code useful for your research, please cite our paper:

```bibtex
@InProceedings{Hu_2024_WACV,
    author    = {Hu, Sha and Gong, Yu and Mori, Greg},
    title     = {Embodied Human Activity Recognition},
    booktitle = {Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (WACV)},
    month     = {January},
    year      = {2024},
    pages     = {6447-6457}
}
```
