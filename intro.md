# Introduction
🚧🚧 Check back later for an updated version. 🚧🚧

In medical scenarios, imaging is crucial to provide context for diagnosis and treatment. Magnetic Resonance (MR) imaging has made it possible to view a patient's internal structures without invasive procedures. However, these methods have limitations such as patient safety, speed, and image quality that need to be addressed {cite}`graff,Yousufi`.

One reason MRI imaging is slow is because they require multiple samples of the same region to create a single view. The time taken to generate these images could be reduced if we could construct the entire view using fewer samples. Our work focuses on the application of compressed sensing, a technique that reconstructs the original signal from a sparse sample, thus requiring fewer samples than the Nyquist sampling criteria {cite}`lustig,zhang,Qaisar`.

Compressed sensing is a technique that can be implemented using various algorithms and regularizers, such as those proposed in {cite}`chambolle,boyd,clarkson,condat`. The first objective of our project is to understand and solve the Total Variation denoising (TVd) problem on grayscale images, which can be achieved by using the L2 regularizer optimized with the ADMM algorithm {cite}`chan`.

To achieve this, we started by implementing TVd for 1-dimensional signals and then proceeded to implement TVd L2 for images using the ADMM algorithm.

Finally, we implement proximal gradient descent {cite}`boyd` for compressed sensing on MRI images. We solve proximal gradient descent using primal dual splitting.

This is a Work-in-Progress project for the coursework ECE-GY-6123 Image and Video Processing by Dr. Yao Wang on Compressed Sensing techniques. The project is built by [Parisima Abdali](https://github.com/parisimaa) and [Shubham Gupta](https://github.com/iamshubhamgupto).



```{tableofcontents}
```
