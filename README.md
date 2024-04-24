[Website Link](https://expo.baulab.info/2024-Spring/debruynt/)

# Stress-Testing Stable Diffusion Concept Erasure
Travis DeBruyn and Ryan Chapados

## Introduction
  The issue of unwanted content is one that has plagued diffusion models since their inception. Recently, there have been a few different approaches to this, including a newer method by Rohit Gandikota, Joanna Materzy´nska, Jaden Fiotto-Kauffman and David Bau in their preprint called [Erasing Concepts from Diffusion Models](https://arxiv.org/pdf/2303.07345.pdf).
  
  Most methods used to solve the issue of unwanted content -- like undesirable image removal, image cloaking, or model editing -- rely on directly interfering with the model, whether it be through changing the train dataset or editing the output. The new angle that concept erasure provides is one that seeks to employ a model's learning against itself. In concept erasure, a diffusion model has its weights fine-tuned using negative guidance.
  
  Concept erasure is naturally void of many of the disadvantages that are present in other methods working to achieve a similar goal. The goal of this project is to attempt to uncover disadvantages that remain undiscovered.

## Review
The overarching limitation of the concept erasure method is that it is only as good at removing concepts as it is at identifying them. 

The training of the Erasing Stable Diffusion, or ESD model includes two diffusion models: One whos parameters *θ*, are updated during training, and a second whos parameters θ\* are frozen. The fine tuning of the model weights occurs during denoising stage of image generation, where the image is only partially denoised. The unfrozen model *θ* will generate a partially denoised image, conditioned on the given concept to erase *c*. The frozen model θ\* will then predict the noise, continuing the image generation process. The frozen model makes two predictions, once predicting the noise while conditioned by *c*, the second time predicting without conditioning. The images generated are then fed into the loss function, which tunes *θ* to reduce the probability that the output image will be classified as *c*.

## Methodology
### Preliminary Questions
1. Engineering prompts to intentionally attack edge cases that simulate a user attempting to "work around" erased concepts. For example, if the concept that has been removed is 'car', what happens when the model is asked to create a pickup truck with no truck bed?

2. As noted in the paper, removing different types of concepts poses different challenges. Specifically, removing object classes can cause the concept erasure to fail while only erasing particular attributes of concepts. Is there a common feature in the offending concepts?

3. Would complex concepts benefit from being removed as a list of subconcepts? For example, would "the sport of baseball" benefit from being input for erasure as "baseball, bat, catcher, outfielder, shortstop, etc."

### Figure

## Experimental Findings

## Conclusions
