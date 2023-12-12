# Monohuman - Animatable Human
Creating realistic and coherent animations for virtual avatars with free-view control is essential in applications such as virtual reality and digital entertainment. Previous research has explored the use of neural radiance fields (NeRF) to reconstruct human bodies from monocular videos. Some recent approaches integrate deformation networks into NeRF to capture the dynamics of the human neural field for lifelike motions. However, existing methods either rely on pose-dependent representations or struggle with motion coherency, hindering their ability to realistically generalize to new pose sequences. In this paper, we introduce a novel framework called **MonoHuman** that efficiently generates avatars with view-consistency and high fidelity across arbitrary poses. Our approach involves modeling the deformation field with bi-directional constraints and leveraging keyframe information to enhance feature correlations for cohesive results. We propose a Shared Bidirectional Deformation module, which establishes a pose-independent and generalizable deformation field by separating backward and forward deformation correspondences into shared skeletal motion weight and distinct non-rigid motions. Additionally, we introduce a Forward Correspondence Search module that utilizes keyframe information to guide the rendering network. As a result, our rendered avatars exhibit multi-view consistency and high fidelity, even in challenging novel pose scenarios. Extensive experiments demonstrate the superior performance of MonoHuman compared to state-of-the-art methods.

## Installation

We recommend to use Google Colab

Create and activate a virtual environment.

    conda env create -f environment.yaml
    conda activate Monohuman

### `Download SMPL model`

Download the gender neutral SMPL model from [here](https://smplify.is.tue.mpg.de/), and unpack **mpips_smplify_public_v2.zip**.

Copy the smpl model.

    cp /path/to/smpl/smplify_public/code/models/basicModel_neutral_lbs_10_207_0_v1.0.0.pkl third_parties/smpl/models

Follow [this page](https://github.com/vchoutas/smplx/tree/master/tools) to remove Chumpy objects from the SMPL model.

## Run on ZJU-Mocap Dataset

### `Prepare a dataset`

1. Download ZJU-Mocap dataset from [here](https://github.com/zju3dv/neuralbody/blob/master/INSTALL.md#zju-mocap-dataset). 

2. Modify the yaml file of subject at `tools/prepare_zju_mocap/xxx.yaml` as below (Replace the 'xxx' to the subject ID):
```
    dataset:
        zju_mocap_path: /path/to/zju_mocap
        subject: 'xxx'
        sex: 'neutral'

...
```
3. Run the data preprocessing script.
```
    cd tools/prepare_zju_mocap
    python prepare_dataset.py --cfg xxx.yaml
    cd ../../
```

4. Modify the 'dataset_path' in core/data/dataset_args.py to your /path/to/dataset

### `Training`
Please replace the 'xxx' to the subject ID

    python train.py --cfg configs/monohuman/zju_mocap/xxx/xxx.yaml resume False


### `Rendering and Evalutaion`

Render the motion sequence. (e.g., subject 377)

    python run.py \
        --type movement \
        --cfg configs/monohuman/zju_mocap/377/377.yaml 

![video](assets/377_movement.gif)

Render free-viewpoint images on a particular frame (e.g., subject 386 and frame 100).

    python run.py \
        --type freeview \
        --cfg configs/monohuman/zju_mocap/386/386.yaml \
        freeview.frame_idx 100
![video](assets/386_free.gif)

Render the text driven motion sequence.
Generate poses sequence from [MDM](https://github.com/GuyTevet/motion-diffusion-model), and put the sequence to `path/to/pose_sequence/sequence.npy` (e.g., subject 394 and backflip)

    python run.py \
        --type text \
        --cfg configs/monohuman/zju_mocap/394/394.yaml \
        text.pose_path path/to/pose_sequence/backflip.npy
![video](assets/backflip.gif)
