---
layout: post
title:  "Generating images with Keras Stable Diffusion [TPU]"
---

# Stable Difussion fun with the small and infinitely big worlds

In order to generate the images below I used Keras's implementation that uses TPUs.
This colab with only has a few lines of code allowed me to evaluate the performance of generating images on TPUs with [stability](https://stability.ai).ai's text-to-image model, [Stable Diffusion](https://github.com/CompVis/stable-diffusion)

Running the collab end to end can take up to 8-10min, once the model is loaded I am able to generate 32 images in about 2 minutes or 4 sec per image.  

I have tested several text-2-image models and stable diffusion surely generates impressive results.

[High-performance image generation using Stable Diffusion in KerasCV](https://keras.io/guides/keras_cv/generate_images_with_stable_diffusion/)



{% include image-gallery.html folder="/uploads/album" %}

