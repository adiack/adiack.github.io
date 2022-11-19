---
layout: post
title:  "Generating images with Keras Stable Diffusion [TPU]"
---

# Using TPUs to Generate Stunning Images with Stability.ai's Text-to-Image Model 

(https://stability.ai).ai's text-to-image model generates stunning images. By using Keras's implementation with TPUs, I was able to create large batches of stunning images. The gallery below shows some of the best ones. 

This colab only has a few lines of code, but it generates images at an impressive speed on TPUs. It uses stability.ai's text-to-image model, [Stable Diffusion](https://github.com/CompVis/stable-diffusion). 

Running the colab end to end can take up to 8-10 minutes, but once the model is loaded I can generate 32 images in about 2 minutes, or 4 seconds per image. 

I have tested several text-to-image models and Stable Diffusion definitely generates impressive results.


[High-performance image generation using Stable Diffusion in KerasCV](https://keras.io/guides/keras_cv/generate_images_with_stable_diffusion/)

In some of the images below I had fun mixing the infinite big and small worlds

{% include image-gallery.html folder="/uploads/album" %}

