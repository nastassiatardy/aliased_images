# Registration of aliased images

Realigning two images that are periodically offset by an unknown translation is relatively easy if both images are well sampled, because the translation results simply in a multiplication in the Fourier domain.

However, if the two images have been poorly sampled after being shifted, the situation is more complex due to the phenomenon of aliasing, which disrupts the process.

The objective of this project is to implement translation-based registration in the case of well-sampled images and then to propose solutions in the case of aliased images.
