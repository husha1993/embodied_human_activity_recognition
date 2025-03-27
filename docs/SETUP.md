# Python Environment Setup
1. Clone this repo and setup conda environment
    ```
    # clone this repo and set PROJECT_PATH
    git clone https://github.com/husha1993/embodied_human_activity_understanding
    cd embodied_human_activity_understanding
    export PROJECT_PATH="PATH/TO/PROJECT/DIRECTORY/embodied_human_activity_understanding" # root of project files
    
    # setup conda environment
    conda create -n myenv python=3.6.12
    conda env create --file environment.yaml --name myenv
    conda activate myenv
    ```

2.  Set PYTHONPATH
    ```
    # set PYTHONPATH
    export PYTHONPATH="$PROJECT_PATH:$PYTHONPATH"
    export PYTHONPATH="$PROJECT_PATH/scripts:$PYTHONPATH"   
    ```

3. Set other environment variable
    ```
    # set code related environment variable
    export IS_CC=false # set true for compute canada
    export DATA_PATH="PATH/TO/DATA/DIRECTORY" # root of data
    ```

