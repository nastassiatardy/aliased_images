# Registration of aliased images

Realigning two images that are periodically offset by an unknown translation is relatively easy if both images are well sampled, because the translation results simply in a multiplication in the Fourier domain.

However, if the two images have been poorly sampled after being shifted, the situation is more complex due to the phenomenon of aliasing, which disrupts the process.

The objective of this project is to implement translation-based registration in the case of well-sampled images and then to propose solutions in the case of aliased images.

## Translation of aliased images 

From an original image, we use downsampling to artificially aliase the image. An integer translation can be easily obtained by cropping the original image at two different locations. On the other hand, a subpixel translation can be obtained using Fourier interpolation:
![image](https://github.com/nastassiatardy/aliased_images/blob/main/aliased_images/results/translated_aliased_images.png)

## Cross-correlation & Upsampling

To find the integer translation, one can use the cross-correlation matrix and locate the coordinates of its maximum:
![image](https://github.com/nastassiatardy/aliased_images/blob/main/aliased_images/results/cross-correlation.png)

To register images translated by a subpixel amount, we used the upsampling technique: first expand the image with 0, then smooth out the discontinuities using a lowpass filter:
![image](https://github.com/nastassiatardy/aliased_images/blob/main/aliased_images/results/upsampling.png)
