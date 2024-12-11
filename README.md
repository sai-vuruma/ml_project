# Generating Images from Audio

**Motivation:** There is an intersection between audio and visual features that needs to be exploited in order to achieve true multi-modality. This would eliminate the bias of intermediary modality and also pave the way for identifying more granular relationships between audio and visual information.

I built a network that leverages the encoder architecture from Autoencoder and the generator architecture from Generative Adversarial Networks. It is trained on a sample taken from the Multimodal Scene Classification dataset curated in https://www.kaggle.com/datasets/birdy654/scene-classification-images-and-audio. The encoder in the network ingests MFCC features extracted from audio signals and converts it into a latent space representation. This representation is fed to the generator which then upsamples it into an image. The network had a SSIM score of 0.463 and a HSS score of 0.999 indicating that it is able to generate images that reasonably match the expected output. From the eye test, the images are still grainy and pixels with low luminance aren't being generated properly. This can be attributed to the small training and testing sample used for the experiments, which is a major limitation of the study.

# Running the code

Use the code notebook in the repo and run each cell. The first cell must be uncommented if you're using Google Colab.

# Results

The network reported a loss of 4.691 on the test set which is slightly higher than the train loss indicating moderate performance and generalization. Comparing the network’s
predictions on the test set with the target images using the eye test, it is clear that the generated images are similar but not quite matching the expected output. The texture is grainy and no distinguishing features like the trees in the background are being captured. Another observation is that the network is unable to generate pixels that have low luminance as seen in Fig 9. The figure shows a side-by-side comparison between the expected output (real images) and actual output (generated images).

![image](https://github.com/user-attachments/assets/3d059c6f-f5a2-45b2-af41-296ec704f7b2)

Refer to the docs folder to see how the project has progressed. The Report contains all the findings from the study, and so does the presentation.
