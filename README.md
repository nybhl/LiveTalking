# Wav2Lip
## Install
Tested with cuda 12.6, nvcc version 12.6
```bash
conda create -n wav2lip python=3.10
conda activate wav2lip
```

Install torch 2.6.0 with nvcc 12.6
```bash
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
```

Test cuda is working
```bash
(wav2lip) root@DESKTOP-UJGQNR3:~# python -c "import torch; print(torch.__version__)"
2.6.0+cu126
(wav2lip) root@DESKTOP-UJGQNR3:~# python -c "import torch; print(torch.cuda.is_available())"
True
```

Install requirements
```
pip install -r wave2lip_requirements.txt
```

## 2. Quick Start
- Download Model 
GoogleDriver <https://drive.google.com/drive/folders/1FOC_MD6wdogyyX_7V1d4NDIO7P9NlSAJ?usp=sharing>  
Copy wav2lip384.pth to models/, and rename checkpoint to wav2lip.pth;  
Copy wav2lip384_avatar1.tar.gz under data/avatars
- Run  
python app.py --transport webrtc --model wav2lip --avatar_id wav2lip384_avatar1  
Use browser to open http://serverip:8010/webrtcapi.html
Click start.


# MuseTalk
## 1. Installation
Tested on Ubuntu 20.04, Python3.10, Pytorch 1.12 and CUDA 11.3

### 1.1 Install dependency
```bash
conda create -n nerfstream python=3.10
conda activate nerfstream

#Check your nvcc version. If it is not 11.3, you need to install it
wget https://developer.download.nvidia.com/compute/cuda/11.3.0/local_installers/cuda_11.3.0_465.19.01_linux.run
sh cuda_11.3.0_465.19.01_linux.run --installpath=/mnt/mount/cuda
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
export PATH=/usr/local/cuda/bin:$PATH
source ~/.bashrc

pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 torchaudio==0.12.1 --extra-index-url https://download.pytorch.org/whl/cu113
pip install -r requirements.txt


