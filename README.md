# GANForge: Artistic Style Transfer using CycleGAN

## Overview

GANForge is an implementation of CycleGAN for artistic style transfer. The project learns to translate real-world photographs into Monet-style paintings without requiring paired training examples.

Unlike traditional supervised image translation methods, CycleGAN learns mappings between domains using unpaired datasets through adversarial learning and cycle-consistency constraints.

---

## Objective

The goal of this project is to:

* Perform artistic style transfer using CycleGAN.
* Translate photographs into Monet-style artwork.
* Learn image-to-image translation from unpaired datasets.
* Preserve image content while adapting artistic style.

---

## Dataset

**monet2photo Dataset**

Two image domains are used:

* Domain A: Monet Paintings
* Domain B: Real Photographs

The model learns bidirectional mappings between the two domains without requiring corresponding image pairs.

---

## Methodology

### CycleGAN Architecture

The framework consists of:

#### Generators

* Generator G: Photo → Monet
* Generator F: Monet → Photo

#### Discriminators

* Discriminator D_Monet
* Discriminator D_Photo

The discriminators distinguish generated images from real images in their respective domains.

---

## Loss Functions

### Adversarial Loss

Encourages generated images to resemble real images from the target domain.

### Cycle Consistency Loss

Ensures that translating an image to the target domain and back reconstructs the original image.

### Identity Loss

Helps preserve colors, structure, and semantic information during translation.

Total Objective:

CycleGAN Loss = Adversarial Loss + Cycle Consistency Loss + Identity Loss

---

## Implementation

### Environment

* Python
* PyTorch
* CycleGAN Framework

### Training

```bash
python train.py \
--dataroot ./datasets/monet2photo \
--name monet2photo_cyclegan \
--model cycle_gan
```

### Testing

```bash
python test.py \
--dataroot ./datasets/monet2photo \
--name monet2photo_pretrained \
--model test \
--no_dropout
```

## Results

The trained model successfully learned stylistic transformations between photographic and artistic domains, producing Monet-inspired renderings while preserving scene layout and object structure.

## Applications

* Artistic Style Transfer
* Domain Adaptation
* Medical Imaging
* Satellite-to-Map Translation
* Image Restoration
* Creative AI Systems

## Future Work

* Quantitative evaluation using FID and LPIPS
* Higher-resolution image generation
* Attention-based generators
* Multi-style artistic transfer
* Real-time deployment

## Author

Dipsikha Rano
IIT Kanpur
