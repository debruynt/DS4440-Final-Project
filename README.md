# Stress-Testing Stable Diffusion Concept Erasure
Travis DeBruyn and Ryan Chapados

## Introduction
  The issue of unwanted content is one that has plagued diffusion models since their inception. Recently, there have been a few different approaches to this, including a newer method by Rohit Gandikota, Joanna Materzy´nska, Jaden Fiotto-Kauffman and David Bau in their preprint called [Erasing Concepts from Diffusion Models](https://arxiv.org/pdf/2303.07345.pdf).
  Most methods used to solve the issue of unwanted content -- like undesirable image removal, image cloaking, or model editing -- rely on directly interfering with the model, whether it be through changing the train dataset or editing the output. The new angle that concept erasure provides is one that seeks to employ a model's learning against itself. In concept erasure, a diffusion model has its weights fine-tuned using negative guidance.
  Concept erasure is naturally void of many of the disadvantages that are present in other methods working to achieve a similar goal. The goal of this project is to attempt to uncover disadvantages that remain undiscovered.

## Review


## Methodology
1. Engineering prompts to intentionally attack edge cases that simulate a user attempting to "work around" erased concepts. For example, if the concept that has been removed is 'car', what happens when the model is asked to create a pickup truck with no truck bed?
<img src="![car_erase_replace](https://github.com/debruynt/DS4440-Final-Project/assets/71042338/ba653a68-d6ca-4b77-be5d-809b8a3c365e)" style="max-width:50%">


2. 

# Figure

## Experimental Findings

## Conclusions



<img src="webhook.png" style="max-width:100%">
