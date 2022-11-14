---
layout: post
title:  "Generating images with Keras Stable Diffusion [TPU]"
---

# Stable Difussion fun with the small and infinitely big worlds

In order to generate the images below I used the Keras implementation with TPU.
This colab which only has a dozen lines of code allowed me to evaluate the performance of generating images on TPUs with the KerasCV implementation of [stability](https://stability.ai).ai's text-to-image model, [Stable Diffusion](https://github.com/CompVis/stable-diffusion)

Running the collab end to end can take up to 10-15min, once the model is loaded I am able to generate 32 images in about 2 minutes or 4 sec per image.  

[High-performance image generation using Stable Diffusion in KerasCV](https://keras.io/guides/keras_cv/generate_images_with_stable_diffusion/)



{% include image-gallery.html folder="/uploads/album" %}
