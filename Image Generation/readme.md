
# **Image Generation using Stable Diffusion**  

## **Overview**  
This project uses the **Stable Diffusion model** from **Hugging Face** to generate images based on text prompts. Stable Diffusion is a **deep learning model** that generates high-quality images from natural language descriptions.  

## **Key Features**  
- **Text-to-Image Generation**: Create images from text prompts.  
- **Uses Pre-trained Stable Diffusion Model**: Efficient and high-quality results.  
- **Hugging Face Integration**: Easy model loading and inference.  

## **Implementation Steps**  

### **1. Load the Stable Diffusion Model**  
- Import the **Stable Diffusion pipeline** from Hugging Face.  
- Load the **pre-trained model** from Hugging Face's model hub.  

### **2. Provide a Text Prompt**  
- Define a **prompt** describing the desired image.  
- The model will interpret the text and generate a corresponding image.  

### **3. Generate the Image**  
- Run the model with the given prompt.  
- The model outputs an image based on the text description.  

### **4. Display & Save the Image**  
- The generated image is displayed using **PIL (Python Imaging Library)**.  
- The image can be saved for further use.  

## **Libraries Used**  
- **diffusers** – For loading and running the Stable Diffusion model.  
- **transformers** – Hugging Face library for pre-trained models.  
- **torch** – Deep learning framework for model execution.  
- **PIL (Pillow)** – For handling image display and saving.  

## **Example Code**  
```python
from diffusers import StableDiffusionPipeline
import torch

# Load the model
model_id = "CompVis/stable-diffusion-v1-4"
pipe = StableDiffusionPipeline.from_pretrained(model_id, torch_dtype=torch.float16)
pipe.to("cuda")  # Use GPU for faster inference

# Define a prompt
prompt = "A futuristic cityscape at sunset, cyberpunk style"

# Generate an image
image = pipe(prompt).images[0]

# Display and save the image
image.show()
image.save("generated_image.png")
```  

## **Expected Output**  
- An **AI-generated image** based on the given text description.  

This project demonstrates how **Stable Diffusion** can be used to generate high-quality images from text descriptions using **Hugging Face**. 🚀  
