# Promtify  
**Text-to-Image Generation for E-Commerce Fashion Products**

Promtify is a deep learning project designed to generate realistic fashion product images (apparel and footwear) from textual descriptions. The goal is to streamline the process of cataloging e-commerce products by reducing the dependency on traditional photography—saving time, labor, and cost.

## Project Motivation
E-commerce platforms heavily rely on visually appealing product images. However, capturing and uploading thousands of product images is time-consuming and expensive. Promtify automates this process by generating high-quality fashion product images directly from descriptive text, empowering scalable and efficient digital retail.

## Dataset
**Source:** [Kaggle – Fashion Images Dataset](https://www.kaggle.com/datasets/vikashrajluhaniwal/fashion-images)

**Size:** 2,906 entries with 11 attributes including:
- Product Title  
- Category & Subcategory  
- Colour  
- Gender  
- Image URLs (for training & evaluation)

## Preprocessing

**Text:**
- Lowercasing and removing special characters/URLs  
- Feature engineering: combining attributes like color, gender, and usage  
- Tokenization and padding for sequence modeling

**Images:**
- Resized to 64×64 pixels  
- Normalized pixel values between 0 and 1

## Models Implemented

**Simple GAN**
- Text encoding with LSTM  
- Low-resolution output  
- FID Score: 12.01

**Style GAN (Custom)**
- Style modulation and text conditioning  
- FID Score: 8.76

**Attention GAN**
- Incorporates attention over text embeddings  
- FID Score: 5.98 (Best among GAN-based models)

**Stack GAN**
- Two-stage generation (64×64 → 128×128 or 256×256)  
- Issues with output quality despite architectural enhancements

**Stable Diffusion (Fine-Tuned)**
- Denoising-based generative process  
- Uses CLIP, UNet, and VAE  
- Best overall performance in realism and semantic alignment

## Evaluation Metric
**Fréchet Inception Distance (FID)**  
Lower scores indicate higher image quality and better alignment with textual input.

## Key Findings
- Attention GAN excelled among GAN models due to better text-image alignment  
- Stable Diffusion produced the most realistic and semantically accurate images  
- GAN-based models struggled with resolution and complexity despite architectural tuning

**Asma Fatima** 
