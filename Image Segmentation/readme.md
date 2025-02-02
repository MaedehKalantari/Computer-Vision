# **Image Segmentation on Oxford-IIIT Pet Dataset**  

## **Overview**  
This project focuses on **image segmentation** using the **Oxford-IIIT Pet Dataset**. The dataset contains **37 pet categories**, with **200 images per class**, totaling **7,400 images**. Each image has an associated **annotation mask**, where the pixels are labeled as:  
1. **Background**  
2. **Foreground (Pet)**  
3. **Edges**  

The goal is to train a **U-Net-based model** that learns to **segment pets** from images by separating object pixels from the background.  

## **Dataset Structure**  
- **Images**: Contained in the main dataset folder.  
- **Annotations**:  
  - `trimaps/` → Background class  
  - `xmls/` → Edge and foreground class  
- **Metadata**: Contains label information.  

## **Approach**  
1. **Load and preprocess the dataset**  
   - Resize images to **200×200**  
   - Resize annotation masks to **24×24**  
2. **Build a U-Net model**  
   - Uses **convolutional layers** for feature extraction.  
   - **Latent space representation** to capture important features.  
   - **Deconvolution layers** to reconstruct segmented images.  
3. **Train the model**  
   - Define a **functional neural network** using **Keras**.  
   - Compile the model with an **optimizer** and **loss function**.  
   - Train on the dataset for segmentation.  

## **Model Architecture**  
- **Encoder**: Convolutional layers extract features.  
- **Bottleneck**: Latent space representation.  
- **Decoder**: Deconvolution layers reconstruct the segmentation mask.  

This project is a **generation task**, meaning the model learns to **create segmentation masks** for input images.  
