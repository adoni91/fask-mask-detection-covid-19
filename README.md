# A Face-Mask Detection System Based on Deep Learning Convolutional Neural Networks

## Full paper => https://link.springer.com/chapter/10.1007/978-981-16-5559-3_23
The alarming situation caused by COVID-19 has prompted the artificial intelligence community to think about using new tools in order to contribute to the fight against COVID-19. Computer vision is a sub-discipline of AI that is blossoming since 2010s and helps in diverse fields like robotics, self-driving cars, health care by handling very complex nonlinear problems. In the wake of this, its contribution to the fight against COVID-19 has to be taken into account. In fact, only a few works have been published recently in that regard despite the seriousness of the situation. This is what fueled our desire to make a contribution. This work is intended to elaborate very powerful and robust mask detection model enabling the detection of not only individuals wearing the recommended masks from those who don’t, but the detection of a third category of people not wearing it appropriately is also taken into account by our model.


The system that we have built is intended to serve as a real-time face-mask detection application for health and safety on the grounds of the COVID19 situation. In fact, the face-mask detection models that have been elaborated so far had some shortcomings that needed to be addressed first:
* They have limited training data, and most of the images of the with-mask class have been artificially generated.
* The case where people don’t wear the mask the correct way is not handle as a category of its own.
* They have not enough images capable of confusing classifiers, what makes their models not effective when deployed in real-life situations.

Last but not least in order to meet the challenge of multi-faces detection, where many haven’t crossed the threshold yet, we made an extension of our system taking
into account these cases. To address these issues, we have collected a dataset composed with 5309 images gathering all the confusing specific cases possible, as shown in Sect. 4.1. In addition to the deficiencies related to the problem of datasets, the face-mask detectors that were built before were always considering two categories: people wearing masks and those who don’t which is not ideal. In fact, what usually happens in the streets is that people have masks with them but they don’t wear them properly. Most of the time masks are put under the nose, under the chin or just on an ear which is totally useless and prohibited.

So this class of masks worn incorrectly, as shown in Fig. 1; it is the one of the main feature of our system attesting its robustness. Consequently, we gathered grand total of 215 images of incorrectly worn mask images to create a third class of its own. After the collection of our rich and diversified dataset, our method was based on a two-step process:
1. detecting and localizing faces in video frames
2. applying face-mask classifier to the detected face in order to assign it a class among the three.

<img width="607" height="165" src="https://github.com/user-attachments/assets/8404afba-0ccb-4698-9de4-7766ca65c534" />

Our model was intended to provide analysis of mask wearing either in real time or with uploaded images or videos with a high degree of precision. It is made up of
two steps. The first step is the face detection and localization, and the second step concerns the face-mask classification.

<img width="602" height="295" src="https://github.com/user-attachments/assets/eb8184ec-c49e-4164-9513-bd015b5f8e6b" />

As we have mentioned it earlier, building a huge and diversified dataset was the first major challenge for our project. Since the outbreak of COVID-19, some people are
upset about the state of the world tried to build face-mask datasets that the scientific community could use. We first collected images from the Real-world Masked
Face Recognition Dataset (RMFD) [12]. This dataset was created from a python crawler tool using images from public figures and their corresponding masked face
images from massive Internet resources. Then, we collected artificially generated images from the face-mask dataset provided by Prajna Bhandary https://github.com/prajnasb/observations, consisting of 1376 images with 690 images containing people with face masks and 686 images containing people without face masks [13].
After merging these two datasets, we added images from various internet sources like kaggle https://kaggle.com/andrewmvd/face-mask-detection, the celebrity face
dataset [14], and then, we have scraped some specific images capable of confusing our classifier. These examples include people covering their faces with cloth parts, hijabs, women wearing burkas, people not wearing their mask correctly to name a few. Last but not least, data augmentation (by rotation, zooming and flipping) was performed on out dataset in order to balance out our classes and also increase the number of images for the training phase. Finally, we wound up with a dataset of 5303 images broken down as follows:

* 3200 images of people wearing a mask
* 1893 images of people not wearing a mask at all
* 211 images of people having a mask but not wearing it properly.

After loading the images by resizing them all with a shape (224, 224, 3), we split our data with 80% for the train (4242 images) and the remaining 1061 images for the test. The 80/20 split is due to the fact that we need as much as possible images in the training set because “the more we train the model the more it’s robustness increases”.

https://github.com/user-attachments/assets/805ed65d-ce3f-4fa5-b5c4-c8a957014cce




