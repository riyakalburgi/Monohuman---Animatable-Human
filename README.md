# Monohuman - Animatable Human

**Contributors:** Sandra Wiktor, Farnoosh Koleini, Riya Kalburgi, Micheal Rawlings

MonoHuman is a framework that generates animated virtual avatars using images from a monocular (single-camera) view. These avatars can be used in a variety of applications, such as virtual reality and digital implementations. It attempts to solve shortcomings of previous works that experienced issues such as pose-dependence and a limited ability to generalize to unseen poses. After consulting the available literature, MonoHuman’s development was guided by three central observations: the deformation weight field must be pose independent and within canonical space, the deformation field must be consistent in implementing both forward and backward deformation, and referencing input observation input directly improves the performance of the model.

Link to original project Github: https://github.com/Yzmblog/MonoHuman

Link to the **Project Report**: https://docs.google.com/document/d/1wiLaC8pTPlmFQ8GfjZOfW_tkYqxFPIA9P5Xjvq1MFXU/edit?usp=sharing

## Easy Steps To Execute

For ease of execution & environment requirements, we suggest to run the code in **Google Colab**

Steps:
1. Run the **Monohuman-Streamlit (1).ipynb** file in Google Colab (In the files in colab, upload all the files present in the Outputs folder before execution) : This files locally hosts the webpage for our project
2. The comment !curl ipv4.icanhazip.com gives the end point IP address for the localtunnel. When clicking on the localtunnel url, the end point IP address is asked. Enter the curl command generated IP address there and click submit to view the webpage.

#### If you want to execute all the files that generated the Output, follow the steps below (not required for viewing streamlit):
1. Get all the dataset in place: Download the Monohuman-main (please note we need to add 4 more folders/files here as they were too big to fit in github, the link to which are provided below), HumanML3D-main, motion-diffusion-model-main and store it in google drive

      a. CoreView _386 (https://drive.google.com/drive/folders/1DVGewbGwSMKARoB-Lfb6plpe5eie9CSS?usp=drive_link)
   
      b. dataset (https://drive.google.com/drive/folders/10Ekxqf0JtumEnd8CdzfVlfaRqmqzkPSV?usp=drive_link)
   
      c. experiments (https://drive.google.com/drive/folders/166cifEjZqKMd_ZEOEhi4ZqccrrkmCd0f?usp=drive_link)
   
      d. Miniconda3-py37_4.9.2-Linux-x86_64 (https://drive.google.com/file/d/17RQTcwnXfFemVs1FvAuxXXgFsYO5olV1/view?usp=drive_link)
   
Note: You can also access the whole Monohuman-main folder from here (https://drive.google.com/drive/folders/1F_d-2agltwxD-uBRIHVGk7Ua1aLtOmaD?usp=drive_link)

2. Run the **Monohuman-Avatar.ipynb** file in Google Colab: This file generates the avatar from the single monocular video
   <img width="946" alt="image" src="https://github.com/riyakalburgi/Monohuman---Animatable-Human/assets/56675842/c713d1f4-5d70-4836-9dc7-f09827a3ac71">
   Might have to update the path here, depending on where the Monohuman-main folder is placed within your drive.
   
Note: This code includes the whole pipeline for pre-processing, training, and rendering. To complete the entire pipeline, uncomment the specified blocks in the Monohuman-Avatar.ipynb code. This will take several hours.

3. Run the **Monohuman-Animation.ipynb** file in Google Colab: This files generates the animation for the avatar and based on the text input animation provided.

# NOTE: 
Make the necessary path updates, if needed.
Running only the Monohuman-Streamlit file should show you all the results that the codes generate. 
