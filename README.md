# Monohuman - Animatable Human
Creating realistic and coherent animations for virtual avatars with free-view control is essential in applications such as virtual reality and digital entertainment. Previous research has explored the use of neural radiance fields (NeRF) to reconstruct human bodies from monocular videos. Some recent approaches integrate deformation networks into NeRF to capture the dynamics of the human neural field for lifelike motions. However, existing methods either rely on pose-dependent representations or struggle with motion coherency, hindering their ability to realistically generalize to new pose sequences. In this paper, we introduce a novel framework called **MonoHuman** that efficiently generates avatars with view-consistency and high fidelity across arbitrary poses. Our approach involves modeling the deformation field with bi-directional constraints and leveraging keyframe information to enhance feature correlations for cohesive results. We propose a Shared Bidirectional Deformation module, which establishes a pose-independent and generalizable deformation field by separating backward and forward deformation correspondences into shared skeletal motion weight and distinct non-rigid motions. Additionally, we introduce a Forward Correspondence Search module that utilizes keyframe information to guide the rendering network. As a result, our rendered avatars exhibit multi-view consistency and high fidelity, even in challenging novel pose scenarios. Extensive experiments demonstrate the superior performance of MonoHuman compared to state-of-the-art methods.

Link to original project Github: https://github.com/Yzmblog/MonoHuman

## Easy Steps To Execute
Steps:
1. Get all the dataset in place: Download the Monohuman-main (please note we need to add 4 more folders/files here, the link to which are provided below), HumanML3D-main, motion-diffusion-model-main and store it in google drive
      a. CoreView _386 (https://drive.google.com/drive/folders/1DVGewbGwSMKARoB-Lfb6plpe5eie9CSS?usp=drive_link)
      b. dataset (https://drive.google.com/drive/folders/10Ekxqf0JtumEnd8CdzfVlfaRqmqzkPSV?usp=drive_link)
      c. experiments (https://drive.google.com/drive/folders/166cifEjZqKMd_ZEOEhi4ZqccrrkmCd0f?usp=drive_link)
      d. Miniconda3-py37_4.9.2-Linux-x86_64 (https://drive.google.com/file/d/17RQTcwnXfFemVs1FvAuxXXgFsYO5olV1/view?usp=drive_link)
Note: You can also access the whole Monohuman-main folder from here (https://drive.google.com/drive/folders/1F_d-2agltwxD-uBRIHVGk7Ua1aLtOmaD?usp=drive_link)
2. Download and execute the Monohuman-Avatar.ipynb file : This file generates the avatar from the single monocular video
3. Download and execute the Monohuman-Animation.ipynb file : This files generates the animation for the avatar and based on the input animation provided
4. Download and execute the Monohuman-StreamLit.ipynb file : This files locally hosts the webpage for our project

NOTE: Make the necessary path updates, if needed.
