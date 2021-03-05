
# **Table of Contents**

- Introduction
- Brief Background about the Problem
- Dataset
- Work Done/ Procedure
- Results and Analysis
- Conclusion
- References

# **Introduction**

## **Brain Tumor Detection Project**

This project comprises a program which receives a brain Magnetic Resonance Image (MRI) and gives a diagnosis that can be the presence or not of a tumor in that brain.

## **Why this task?**

In clinical analysis, checking brain tumors among a lot of MRI pictures, take specialists much time. For instance, in tests of this undertaking, a patient has around 200 MRI pictures, however, tumor tissues just show up in 15 pictures. Thus, this venture intends to naturally recognize tumor tissues in a huge measure of MRI picture information.

# **Brief Background about the Problem**

The result when we give an image to the program is a probability that the brain contains a tumor, so we could prioritize the patients which magnetic resonance have higher probabilities to have one, and treat them first.

Another objective could be to move the obligation of seeing these pictures from the specialists to the machine, which in the long run could have a greater ability of detection, as it has learned by viewing an enormous number of images knowing their real diagnosis. This would be a clear example of cooperation between humans and machines.

## **Our Objectives:**

1. Naturally, recognize if tumor tissue shows up in the MRI picture.
2. Automatic brain tumor detection in MRI picture.

# **Dataset**

The dataset utilized in the task is a lot of pictures with and without tumors, from which we know the genuine finding. You can discover it here:

[https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection](https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection)

## **About the Data:**

The dataset contains 2 folders: yes and no which contains 253 Brain MRI Images. The folder yes contains 155 Brain MRI Images that are tumorous and the folder no contains 98 Brain MRI Images that are non-tumorous.

# **Work Done/ Procedure**

First, we had to do some image processing, and then pass 80% of these images to a neural network, make it learn and be capable of making an accurate diagnosis of a new image.

The other 20% of the images are used to test the model. We will compare their real diagnosis to the one that the model gives, to see how it performs.

## **Steps:**

Eventually, images are data, since they contain pixels which also contain information about their color. We can manipulate this information to achieve our goals which, in this case, are making the images better for the model to learn. The objective here is to make all the images as similar as possible, so that the actual discriminating feature is the presence or not of a tumor, and not the difference of shape, size, color, etc. of the images.

**Original images**

![](RackMultipart20210305-4-1lgpfdx_html_63d392e4f806dac9.png)

**Squaring**

![](RackMultipart20210305-4-1lgpfdx_html_e2dcee6bc5eabab4.png)

**Resizing**

![](RackMultipart20210305-4-1lgpfdx_html_eb685f9ea8188d8c.png)

**Grayscale**

![](RackMultipart20210305-4-1lgpfdx_html_7394bb18990db097.png)

**Median Filter**

![](RackMultipart20210305-4-1lgpfdx_html_7394bb18990db097.png)

**Black and white**

![](RackMultipart20210305-4-1lgpfdx_html_e3ee361435efcf76.png)

At this point, each image is a 2-dimension NumPy array with 128 x 128 shape. In order to put all the images together in a Pandas data frame, we had to flatten each array so the dimension is 1 and its shape is 16,384.

Once we have these data frame, we can train the model with 80% of the images, and test it with the other 20%.

# **Results and Analysis**

The result of testing is the following Confusion Matrix:

![](RackMultipart20210305-4-1lgpfdx_html_d996e30fc3f34879.png)

We can see the actual diagnosis on y-axis and the predicted diagnosis on the x-axis. We can see that the model has learnt better to detect the tumors than the not tumors. It could be because the dataset contained more tumor images than not tumor images.

**Accuracy:**

![](RackMultipart20210305-4-1lgpfdx_html_9def6f4e13c62e43.png)

Accuracy = (32+4)/(32+4+15+0)

**=70.5%**

# **Conclusion**

- Given that we can precisely automate the process of detecting whether a brain tumor is present in a patient or not, hospitals and patients will be able to simplify their workflow for detecting anomalies much earlier and are able to capture it with precision without having to sacrifice accuracy.

- It is really important to add that because image-based tumor recognition has become a well-defined problem with heavily promising solutions, we see the viability in the productionization and scale in developing this product further.

- In this decade (2020-2029), the necessity for automation within care delivery will hopefully be deployed at scale, putting the core central focus of the patient back into the hands of the care providers, while lining up monetary incentives for all parties involved via an inverse system between efficiency and cost with automation.

# **References**

- Kermi, A., Andjouh, K., Zidane, F.: Fully automated brain tumour segmentation system in 3D-MRI using symmetry analysis of brain and level sets. IET Image Process. 12, 1964–1971 (2018)

- Khotanlou, H., Colliot, O., Atif, J., Bloch, I.: 3D brain tumor segmentation in MRI using fuzzy classification, symmetry analysis and spatially constrained deformable models. Fuzzy Sets Syst. 160, 1457–1473 (2009)

- Prastawaa, M., Bullitt, E., Geriga, G.: Simulation of brain tumors in MR images for evaluation of segmentation efficacy. Med. Image Anal. 13, 297–311 (2009)

- Sharma, N., Aggarwal, L.M.: Automated medical image segmentation techniques. J. Med. Phys. 35, 3–14 (2010)

- Despotovic, I., Goossens, B., Philips, W.: MRI segmentation of the human brain: challenges, methods, and applications. Comput. Math. Methods Med. 2015, 23 (2015)

- Wirtz, C.R., et al.: The benefit of neuronavigation for neurosurgery analyzed by its impact on glioblastoma surgery. Neurol. Res. 22, 354–360 (2000)

- Yanyun, L., Zhijian, S.: Automated brain tumor segmentation in magnetic resonance imaging based on sliding-window technique and symmetry analysis. Chin. Med. J. 127, 462–468 (2014)

- Işın, A., Direkoğlu, C., Şah, M.: Review of MRI-based brain tumor image segmentation using deep learning methods. Procedia Comput. Sci. 102, 317–324 (2016)

- Ronneberger, O., Fischer, P., Brox, T.: U-Net: convolutional networks for biomedical image segmentation. In: Navab, N., Hornegger, J., Wells, W.M., Frangi, A.F. (eds.) MICCAI 2015. LNCS, vol. 9351, pp. 234–241. Springer, Cham (2015). https://doi.org/10.1007/978-3-319-24574-4\_28

- Havaei, M., et al.: Brain tumor segmentation with Deep Neural Networks. Med. Image Anal. 35, 18–31 (2017)
