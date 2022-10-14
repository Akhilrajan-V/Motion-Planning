# Motion-Planning

A motion Planning model based on GoogLeNet trained on the **Lyft's Planning and Prediction Dataset** capable of planning the motion of the ego vehicle.   

## Model 
The base model is a ***GoogLeNet*** model that is pretrained. It is customized with multiple Fully Connected convolution layers at the output to meet the requirements. The input layer is also customized to match the output size of the rasterizer. 

## Result

  ![img](./Assets/Planner_sim.gif)
  
 
## Setup

1. Download the Lyft's Prediction Dataset and the example codes from the Lyft's [website](https://level-5.global/data/prediction/)
2. Create a new virtual python environment using conda or python env.
**Note:** (Only Part 1 of training dataset was used to train the mote due to RAM limitations)
2. Download the Lyft Python SDK in the new environment. 
3. Reorganize the folders and files downloaded as mentioned below (Refer Directory Structure)
4. Paste the files in the /Scripts sub directory of this repository inside the examples directory.
5. Change parameters in the config file as fit for your system specifications. 
6. Change the PATH in the planning python/jupyter-notebook scripts
7. For inference load the trained model into the ```open_loop_test.ipynb``` and ```closed_loop_test.ipynb``` jupyter-notebooks.

```python
os.environ["L5KIT_DATA_FOLDER"] = "/home/akhil/lyft_predict/l5kit-1.5.0"
...
cfg = load_config_data("./config.yaml")
```
## Directory Structure

```bash
Motion_Prediction(any_name)
├── aerial_map
│   ├── aerial_map.png
│   ├── feedback.txt
│   ├── LICENSE
│   └── nearmap_images
├── l5kit-1.5.0
│   ├── dataset_metadata
│   ├── docs
│   ├── examples
│   ├── l5kit
│   ├── meta.json
│   ├── README.md
│   ├── scenes
│   ├── scripts
│   ├── semantic_map
│   └── trained_models
├── sample
│   ├── feedback.txt
│   ├── LICENSE
│   └── sample.zarr
└── semantic_map
    ├── feedback.txt
    ├── LICENSE
    ├── meta.json
    └── semantic_map.pb

```
  
## System Specifications

- 16 GB RAM 
- Nvidia RTX 3070 8 GB VRAM
- Ubuntu 20.04 LTS
- 200 GB SSD

***NOTE:***

These are the specifications of the system this model was trained on and is **not the minimum specification** 

## Requirements

- python 3.9
- L5kit-1.5.0
- torch
- torchvision
- torchaudio
- openCV
- protobuf 3.20
- jupyter
- CUDA (optional- only for GPU)

### TODO

- [X] Train on DeepCNN  
- [ ] Train on Vision Transformer

---

