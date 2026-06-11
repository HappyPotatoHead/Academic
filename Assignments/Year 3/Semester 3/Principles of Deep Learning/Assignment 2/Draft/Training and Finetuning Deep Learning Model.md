# What we have now

We have the code for:
1. EfficientNetV2
2. Swin 

The dataset that we have is PlantVillage. Which is a clean, simple dataset that is easy to get good results with.

# What we can do now

1. Use the saved models trained from PlantVillage
	- Train it again on the training dataset of PlantDoc
2. Create a Hybrid CNN Transformer model 
	- Train it on the PlantVillage
	- Use a saved checkpoint and train it again on the training set of PlantDoc
3. Compare the results

# Preprocessing

We keep it simple

**OpenCV**
1. CLAHE

**Data Augmentation**
1. RandomResizedCrop
2. RandomHorizontalFlip
3. RandomVerticalFlip
4. RandomRotation
5. ColorJitter
6. RandomGrayscale
7. GaussianBlur
8. Random Erasing

# Sources

- **Singh et al. (2020)** — PlantDoc original paper _"PlantDoc: A Dataset for Visual Plant Disease Detection"_ ACM IKDD CoDS and COMAD 2020 
- **Hughes & Salathé (2015)** — PlantVillage original paper _"An open access repository of images on plant health to enable the development of mobile disease diagnostics"_ 
- **Salman et al. (2025)** — ViT + MoE on PlantVillage _"Plant disease classification in the wild using vision transformers and mixture of experts"_
- **Hasan et al. (2025)** — Multi-dataset approach with EfficientNet on PlantDoc _"Plant Leaf Disease Detection Using Deep Learning: A Multi-Dataset Approach"_
- **Kaur et al. (2024)** — Systematic review of DL for plant diseases 2020–2024 _"A systematic review of deep learning techniques for plant diseases"_ 
- **PMC Review (2025)** — Review of deep learning architectures for plant disease detection _"A review of deep learning architectures for plant disease detection"_ 
- **Xu et al. (2024)** — Dataset challenges and opportunities _"Plant disease recognition datasets in the age of deep learning: challenges and opportunities"_ 
- **Yu et al. (2023)** — Inception + ViT hybrid for plant disease _"Inception convolutional vision transformers for plant disease identification"_ — Internet of Things, 2023 → Directly justifies your CNN-Transformer hybrid idea — a published precedent



if you want to add yolo/object detection, the assignment becomes more of an engineering thing than an comparison thing. also it defeats the purpose of introducing a model that is good enough to handle the noises in plantdoc, hence why it becomes more of an engineering thing. 

Also we have to knock the learning rate down to 1/10 of 0.001. 

so what I need yall to do now is 

1. Preprocessing
	- Implement the OpenCV CLAHE
	- Update the `torchvision.transform` to include the new data augmentations
	- Clean up the dataset folders so that it matches PlantVillage's 
2. Create the hybrid model 
	- Write the hybrid class model
		- Take the feature maps from EfficientNetV2 backbone
		- Reshape into tokens
		- Feed into Swin Transformer blocks
	- Please make sure the dimension matches
	- Train the model on the CLEANED PlantDoc and test it again
3. Ablation Studies
	- Take the checkpointed models (standalone ones) 
	- Run the training on the new CLEANED PlantDoc Dataset using the new updated augmentations
	- Log results