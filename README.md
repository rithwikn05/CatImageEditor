The cat iamge editor converts an rgb that a human would see to how the cat would see the same image.

To do this, I did three main steps:
1. Convert the RGB values at each pixel to a wavelength value
  - I first converted RGB to CIE XYZ values using already existing coefficients.
  - I then convert the X, Y, Z into X, Y chromacity values which allows me to use the spectral locus values correlating to find a wavelength value for the chromaticity values
2. Convert the wavelength back into a rgb value based on the data given in the papers (cat's eyes are sensitive at around 450 nm and 550 nm)
  - Based on the papers, I decided to create the function to represent the sensitivity in relation to the wavelength as two gaussian functions centered at 450 nm and 550 nm respectively with standard deviations of 55 nm.
  - I plug the wavelength into both gaussian functions and get a wavelength value that follows the function representing the cat's vision. I then normalize and multiply the values by 255 to get it back into RGB

I have some results where I took an image and applied this function to. The results are also in this repository.
