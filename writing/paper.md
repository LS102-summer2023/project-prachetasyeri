# LS 102 - Computer Science Research Paper

## Emotion Detection in Virtual Medical Consultations: A Computer Vision-based Approach to Analyze Pain and Increase Patient Care Efficsey

Prachetas Yeri

---
## I. Abstract

Currently, assessment of pain occurs through self-report, external observations, or physiological tests[1]. Not all patients can express their experience of pain, such as patients in a coma or neonates[2]. Patients may express several emotions that are unidentified by humans that can be detected by nonhuman observers, potentially aiding in the diagnosis of disease [3]. There are six types of human emotions shown to be universally recognizable across different cultures [4]: anger, disgust, fear, happiness, sadness, and surprise. In recent years, the field of emotion detection has been prevalent. Using Machine Learning(ML) algorithms, emotions can be detected from real-time videos. The research analyzes video feed(unimodal) that uses Convolutional Neural Networks(CNN)- a deep learning technique to detect emotions in patients during a virtual consultation. This strives to help medical practitioners understand their patients' emotions which could help in their diagnosis of disease. Additionally, Python libraries such as Keras, and TensorFlow in the building of the prototype and used Cascade Classifier. The present study aims to see if Computer Vision(CV) can be used to identify emotions and pain in virtual consultations between medical practitioners and patients is feasible and can improve medical care.


## II. Motivation
During the COVID-19 pandemic, it was evident that for patients with lower immunity, in-person consultations would be risky due to coronavirus exposure. These patients would benefit greatly from online consultations. Although possible, online sessions would not be effective compared to face-to-face consultations because doctors could not get body language cues from the patient. Would the ability to identify cues from patients benefit the diagnosis of disease in virtual consultations? If online consultations were more reliable, here are a few ways the patients would benefit:

  ◦ Patients may have a primary doctor whom they see regularly and such a doctor would be familiar with their medical history. In these cases, the patient would be able to consult their preferred doctor over the Internet and have a just as effective consultation.

  ◦ Accessibility of medical services would be increased and would benefit patients without easy access to good medical services. They would be able to reach a qualified doctor and get treated remotely. 

  ◦ Patients would be able to get multiple opinions from doctors with completely different perspectives. This could include doctors from different backgrounds, qualifications, and doctors from different countries.

  ◦ According to World Health Organization[5] as of 2020, there were 53.52 physicians per 10,000 people in Austria whereas in Chad there were only 0.6 physicians per 10,000 people. If online consultations are feasible, the ratio of physicians to patients would be drastically increased improving the medical state of the world.


## III. Review of Literature

Based on a clinical study of 862 inpatients and 115 nurses, researchers proved that Caregivers are often inaccurate in their pain assessments and tend to misjudge pain, especially in the case of symptom uncertainty[6]. Research on emotion detection mainly encompasses static images and text. Only recently emotion detection has been researched concerning real-time video and can be implemented in several fields. Fernando Alonso-Martin et al. [7] have used a multimodal user-emotion detection system for social robots. Using emotion detection information from the user, the interaction between the robot and the user makes its way towards a more probable interaction and allows the robot the dialog to adapt. Additionally, they have used emotions to understand the degree of confidence projected by the user. 

  
Furthermore, Ayman Altameem et al. [8] have researched using a Support Vector Machine(SVM) model which was connected to the vehicle's electronics to detect if the driver is drowsy, angered, or if there is any sudden change in emotion. This allows the model to identify if they are driving safely and if not, alerts the driver and slows the car down. The algorithm was tested with several different parameters including different levels of light intensity and various distances between the camera and subject. Bartlett et al. [9] analyzed the use of computer vision (CV) and pattern recognition to understand if computers could distinguish between genuine and false pain expressions. The researchers experimented with videos of genuine pain versus those of false pain. Computer Expression Recognition Toolbox (CERT) analyzed the videos and showed significant improvements in accuracies of detecting false pain in comparison to human examination.

  
Convolutional Neural Networks (CNN) were used to examine real-time emotions from facial expressions [10]. In the author's game, CNN was deployed to an input video stream to capture the user's facial expression allowing them to control the game using their face. The facial changes detected would then be processed, decreasing quick facial variations and other noise. Gkikas et al. [11]  analyze different automatic methods to asses pain based on deep learning methods. They identified 110 publications and sorted them by the number of channels and if the temporal dimension was used. The results showed several multimodal approaches for automatic pain estimation and observed significant improvements when temporal exploitation of modalities was used. One method discussed in the paper was a vision-based temporal exploitation which used CNN for the model. This paper analyses a prototype that also used CNN and deep learning.

Although, emotion detection has been researched in several other fields, can it be linked to the degree of pain felt by patients and be conveyed to the physician so they can act accordingly?

## IV. Goals of the Project

The following is what the project entails and what is aimed to be analyzed or discussed.

   ◦ To correlate emotion and pain detection using CNN and deep learning models
  
   ◦ Understand if this method is feasible to aid in the diagnosis of diseases in virtual consultations
  
   ◦ If it is feasible, can the quality and accessibility of medical services improve?
   
   ◦ Can computers and technology help scale up virtual diagnosis in medical fields?

## V. Methodology

### Exploratory Data Analysis

The dataset used for the prototype used in this paper is "fer2013" downloaded from Kaggle[12] which contains 35,887 images of various classes (0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral). The dataset used in the model was downloaded from Kaggle. The dataset consists of 48x48 grayscale images of unique faces. Each face is approximately centered and is the same size in the image to avoid training mismatches. In the current prototype, an 80% (28,709 images) for training data and 20% (7,117 images) for testing data split was used. Below are examples of the dataset and some key features identified for each class.




![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/f2fa6e3d-1953-451c-8b1c-ab1d7ff7cabe)

###### _Fig 1.0 - Sample of angry images from the dataset[12]_


   ##### __Observable features of "Anger" include:__ 
      
      1. Eyebrows arched
      2. Eyes contracted
      3. Mouth frowned or bent
      4. Cheeks clinched
      5. Jaw projected


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/516ecbdd-df2c-4ab7-85a3-16b6c893f166)

###### _Fig 1.1 - Sample of disgusted images from the dataset[12]_


   ##### __Observable features of "Disgust" include:__
      
      1. Eyebrows contracted
      2. Eyes squinted
      3. Mouth opened or bent to one side
      4. Cheeks dropped elongating the face
      5. Tension visible on the forehead


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/978e6d4a-6a6d-43a9-9f0b-fb8716fc12e1)

###### _Fig 1.2 - Sample of fearful images from the dataset[12]_


   ##### __Observable features of "Fear" include:__

      1. Frontalis(forehead) tentioned[13]
      2. Mentalis(midline above chin) stretched[13]
      3. Eyebrows thrust upwards
      4. Eyes widened
      5. Mouth opened laterally or vertically
      6. At times hands touching the face


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/a8f0f490-4d7b-4a9b-af32-dbe78c585755)

###### _Fig 1.3 - Sample of happy images from the dataset[12]_


   ##### __Observable features of "Happy" include:__

      1. Orbicularis oculi (outer cleft of the eye) contracted[13]
      2. Zygomaticus major(midpoint of a line between nose and ear lobe) raised[13]
      3. Eyebrows relaxed
      4. Eyes slightly closed
      5. Cheeks contracted (lifted)
      6. Angle of mouth drawn upward and laterally
      7. Frontalis relaxed
      8. Nose slightly dilated
      9. In most cases, teeth are visible slightly


  ![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/f9650aae-7c32-4c42-ab59-5861c00dcc67)

   ###### _Fig 1.4 - Sample of sad images from the dataset[12]_


   ##### __Observable features of "Sad" include:__
      
      1. Corrugator(above medial aspect of left eyebrow) clenched[13]
      2. Depressor Anguli Oris(below left corner of mouth) pronouned[13]
      3. Eyebrows tense
      4. Eyes slightly closed
      5. Angle of mouth drawn downward (frown)
      6. Nose slightly dilated


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/c9918534-054b-4e4b-a5a3-3f94cd7a0b3c)

###### _Fig 1.5 - Sample of surprise images from the dataset[12]_


   ##### __Observable features for "Surprise" include:__

      1. Eyebrows raised
      2. Eyes widened
      3. Jaw extended
      4. Mouth opened vertically
      4. Face elongated


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/71b25098-5843-43e4-a72c-f94d0f985970)

###### _Fig 1.6 - Sample of neutral images from the dataset[12]_


   ##### __Observable features for "Neutral" include:__

      1. Orbicularis oculi relaxed
      2. Zygomaticus major relaxed
      3. Eyebrows relaxed
      4. Eyes neutral
      5. Cheeks rested
      6. Frontalis relaxed

### Prototype

__The model this paper analyzes and uses Sunny Kusawa's Emotion_detection_with_CNN model[14] which uses CNN and deep learning in training the model.__

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/668baf35-312d-4d42-86c5-462326663394)

###### _Fig 2.0 - Diagrammatic representation of a CNN[15]_

Emotion detection using computer vision has attracted significant attention from programmers over the past few years. Many have used different models or methods to create an emotion detection program that analyses images and outputs the emotion predicted by the model. Initially, a code from GitHub was found and tested. The model was for detecting emotion in images which would not be feasible for this application. In a virtual consultation between medical practitioners and patients, the model should be able to detect emotion using real-time video which would allow for a live feed to be available for the doctor.

The prototype uses pythons Keras, Tensorflow, and Cascade Classifier to predict emotions in real-time videos. Keras is an open-source library that provides a Python interface for artificial neural networks(ANN) and DL. ANN is inspired by the structure of neurons in the human brain[16]. It was developed to make deep learning models as quickly and as easily as possible. Keras runs on Python 2.7 or 3.6 and TensorFlow[17]. Tensorflow is another open-source library for fast numerical computing. It was created and is maintained by Google. It can run on single CPU systems, GPUs, and mobiles[17]. Tensorflow is used to build artificial intelligence(AI) and Machine learning(ML) algorithms. 

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/5fbf1acc-de0e-4446-9905-03e41e4795b9)

###### _Fig 2.2 - Shows the interest in Tensorflow over the last five years according to Google Trends[18]_

Videos are nothing but a series of static images. In emotion detection of real-time videos, these static images are analyzed and the emotion predicted is displayed on the module. Cascade Classifier was used to identify faces and classify them into their emotion classes.

### Steps to train the model

  1. All necessary packages are imported

  2. All training data were rescaled using the image data generator

  3. Training data was preprocessed to grayscale

  4. The model structure is created

  5. The model is trained (Took around an hour on an i7 10th Gen, RTX 2060, and 16GB RAM)

  6. The model structure is saved in the .json file

  7. The trained model weight is saved in the .h5 file


### Steps to test the model

  1. All necessary packages are imported

  2. Load the .json file and create the model

  3. Load weights into the new model

  4. Start the webcam feed or pass the video path

  5. Draw a box around the identified face

  6. Preprocess each face detected

  7. Predict and display the emotion


### Model Evaluation


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/640c2eeb-3475-45a9-829c-b09a21b89364)
###### _Fig 2.3 - Confusion Matrix of model_

◦  The model correctly classified 116 images for the emotion state anger (accuracy: 12.11%)

◦ The model correctly classified 1 image for the emotion state disgust (accuracy: 0.90%) as shown with white color

◦ The model correctly classified 121 images for the emotion state fear (accuracy: 11.82%)

◦ The model correctly classified 448 images for the emotion state happy (accuracy: 25.25%) as shown with the darkest blue color

◦ The model correctly classified 253 images for the emotion state sad (accuracy: 20.52%)

◦ The model correctly classified 212 images for the emotion state surprise (accuracy: 17%)

◦ The model correctly classified 81 images for the emotion state neutral (accuracy: 9.75%)


#### Model Analysis for edge cases:

In 233 instances, the model predicted that the subjects were happy when they were actually Angry. On the other hand, in 223 instances, the model predicted that the subjects were angry when they were actually happy. More training data needs to be included to classify anger versus happy states better.

In 81 instances, the model correctly predicted that the subjects were neutral compared to the ground truth. This combination is extremely low and more classifiers need to be tuned to identify a neutral state.

There are 1,774 images in the happy training class, of that 448 times the model correctly predicted the emotion with an accuracy of 25.25%.

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/86d002be-3078-41d6-ba97-a002fc3a6d5a)


###### _Fig 2.4 - Analysis of confusion matrix table_


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/30be22b3-9657-4c58-915d-27ff32041b36)

###### _Fig 2.5 - Classification report of model_

The accuracy of the overall model is seen to be 17%. Although its accuracy is low, with better datasets the accuracy should improve. With a multi-modal model which captures specific scenarios such as reading emotion through eyes alone[19], lip and cheek movements[20], and eyebrow postitioning[20]. 

#### Analysis of f-1 score
f-1 score takes both precision and recall into account, which also means it accounts for both false positives(FP) and false negatives(FN) The higher the precision and recall, the higher the f1-score. f1 score ranges between 0 and 1. The closer it is to 1, the better the model[21]. 

In the fear class, precision and recall differ by 0.02, this is because of the low sample rate. In all other states, precision, and recall are close to each other. f-1 score is highest in the happy category.


## VI. Experimental Results

The following experiments were conducted on the model to evaluate its performance under varying circumstances. 


#### Optimal Conditions

Optimal lighting conditions were used and there were no additional accessories to face. The model was able to detect faces and sufficiently classified the emotion.

![regular](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/347eb2e7-7db4-4dc8-8bb3-5d3f5ac8a847)

#### Sunglasses

Optimal lighting conditions were used and large, dark sunglasses were worn. The model reliably detected happy, sad, and neutral emotions while it was not reliable in the detection of other emotions. The box would sometimes be drawn twice often detecting two faces when there was only one but would flicker hence screenshots could not be taken.

![sunglass](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e0bbd0ce-cac9-45ad-b085-307183008b5a)



#### Surgical Mask

Optimal lighting conditions were used and a black surgical mask was worn. When the mask was worn the model could not detect the face and even when the chin was covered the model was no longer able to detect the face.

![mask](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e0307cc4-ce02-44fa-a8a8-1e3bd0acdf40)



#### Cap

Optimal lighting conditions were used but the cap covered the hair. The model was able to detect the face and emotion reliably. The happy face seemed to be detected easier with a cap on.

![cap](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e4457a35-dcb7-456a-a16f-8d635aea9050)


#### Non-optimal lighting conditions

When there was a strong backlight, the model was not able to identify any faces in the frame.


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/fb2f6bae-3efc-4119-8988-1c723fe00f7a)


#### Hair near eyebrows

Optimal lighting conditions were used but hair was near the eyebrows. The model was not reliably detecting the face when hair was near the eyebrows. Once lifted or parted, the model detected the face. This is due to eyebrow shape being a critical aspect of facial recognition.

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/17a85fd4-3e5f-404f-a2f0-d709af7d1a68)



## VIII. Threats to Validity

  ◦ Data Quality: Data is extremely important for model accuracy. If data is biased, mislabeled, or incomplete, the models' accuracy will be affected

  ◦ Biased Training Data: If data is biased towards certain demographics, the model may not perform well for users from different ethnicities, ages, or cultural backgrounds

  ◦ Environmental Variability: Subjects must have an acceptable camera quality, a well-lit environment, and a suitable background otherwise the model may not perform as well.

  ◦ Overfitting: The model may perform well on training data, but face challenges in real-life scenarios

  ◦ Limited Expressions: Training data may not include specific emotions or culturally specific emotions

  ◦ Context Dependency: The model may underperform when exposed to different and uncontrolled environments

  ◦ Cultural Differences: Emotion expression can vary significantly across different cultures, and a model trained on data from one culture may not be effective for individuals from other cultural backgrounds.

  ◦ Limited Labeling Accuracy: Emotion labels provided may not always accurately represent the true emotional state of the subjects.

(OpenAI's ChatGPT, private communication, 31 July 2023).


## IX. Conclusion

The prototype evaluated in this paper used CNN and Cascade Classifier to detect the emotions of subjects in real-time videos. The model accuracy is only 17% but with more research in the field, better datasets, and multi-modality, it is believed that the model accuracy can drastically improve. The model is sensitive to lighting conditions and only detects the face if all key features(eyebrows, nose, lips, and chin) are being identified. Creating a model for emotional pain detection is more difficult due to various emotions and the lack of widely accepted pain scales [22]. For example, one person may express more pain whereas another may not express as much pain on their face. Or gender and culturally different emotions may be expressed[23]. 

The idea of detecting emotions and pain in patients is feasible and can be implemented into virtual consultations and aid in the diagnosis of diseases. However, the model needs to include detection of the degree of pain in patients to aid doctors effectively. The model would have to be trained on synthetic data keeping in mind all previously mentioned factors. 

## X. Future Work

  ◦ Create synthetic data for pain detection

  ◦ Add more images to the dataset for better accuracies

  ◦ Explore additional methods of emotion and pain detection to see if they can be implemented

  ◦ Find pain images and data from various demographics and ethnicities 

  ◦ Test the current model on pain data

  ◦ Extend the analysis to near real-time video sessions (Facetime, Google Meet)

  ◦ Can this tie to the training of professionals using emotion detection in links with augmented reality?

  ◦ Include audio in the future - transition into audio to add to the algorithm


## XI. Ethical Implications and Recommendations

  ◦ Patient has not agreed to be on camera or recorded: Signed consent forms need to be given before the consultation.

  ◦ Can doctors rely on the model too much? Doctors may blame the model in an event of an inaccurate diagnosis. The model simply aids the doctor but cannot be fully relied on. 

  ◦ Data privacy issues: Data should be encrypted to avoid being seen by others

  ◦ Is there a chance of ghost observers at either end of the conference? Ghost observers are people not seen in the meeting but observing from a side angle where they cannot be seen by a camera.

## XII. Conflict of Intrest

The author declares there is no conflict of Intrest.


## XIII. Acknowledgements

Mentor: Professor Janyl Jumadinova- Thought basics of ML and helped with any questions that I had for her. Giving feedback and guidance for the next steps, she was an integral part of the paper.

Naveen Yeri and Meenakshi Yeri- Gave tips along the way and provoked my imagination.

Thejas Bhat- Assisted in running the prototype. He helped immensely with implementing the prototype and any code-related work.

Emotion_Detection_with_CNN[13] by Sunny Kusawa

FER-2013 Dataset from Kaggle[20]

## References

[1]  P. Werner, A. Al-Hamadi, R. Niese, S. Walter, S. Gruss, and H. C. Traue, “Automatic pain recognition from video and biomedical signals,” in Proceedings of 2014 22nd International Conference on Pattern Recognition (ICPR), pp. 4582–4587, IEEE, Stockholm, Sweden, August 2014.

[2] R. Kharghanian, A. Peiravi, and F. Moradi, “Pain detection from facial images using unsupervised feature learning approach,” in Proceedings of 2016 38th Annual International Journal of Healthcare Engineering 21 Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 419–422, IEEE, Orlando, FL, USA, August 2016.

[3] A. B. Ashraf, S. Lucey, J. F. Cohn et al., “)e painful face–pain expression recognition using active appearance models,” Image and Vision Computing, vol. 27, no. 12, pp. 1788–1796, 2009.

[4] Ekman, Paul. "Universals and cultural differences in facial expressions of emotion." Nebraska symposium on motivation. University of Nebraska Press, 1971.

[5] “Medical doctors (per 10 000 population).” World Health Organization. https://www.who.int/data/gho/data/indicators/indicator-details/GHO/medical-doctors-(per-10-000-population) (accessed: Jul. 31, 2023).

[6] Samolsky Dekel, Boaz Gedaliahu, et al. "Medical evidence influence on inpatients and nurses pain ratings agreement." Pain Research and Management 2016 (2016).

[7] F. Alonso-Martín, M. Malfaz, J. Sequeira, J. Gorostiza, and M. Salichs, “A Multimodal Emotion Detection System during Human–Robot Interaction,” Sensors, vol. 13, no. 11, pp. 15549–15581, Nov. 2013, doi: 10.3390/s131115549.

[8] A. Altameem, A. Kumar, R. C. Poonia, S. Kumar and A. K. J. Saudagar, "Early Identification and Detection of Driver Drowsiness by Hybrid Machine Learning," in IEEE Access, vol. 9, pp. 162805-162819, 2021, doi: 10.1109/ACCESS.2021.3131601.

[9] M. S. Bartlett, G. C. Littlewort, M. G. Frank, and K. Lee,“Automatic decoding of facial movements reveals deceptivepain expressions,” Current Biology, vol. 24, no. 7, pp. 738–743, 2014.

[10] S. Ouellet, “Real-time emotion recognition for gaming using deep convolutional network features,” CoRR, vol. abs/1408.3750, 2014.

[11] Gkikas, Stefanos, and Manolis Tsiknakis. "Automatic assessment of pain based on deep learning methods: A systematic review." Computer methods and programs in biomedicine 231 (2023): 107365.

[12] “FER-2013 | Kaggle.” Kaggle. https://www.kaggle.com/datasets/msambare/fer2013 (accessed: Jul. 31, 2023).

[13] Root, A A, and J A Stephens. “Organization of the central control of muscles of facial expression in man.” The Journal of physiology vol. 549,Pt 1 (2003): 289-98. doi:10.1113/jphysiol.2002.035691

[14] “datamagic2020/Emotion_detection_with_CNN - GitHub.” GitHub. https://github.com/datamagic2020/Emotion_detection_with_CNN (accessed: Jul. 31, 2023).

[15] “anishjohnson/Face-Emotion-Recognition: This project is a .. - GitHub.” Medium. https://github.com/anishjohnson/Face-Emotion-Recognition (accessed: Aug. 01, 2023).

[16] Bengio, Yoshua. "Learning deep architectures for AI." Foundations and trends® in Machine Learning 2.1 (2009): 1-127.

[117] Brownlee, Jason. "Deep learning with Python: develop deep learning models on Theano and TensorFlow using Keras." Machine Learning Mastery, 2016.

[18] “Google Trends.” Google Trends. https://trends.google.com/trends/ (accessed: Aug. 01, 2023).

[19] J. Z. Lim, J. Mountstephens, and J. Teo, “Emotion Recognition Using Eye-Tracking: Taxonomy, Review and Current Challenges,” Sensors, vol. 20, no. 8, p. 2384, Apr. 2020, doi: 10.3390/s20082384.

[20] Kohler, Christian G., et al. "Differences in facial expressions of four universal emotions." Psychiatry research 128.3 (2004): 235-244.

[21] 

[22] Heiderich, Tatiany M., et al. "Face-based automatic pain assessment: challenges and perspectives in neonatal intensive care units." Jornal de Pediatria (2023).

[23] McClelland, Laura E., and James A. McCubbin. "Social influence and pain response in women and men." Journal of Behavioral Medicine 31 (2008): 413-420.
