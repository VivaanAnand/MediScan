# MediScan
Mediscan is an AI powered breast cancer detection from histopathological images

## Why I Built This
When I was in the 8th Grade, my mom was diagnosed with Breast Cancer. For a year, my family didn't know whether she would survive or not. Thankfully she lived, but not without much adversity, particularly involving the doctors. Firstly, when my mom discovered the tumor and went to the doctor to get it checked, it took the doctors 2 weeks to determine the diagnosis because their computer system was not working so they couldn't receive their report. Not only that, but the doctors did not want to give the diagnosis to my parents. They had to tell the doctors that they weren't going to leave until they got the diagnosis. Furthermore, the diagnosis was wrong! They said it was stage 1 at first and told my Mom to take an ultrasound. Then in the ultrasound they learned it was stage 2. But when we got the surgery to remove the cancer, the doctors realized that it was stage 3 and couldn't do it with just the original surgery. Instead of relying on a broken system, artificial intelligence can be trained on datasets of medical images to discover hidden patterns and classify life-or-death data with high accuracy that humans clearly miss. After experiencing the terrible American Medical system, I felt that I could give AI histopathological images and it would diagnose Breast Cancer faster and with more accuracy than doctors.

## Model Architecture
1. The Model (using EfficientNet-B0)is given Histopathological images from the BreakHis dataset at magnifications 40x, 100x, 200x, 400x

2. Before the model is given these images, they are first resized to 224x224 pixels. Next, they colors will not be 0(black)-255(white), I will instead convert them to values between -1 and 1. Finally, I will also augment the images. There are only 7909 images in the BreakHis Dataset. I will take each image and create variations. For example, I could rotate an image 15 degrees counterclockwise.

3. The core model is EfficientNet-B0. I chose this one over alternatives like ResNet and VGG because EfficientNet-B0 achieves better accuracy while requiring significantly less computational power. The output is a classification plus the confidence score (how confident the model is).

4. Grad-Cam is what makes MediScan medically useful. This generates a heatmap overlaid on the original image which shows where the model is looking. This can helped doctors gather patterns about malignant and benign tumors that were previously unknown.

NOTE: This is V1 architecture, refer to the roadmap to see how it will change over the course of each version.

## Dataset
BreakHis: https://www.kaggle.com/datasets/ambarish/breakhis. The dataset is sorted into 2 main classes (Benign and Malignant), but 4 subclasses of each class. For Benign they are adenosis (A), fibroadenoma (F), phyllodes tumor (PT), and tubular adenona (TA). For Malignant they are carcinoma (DC), lobular carcinoma (LC), mucinous carcinoma (MC) and papillary carcinoma (PC). There are 4 magnification levels: 40x, 100x, 200x, and 400x. Its license is the CC by 4.0 international license.

## Roadmap
1. V1 (Finished By December 2026): EfficientNet-B0 on all 7909 BreakHis images. Only using the Benign and Malignant classes. Target: 90% accuracy. Grad-CAM heatmaps to show where the model is looking. Deploy on Huggingface so others can upload an image and get a prediction.

2. V2 (Finished By February 2027): Same Model Architecture but the 4 subclasses for both Benign (adenosis (A), fibroadenoma (F), phyllodes tumor (PT), and tubular adenona (TA)) and Malignant (carcinoma (DC), lobular carcinoma (LC), mucinous carcinoma (MC) and papillary carcinoma (PC))

3. V3 (Finished By April 2027): 3 Models combined: EfficientNet-B0, ResNet50, and ViT-B/16 fused together by a learning neural network that learns which model to trust more for each image. Adds CBIS-DDSM dataset for more training data. Target 93%+ accuracy. Deployed on Streamlit.

4. V4 (Finished by May/June 2027): Same as V3, but Grad-CAM++ is used, which highlights more precise areas of interest and shows multiple instad of just one. Streamlit interface is overhauled to be usable by pathologists.

5. V5 (Finished by November 2027): Instead of showing images to the 4 models blindly, I will instead tell it the magnification, to increase accuracy. Target Accuracy: 96%+.

6. V6 (Planned to be finished Summer 2028): Implement pre-training with SimCLR to understand the general structure of the histopathology images without any labels. This should theoretically improve accuracy.

7. V7 (Planned to be finished Summer 2028): Instead of a ViT Architecture which processes the full image at once, implement Swin transformer which processes the images in shifted Windows. I will test if Swin outperforms our current models and implement it accordingly. Also, give the AI the ability to identify the tumor boundary is.

## Setup
Exact commands:
git clone https://github.com/VivaanAnand/MediScan.git
cd MediScan
pip install -r requirements.txt
cp .env.example .env
#Fill in your .env values (W&B API key, paths)

## Current Status
Currently building the Github Repository before starting V1

## License
This project is licensed under the MIT License - see the LICENSE file for details

## Contacts
Github: github.com/VivaanAnand, Email Address: vivaan.anand.11@gmail.com
