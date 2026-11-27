# Midterm | Creating Images with Diffusion Models

### Generative Artificial Intelligence and Image Synthesis

## Project Overview

This project explores the implementation, training, and evaluation of a class-conditioned denoising diffusion model capable of generating images using the Fashion-MNIST dataset.

The objective was to gain practical experience with generative artificial intelligence, neural network architectures, progressive noise addition, noise prediction, and image generation.

The model was trained using a compact U-Net architecture in Google Colab with GPU acceleration.

## Learning Objectives

- Understand the theory behind diffusion models.
- Implement a U-Net neural network architecture.
- Explore forward and reverse diffusion processes.
- Train a generative AI model using image data.
- Analyze training and validation loss.
- Evaluate generated images using CLIP.
- Identify model limitations and potential improvements.

## Technologies Used

- Python
- PyTorch
- Google Colab
- Jupyter Notebook
- CUDA GPU
- Fashion-MNIST
- Matplotlib
- CLIP

## Model Configuration

| Parameter | Configuration |
|---|---|
| Dataset | Fashion-MNIST |
| Training Images | 48,000 |
| Validation Images | 12,000 |
| Image Dimensions | 28 x 28 pixels |
| Image Type | Grayscale |
| Architecture | U-Net |
| Training Epochs | 30 |
| Diffusion Steps | 300 |
| Batch Size | 64 |
| Learning Rate | 0.001 |
| Optimizer | Adam |
| Loss Function | Mean Squared Error (MSE) |
| Noise Schedule | Linear |
| Computing Environment | Google Colab GPU |

## Understanding Diffusion Models

### Forward Diffusion

The forward diffusion process gradually introduces Gaussian noise into an original image over multiple timesteps until most of its recognizable visual information is lost.

### Reverse Diffusion

The reverse diffusion process starts with random noise and uses a trained neural network to progressively remove noise and generate an image.

### U-Net Architecture

The U-Net architecture supports noise prediction through:

- Encoder layers
- Decoder layers
- Bottleneck representations
- Skip connections
- Class conditioning
- Timestep embeddings

These components allow the model to process visual features at multiple spatial resolutions.

## Experimental Results

| Performance Metric | Result |
|---|---:|
| Initial Training Loss | 0.1160 |
| Final Training Loss | 0.0713 |
| Initial Validation Loss | 0.0931 |
| Final Validation Loss | 0.0733 |
| Lowest Validation Loss | 0.07147 |
| Best Model Checkpoint | Epoch 29 |
| Training Loss Reduction | Approximately 38.5% |
| Average CLIP Similarity | 0.2812 |

The reduction in training and validation loss demonstrated improvement in the model's ability to predict noise during training.

However, lower noise-prediction loss did not necessarily guarantee realistic images or accurate class-specific generation.

## CLIP Evaluation

The optional CLIP evaluation was completed to explore the relationship between generated images and their requested text descriptions.

Five generated images were evaluated against the text description "a grayscale image of a sandal."

| Sample | CLIP Cosine Similarity |
|---|---:|
| Sample 1 | 0.2806 |
| Sample 2 | 0.2712 |
| Sample 3 | 0.3039 |
| Sample 4 | 0.2660 |
| Sample 5 | 0.2846 |
| Average | 0.2812 |

The highest-scoring image visually resembled a handbag rather than a sandal.

This observation demonstrated that numerical similarity scores should not be interpreted as definitive evidence of image accuracy.

## Model Limitations

- Low-resolution grayscale images
- Limited to ten Fashion-MNIST clothing categories
- Inconsistent class-specific image generation
- Computationally intensive sequential sampling
- Limited evaluation sample size
- No independent classifier to verify class accuracy
- No saved image comparisons across early and later training epochs

## Potential Improvements

Future improvements could include:

- Enhancing the U-Net architecture with residual blocks and attention.
- Improving class conditioning.
- Generating multiple samples for each class.
- Evaluating images using an independent classifier.
- Comparing faster diffusion sampling methods.
- Saving intermediate image-generation results throughout training.
- Combining automated evaluation with human visual inspection.

## Real-World Applications

- Generative artificial intelligence
- Synthetic data generation
- Image synthesis
- Fashion concept prototyping
- Creative design
- Computer vision research
- Image restoration research

## Project Deliverables

- [Midterm Analysis Report](Midterm_Diffusion_Report.pdf)
- Jupyter Notebook implementation - pending repository upload

## Personal Learning Reflection

This project strengthened my understanding of how generative artificial intelligence models create new content through learned patterns.

Before completing this project, my understanding of AI-generated images was primarily conceptual. Implementing and training a diffusion model helped me understand the mathematical and computational processes involved in image generation.

I also learned that evaluating artificial intelligence requires more than examining training loss or relying on a single performance metric.

Although the model demonstrated improvements in noise prediction, some generated images did not accurately represent their requested categories.

This experience reinforced the importance of continuous evaluation, critical analysis, responsible AI development, and recognizing the limitations of machine learning systems.

## References

- [Ho et al. - Denoising Diffusion Probabilistic Models](https://arxiv.org/abs/2006.11239)
- [Radford et al. - Learning Transferable Visual Models From Natural Language Supervision](https://proceedings.mlr.press/v139/radford21a.html)
- [Xiao et al. - Fashion-MNIST Dataset](https://arxiv.org/abs/1708.07747)

---

[Return to Main Portfolio](../README.md)
