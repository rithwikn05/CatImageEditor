The cat image editor converts an RGB that a human would see to how the cat would see the same image.

To do this, I did three main steps:
1. Convert the RGB values at each pixel to a wavelength value
  - I first converted RGB to CIE XYZ values using already existing coefficients.
  - I then convert the X, Y, Z into X, Y chromaticity values which allows me to use the spectral locus values correlating to find a wavelength value for the chromaticity values
2. Convert the wavelength back into a RGB value based on the data given in the papers (cat's eyes are sensitive at around 450 nm and 550 nm)
  - Based on the papers, I created the function to represent the quantum sensitivity in relation to the wavelength as two Gaussian functions centered at 450 nm and 550 nm respectively with standard deviations of 55 nm.
  - I plug the wavelength into both Gaussian functions and get a wavelength value that follows the function representing the cat's vision. I then normalize and multiply the values by 255 to get it back into RGB

I have some results where I took an image and applied this function in the repo along with the code.
