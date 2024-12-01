### **Project: Latent-Feature-Learning-with-Variational-Autoencoders**

In this project we will use the Fashion MNIST computer vision digit dataset and experiment with auto-encoders such as Variational Auto-encoder(VAE) and simple autoencoder. 

![image](https://github.com/user-attachments/assets/ace66f52-b82d-40dc-885f-b6a45f8f1880)

Figure3:

A: A sample Variational Auto-encoder. The VAE contains  one encoder and one decoder part. Encoder starts from x,h and ends in z=(σ + μ). [(σ + μ) learns latent representation or key features of the images]. Decoder starts from z=(σ + μ) to h2 and ends in x2. Decoder utilizes learned important represntation from z=(σ + μ) and tries to regenerate the image in x2.

B: A sample normal auto-encoder. A normal autoenoder contains only a fully connected layer z instead of a pair of layers (σ + μ) to learn the hidden representation. 

![image](https://github.com/user-attachments/assets/e6482ff1-bea6-4154-b30c-dfaf4585a86b)

![image](https://github.com/user-attachments/assets/138b595f-78c2-4af6-a2dd-e0b9c40c85e3)


This project involves experimenting with autoencoder architectures, including Variational Autoencoders (VAEs) and standard autoencoders, to analyze latent feature learning and image reconstruction. The tasks are structured as follows:  

Task 1. **Expanding the VAE Architecture:**  
   The baseline VAE model, which has a three-layer encoder and decoder, is extended into a five-layer architecture. The encoder is restructured to `(784, 400, 200, 100, 20)` while the decoder is adjusted to `(20, 100, 200, 400, 784)`. Model training is monitored to prevent overfitting, and the results are evaluated based on:  
   - **Optimal Loss:** The lowest achievable loss during training.  
   - **Visual Reconstruction:** Quality assessment of generated and reconstructed images using `plot_generation()` and `plot_reconstruction()` functions.  
   This task aims to compare the performance of the modified and original architectures, identify which performs better, and explain the differences in performance.

Task 2. **Evaluating Different VAE Configurations:**  
   Six configurations of the 5-layer VAE architecture are explored by modifying the hidden layer dimensions (`h_dim`) and latent dimensions (`z_dim`):  
   - Configurations: `(400,40)`, `(200,50)`, `(400,70)`, `(300,30)`, `(250,80)`, and `(300,5)`.  
   For each configuration, the model's performance is analyzed using optimal loss values and visual reconstruction outputs. This evaluation helps identify the most effective configuration and provides insights into why certain setups perform better than others.

Task 3. **Converting to a Standard Autoencoder:**  
   The best-performing VAE configuration from Task 1 is converted into a standard autoencoder by simplifying the latent space to a single fully connected layer (`z_dim`). The loss function is adjusted to exclude KL divergence. The standard autoencoder is then compared to the VAE using the same metrics of optimal loss and visual reconstruction. This comparison highlights the strengths and weaknesses of both architectures in capturing and reconstructing latent features.  

