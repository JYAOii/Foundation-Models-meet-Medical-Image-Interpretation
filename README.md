# Foundation-Models-meet-Medical-Image-Interpretation
Foundation Models meet Medical Image Interpretation

## 📌 List
- [ ] 📄 Paper submitted (coming soon)
- [ ] 🔓 Code released
- [ ] 🚀 Data
- [ ] 📚 Citation

## 🔓 Code
Our code will be publicly available on: [![Code](https://img.shields.io/badge/💻-Code-blue)](https://github.com/IPIU-XDU/MedicalFM) https://github.com/IPIU-XDU/MedicalFM
## I. Models Available

## II. Getting Started
To get started, follow these steps: 
   ```bash
   conda activate p310
   cd /home/lry/MedicalFM
   export PYTHONPATH=$PYTHONPATH:./
   ```
1. Clone the Repository
   ```bash
   git clone https://github.com/IPIU-XDU/MedicalFM.git
   ```
2. Create and Activate a Virtual Environment
    ```bash
    conda create -n IPIUMed python=3.10
    conda activate IPIUMed
   ```
3. Install Pytorch: Follow the instructions [here](https://pytorch.org/get-started/locally/):
   ```bash 
    pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu120
   ```
5. Install the Repository 
   ```bash 
    cd IPIUMed
    pip install -e .
   ```

## III. Data Preparation
We follow the [nnU-Net V2](https://github.com/MIC-DKFZ/nnUNet?tab=readme-ov-file) guideline for data preparation, detailed below and accessible [here](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/dataset_format.md).

## IV.Model Training
### 1. To train the expert models
(1) **STU-Net** :snake:
- Training from scratch:
There are four types of STU-Net trainers:`STUNetTrainer_small`, `STUNetTrainer_base`, `STUNetTrainer_large`, `STUNetTrainer_huge`;
```bash
training_dataset: Abdomen/BTCV1
infer_dataset: Abdomen/BTCV1
trainer_name: STUNetTrainer_small
```

- Training with pretraining weights:
There are four types of STU-Net trainers:`STUNetTrainer_small_ft`, `STUNetTrainer_base_ft`, `STUNetTrainer_large_ft`, `STUNetTrainer_huge_ft`; And you need to set the pre-training weight path.
```bash
training_dataset: Abdomen/BTCV1
infer_dataset: Abdomen/BTCV1
trainer_name: STUNetTrainer_small_ft
pretrained_weights: MODEL_WEIGHT_PATH
```
Where `MODEL_WEIGHT_PATH` is the absolute path for the weights of pre-trained models.
These models are trained on TotalSegmentator dataset by 4000 epochs with mirror data augmentation.

| Model Name | Crop Size | #Params | FLOPs | Download Link |
|:------:|:-------:|:-----:|:---------:| :-------|
| STU-Net-S | 128x128x128 | 14.6M | 0.13T | [Baidu Netdisk](https://pan.baidu.com/s/1ZBfOhaTvjvhcgXKGNe_gWg?pwd=soz7) \| [Google Drive](https://drive.google.com/file/d/1HReH6dDrEuXgHPrsw7OrHSjvEUF3f4mv/view?usp=sharing)|
| STU-Net-B | 128x128x128 | 58.26M | 0.51T | [Baidu Netdisk](https://pan.baidu.com/s/1a17XmOGiGSgbEvK-acSOSg?pwd=91w3) \| [Google Drive](https://drive.google.com/file/d/1BHCp1Ort-OaVFwaZmvsG4qHiKiPeNb4h/view?usp=share_link)|
| STU-Net-L | 128x128x128 | 440.30M | 3.81T | [Baidu Netdisk](https://pan.baidu.com/s/1WOLoTrzCLYyJXZnITGK6jg?pwd=91pt) \| [Google Drive](https://drive.google.com/file/d/1KA1eXWWf_xAoJg5KHYrxTmfiz7wxGhHS/view?usp=share_link)|
| STU-Net-H | 128x128x128 | 1457.33M | 12.60T | [Baidu Netdisk](https://pan.baidu.com/s/1CinTvceZuvdEEWGcaJEuEA?pwd=bk9n) \| [Google Drive](https://drive.google.com/file/d/1Qrq7oGPJ7ileFHWOAxwpeWdaB6hySptU/view?usp=share_link)|

### 2. To train the expert models

### 3. To train the universal models

### 4. To train the foundation models

## V.Inference and Ulitls

## 🚀 Data

## 📚 Citation
If you utilize the baselines in this repository for your research, please consider citing the relevant papers for 
[nnU-Net](https://www.nature.com/articles/s41592-020-01008-z);
[STU-Net](https://arxiv.org/abs/2304.06716).

## Acknowledgements
We would like to acknowledge the contributions of [nnU-Net](https://github.com/MIC-DKFZ/nnUNet) and the authors of the baseline models: [STU-Net](https://github.com/uni-medical/STU-Net). This repository builds upon their foundational code and work.
