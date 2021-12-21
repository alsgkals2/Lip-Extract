# Lip-Extraction
### This Repo contains the codes for extraction the landmark and lip  

This is a PyTorch implementation by referreing [LipForensics paper](https://arxiv.org/abs/2012.07657). 
#### This is an Unofficially implemented codes with some Official code. I made this repo to use more conveniently.
#### If you want to see the Original code, You can cite [this link](https://github.com/ahaliassos/LipForensics)
#### You should try the preprocessing, which steps are firstly getting landmarks and then cropping mouth.
 
## Setup
### Install packages
```bash
pip install -r requirements.txt
```

Note: we used Python version 3.8 to test this code.
### Prepare data
1. Follow the links below to download the datasets (you will be asked to fill out some forms before downloading):
    * [FaceForensics++ (FF++) / FaceShifter (c23)](https://github.com/ondyari/FaceForensics) 
    * [DeeperForensics](https://github.com/EndlessSora/DeeperForensics-1.0)
    * [CelebDF-v2](https://github.com/yuezunli/celeb-deepfakeforensics)
    * [DFDC](https://ai.facebook.com/datasets/dfdc/) (the test set of the full version, not the Preview)
2. Extract the frames (e.g. using code in the [FaceForensics++ repo](https://github.com/ondyari/FaceForensics/blob/master/dataset/extract_compressed_videos.py).)
The filenames of the frames should be as follows: 0000.png, 0001.png, ....
3. Detect the faces and compute 68 face landmarks. From this step, see the 4.1 section.

### 4. Running 
#### 4.1 Landmark Extraction 
For extraction the landmark of faces, I referred [RetinaFace](https://github.com/biubug6/Pytorch_Retinaface) and [FAN](https://github.com/1adrianb/face-alignment) for good results. The results are .json files 

    ```bash
   You can use easy_start_lip_extract.ipynb
    ``` 
    
#### 4.2 Lip Extraction and Crop 
    ```bash
   python preprocessing/crop_mouths.py --dataset all
    ```
    This will write the mouth images into the corresponding `cropped_mouths` directory. 
    
