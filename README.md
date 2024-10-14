# MVD-NeRF
1.Proposed a novel framework for 3D reconstruction of NeRF tailored for blurry inputs.
2.Simulated defocus blur based on its generation principle.
3.Translated the camera center to simulate light source movement in different views.

## Quick Start
### 1.Install environment
```
git clone https://github.com/luckhui0505/MVD-NeRF.git
cd MP-NeRF
pip install -r requirements.txt
```

### 2. Download dataset
There are total of 31 scenes used in the paper. We mainly focus on defocus blur. You can download all the data in [here](https://hkustconnect-my.sharepoint.com/personal/lmaag_connect_ust_hk/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Flmaag%5Fconnect%5Fust%5Fhk%2FDocuments%2Fshare%2FCVPR2022%2Fdeblurnerf%5Fdataset&ga=1).
### 3. Setting parameters
Changing the data path and log path in the configs/demo_blurball.txt
### 4. Execute
python3 run_nerf.py --config configs/demo_blurball.txt

## Method Overview
![image](https://github.com/luckhui0505/MVD-NeRF/framework/framework.jpg) 
## Comparison of Experimental Results
![image](https://github.com/luckhui0505/MP-NeRF/blob/master/result.jpg) 
## Some Notes
### GPU Memory
We train our model on a RTX3090 GPU with 24GB GPU memory. If you have less memory, setting N_rand to a smaller value, or use multiple GPUs.
### Multiple GPUs
you can simply set <mark> num_gpu = <num_gpu> <mark> to use multiple gpus. It is implemented using <mark> torch.nn.DataParallel <mark>. We've optimized the code to reduce the data transfering in each iteration, but it may still suffer from low GPU usable if you use too much GPU.
## Acknowledge
This source code is derived from the famous pytorch reimplementation of NeRF, nerf-pytorch, Deblur-NeRF. We appreciate the effort of the contributor to that repository.
