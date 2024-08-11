# Synthetic_Medical_Tabular_Data
Generate synthetic medical data from a patient population dataset.

## SCENARIO

Dr. AA is conducting a study to better understand a rare disease.  However, due to the rarity of the disease, he could not gather enough numbers that would power statistical analyses.

In an international conference, he met Dr. BB who was presenting case reports on the disease and who also acknowledged the difficulty of recruiting patients for enrollment in a study.

They agreed to collaborate.  However, their individual hospitals would not give them permission to share patient data due to privacy constraints.

What can they do so that they can do robust research on this challenging patient population while maintaining rigid privacy standards?



## Primary Objective:

To generate a synthetic medical dataset for a patient population

## Secondary Objectives:

1.  Demonstrate the transformation of human-interpretable categorical and continuous data to a tensor input, and the re-transformation of the tensor output to human-interpretable data
2.  Explore the use of tabular data (continuous and categorical variables) in deep learning generative models
3. Evaluate the performance of generative models regarding its ability to create synthetic data that closely approximates the real data:  
  *   Variational AutoEncoder
  *   Generative Adversarial Network


## Methodology:
### DATA LOADING and PREPARATION

-  Using medical patient data from https://synthetichealth.github.io/synthea/
1.  Get continuous  and categorical variables
2.   Merge continuous and categorical variables
3.    Split data to Train / Test sets
4.  Data Transformation

### CREATE AND TRAIN VARIATIONAL AUTOENCODER (VAE) MODEL

1.  Define sampling batch
2.  Create Encoder
3.  Create Decoder
4.  Define losses
5.  Compile and train
6.  Visualize results
7.  Evaluate model on Test set

   ### CREATE AND TRAIN A GENERATIVE ADVERSARIAL NETWORK (GAN) MODEL

1.  Create Generator
2.  Create Discriminator
3.  Define Losses
4.  Compile and train
5.  Visualize results
5.  Evaluate model on Test set

## RESULTS
### VAE
![image](https://github.com/user-attachments/assets/15da94ee-136c-42d1-821d-4eef5b39f45a)

![image](https://github.com/user-attachments/assets/8fcc7d3d-7a53-4b00-a215-c9ad158a21be)

![image](https://github.com/user-attachments/assets/8e764e7a-d8aa-4d21-802e-48316fddce85)

![image](https://github.com/user-attachments/assets/a190428d-54ba-4abe-8d2b-df2cd3c73492)


### GAN
![image](https://github.com/user-attachments/assets/64cb9f7f-d67a-4138-8f26-7fa6b3338abb)

![image](https://github.com/user-attachments/assets/78276d83-76cb-4808-993f-73a5eee9d4a3)

![image](https://github.com/user-attachments/assets/a5e3ddcb-0c1c-48b5-af5d-fb90aa659ff5)

![image](https://github.com/user-attachments/assets/9ae32aea-e361-48f9-b856-673ab5c3d7ce)


### Findings:

 The GAN model used a single hidden layer (with 100 nodes for the generator and 150 nodes for the discriminator), and 10 latent variable size.  The model **training showed a torsade pattern illustrating the adversarial method** between the training of the generative and discriminator components.  It can be considered that 'convergence' was reached at around Epoch 100 - 200.

The **synthetic data generated from the Test set showed a distribution nearly equivalent with the Real Test set**.  (Note: the distribution was more equivalent at lesser Epochs, but a higher Epoch was used here to demonstrate the adversarial training).  This shows the the **model training was reasonable and is able to generalize to new data**.

This shows that **GAN can be applied to generate synthetic tabular data containing both continuous and categorical variables**.

### COMPARING RESULTS BETWEEN VAE AND GAN:

**VAE reached convergence faster.  Both VAE and GAN and had similar distributions between real and synthetic data** with this small dataset.  

Due to the continuous improvement in training, it can be hypothesized that GAN may be more useful for more complex and bigger datasets.

### TECHNICAL CONCLUSION:

VAE and GAN generative models can generate reasonable synthetic tabular data containing heterogenous variables.  

### REAL-WORLD APPLICATION:

This will be useful in medical research to alleviate privacy restrictions.  It will enable data sharing between different institutions which will lead to data that is more representative of the whole population, particularly for rare diseases.










