# LS 102 - Computer Science Research Paper

## Title

Prachetas Yeri

---
## I. Abstract

Currently, the assessment of pain is carried out by means of self-report, external observations, or physiological tests[15]. Though not all patients are able to express their experience of pain, such aspatients in a coma or neonates[16]. Patients may express several emotions that are not identitfied by humans which can be done by nonhuman observers, potentially aiding in diagnosis of diasease[17]. There are seven types of human emotions shown to be universally recognizable across different cultures [14]: anger, disgust, fear, happiness, sadness, surprise, contempt. In recent years, the field of emotion detection has been prevelant. Using Machine Learning(ML) algorithms, emotions are being able to be detected from real-time videos. This paper analyzes a unimodal prototype which uses Convolutional Neural Networks(CNN)- a deep learning techniqueto detect emotion in patients during a virtual consultation. This strives to help medical practitioners understand their patients emotions which could help in their diagnosis of disease. Aditionally, Python libraries such as Keras, Tenosorflow in building of the prototype and used Cascade Classifier. The present study aims to see if these implementations of Computer vision(CV) in virtual consultations between doctors and patients is feasible and improves medical care.


## II. Motivation
During the COVID-19 pandemic, my grandpa suffered from Alzheimer's and Leukemia. As he was in a weakened state of health, Coronavirus exposure would have been undesirable to his health. Wondering if we could engage in online consultations with his doctors. Although possible, online sessions would not be an adequate method compared to face-to-face interactions. Speculating ways in which online consultation between doctors and patients could be improved to help in the diagnosis of diseases and be more effective. If online consultations were more reliable, here are a few ways the public would benefit:

1. Patients may have a primary doctor whom they see regularly and such a doctor would be familiar with their medical history. In these cases, the patient would be able to consult their preferred doctor over the Internet and have a just as effective consultation.

2. Accessibility of medical services would be increased and would benefit patients without easy access to good medical services. They would be able to reach a qualified doctor and get treated remotely.

3. Patients would be able to get multiple opinions from doctors with completely different perspectives. This could include doctors from different backgrounds, qualifications, and doctors from different countries.

4. According to World Health Organization(WHO) as of 2020, there were 53.52 physicians per 100,000 people in the Austria whereas in Chad there were only 0.6 physicians per 100,000 people. If online consultations are feasible, the ratio of physicians to patients would be drastically increased improving the medical state of the world.


## III. Review of Literature

  Research on emotion detection mainly emcompassed of static images and text. Only recently emotion detection has been researched with respect real-time video and can be implemented in several fields. Fernando Alonso-Martin et al. have used a multimodal user-emotion detection system for social robots. Using emotion detection information from the user, the interaction beeween the robot and user makes its way towards a more probable interaction and allows the robot the dialog to adapt. Additionally they have used emotions to understand the degree of confidence projected by the user[1]. 

  
  Furthermore, Ayman Altameem et al. has researched using a Support Vector Machine(SVM) model which was connected to the vehicles electronics to detect if the driver is drowsy, angered or there is any sudden change in emotion. This allows the model to identify if they are driving safely and if not, alerts the driver and slows the car down. The algorithm was tested with several different parameters including different levels of light intenisty and various distances between the camera and subject[2]. Bartlett et al. analysed the use of computer vision (CV) and pattern regognition to understand if computers could distinguish between genuine and false pain expresssions. THe researches experimented on videos of genuine pain versus those of false pain. Computer Expression Regognition Tool box(CERT) analyzed the videos and showed significant improvements in accuracies of detecting false pain in comparison to human examine[3].

  
  In [4] Convolutional Neural Network(CNN) were used to examine real-time emotions from facial expressions. In the authors game, CNN was deployed to an input video stream to capture the users facial expression allowing them to control the game using their face. The facial changes detected would then be proccessed, decreasing quick facial variations and other noise. Gkikas et al. analyze different automatic methods to asses pain based on deep learning methods. They identified one hundred ten publications and sorted them by the number of channels and if the temporal dimension was used. The results showed several multimodal approaches for auomatic pain estimation and observed significant improvements when temporal exploitation of modalities was used. One method discussed in the paper was Vision based temporal exploitation which used CNN for the model. This paper analyses a prototype which also used CNN and deep learning.


  
  
Although, emotion detection has been researched upon in several other fields, can it be linked to degree of pain felt by patients and be conveyed to the physician so they can act accordingly?

## IV. Goals of the Project

The following are what the project entails and what is aimed to be analyzed or discussed.

   ◦ To corelate emotion and pain detection using CNN and deep learning models
  
   ◦ Understand if this method is feasible to aid in diagnosis of diseases in virtal consulations
  
   ◦ If it is feasible, can the quality and accessibility of medical services improve?
   
   ◦ Can computers and technology help scale up virtual diagnosis in medical fields?

## V. Methadology

### Exploratory Data Analysis

The dataset used for the prototype used in this paper is "fer2013"[12] which contains 35,887 images of various classes (0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral). The dataset used in the model was downloaded from Kaggle. The dataset consists of 48x48 grayscale images of unique faces. Each face is approximately centered and is the same size in the image to avoid training mismatches. In the current prototype, an 80% (28,709 images) for training data and 20% (7,117 images) for testing data split was used. Below are examples of the dataset and some key feautres identified for each class.




![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/f2fa6e3d-1953-451c-8b1c-ab1d7ff7cabe)

###### _Fig 1.0 - Sample of angry images from dataset_


   ##### __Observable features for anger include:__ 
      
      1. Eyebrows arched
      2. Eyes contracted
      3. Mouth frowned or bent
      4. Cheeks clinched
      5. Jaw projected


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/516ecbdd-df2c-4ab7-85a3-16b6c893f166)

###### _Fig 1.1 - Sample of disgusted images from dataset_


   ##### __Observable features for disgust include:__
      
      1. Eyebrows contracted
      2. Eyes squinted
      3. Mouth opened or bent to one side
      4. Cheeks dropped elongating the face
      5. Tension visible on forehead


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/978e6d4a-6a6d-43a9-9f0b-fb8716fc12e1)

###### _Fig 1.2 - Sample of fearful images from dataset_


   ##### __Observable features for fear include:__

      1. Frontalis(forehead) tentioned[5]
      2. Mentalis(midline above chin) stretched[5]
      3. Eyebrows thrusted upwards
      4. Eyes widened
      5. Mouth opened laterally or vertically
      6. At times hands touching the face


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/a8f0f490-4d7b-4a9b-af32-dbe78c585755)

###### _Fig 1.3 - Sample of happy images from dataset_


   ##### __Observable features for happiness include:__

      1. Orbicularis ocui (ourter cleft of the eye) contracted[5]
      2. Zygomaticus major(midpoint of a line between nose and ear lobe) raised[5]
      3. Eyebrows relaxed
      4. Eyes slightly closed
      5. Cheeks contracted (lifted up)
      6. Angle of mouth drawn upward and laterally
      7. Frontalis relaxed
      8. Nose slightly dialated
      9. In most cases, teeth are visible slightly


  ![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/f9650aae-7c32-4c42-ab59-5861c00dcc67)

   ###### _Fig 1.4 - Sample of sad images from dataset_


   ##### __Observable features for sadness include:__
      
      1. Corrugator(above medial aspect of left eyebrow) clenched[5]
      2. Depressor Anguli Oris(below left corner of mouth) pronouned[5]
      3. Eyebrows tentioned
      4. Eyes slightly closed
      5. Angle of mouth drawn downward (frown)
      6. Nose slightly dialated


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/c9918534-054b-4e4b-a5a3-3f94cd7a0b3c)

###### _Fig 1.5 - Sample of surprise images from dataset_


   ##### __Observable features for surprised include:__

      1. Eyebrows raised
      2. Eyes widened
      3. Jaw extended
      4. Mouth opened vertically
      4. Face elongated


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/71b25098-5843-43e4-a72c-f94d0f985970)

###### _Fig 1.6 - Sample of neutral images from dataset_


   ##### __Observable features for neutral include:__

      1. Orbicularis ocui relaxed
      2. Zygomaticus major relaxed
      3. Eyebrows relaxed
      4. Eyes neutral
      5. Cheeks rested
      6. Frontalis relaxed

### Prototype

__The model this paper analyzes and uses in Sunny Kusawa's Emotion_detection_with_CNN model[7] whcih uses CNN and deep learning in training the model.__

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/668baf35-312d-4d42-86c5-462326663394)

###### _Fig 2.0 - Diagramatic representation of a CNN_

Emotion detection using computer vision has attracted significant attention to programmers over the past few years. Many have used different models or methods to create an emotion detection program that analyses images and outputs the emotion predicted by the model. Initially a code from github was found and tesed on. The model was for detecting emotion in images which would not be feasible for this application. In a virtual consultation between medical practitioners and patients, the model should be able to detect emotion using real time video which would allow for live feed being available for the doctor.


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/816365ca-4158-46b7-9120-0a14746f7877)

###### _Fig 2.1 - All packages used in this prototype_

The prototype uses pythons Keras, Tensorflow and Cascade Classifier to predict emotions in real time videos. Keras is an open-source library that provides a Python interface for artificial neural networks(ANN) and Deep Learning(DL). ANN is inspired bt the structure of neurons in the human brain[8]. It was developed to make deep learning models as quickly and as easily as possible. Keras runs on Python 2.7 or 3.6 and on TensorFlow[9].

Tensorflow is another open source library for fast numerical computing. It was created and is maintained my Google. It can run on single CPU systems, GPUs and mobiles[9]. Tensorflow is used to build artificial intelligence(AI) and Machine learning(ML) algorithms. 

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/5fbf1acc-de0e-4446-9905-03e41e4795b9)

###### _Fig 2.2 - Shows the interest of Tensorflow over the last five years according to Google Trends_


Videos are nothing but a series of static images. In emotion detection of real-time videos these static images are analyzed and the emotion predicted is displayed on the module.Cascade Classifier was used identify faces and classify them into  their emotion classes.

### Steps to train the model

  1.  All necessary packages are imported

 

  2. All training data was rescaled using image data generator

  

  3. Training data was preproccessed to grayscale



  4. Model structure is created



  5. Model is trained (Took around an hour on an i7 10th Gen, RTX 2060 and 16GB RAM)



  6. Moddel structure is saved in the .json file



  7. Trained model weight is saved in the .h5 file



### Steps to test the model

  1.  All necessary packages are imported




  2. Load .json file and create model



  3. Load weights into new model




  4. Start webcam feed or pass the video path




  5. Draw a box around the identified face

    


  6. Preprocess each face detected

  


  7. Predict and display the emotion



### Model Evaluation


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/640c2eeb-3475-45a9-829c-b09a21b89364)
###### _Fig 2.3 - Confusion Matrix of model_


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e320b593-e742-4cb3-b5a0-7fed22d52219)


###### _Fig 2.4 - Analysis of confusion matrix table_

Based on the analysis of the confusion matrix the model is accurate 25.25% of the times in predicting happy emotion and 20.52% of the times it accurately predicts a neutral face. The model is least accurate in predicting disgusted and surprised faces. To improve model accuracy, the model should be trained on more images for each class. 



![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/30be22b3-9657-4c58-915d-27ff32041b36)

###### _Fig 2.5 - Classification report of model_

The accuracy of the overall model is seen to be 17%. Although its accuracy is low, with better datasets the accuracy should improve. With a multi modal model which captures specific senarios such as reading emotion through eyes alone[10], rlip and cheek movements[11], eyebrow postitioning[11].



## VI. Experimental Results

The following experiments were conducted on the model to evaluate its performance under varying circumstances. 


#### Optimal Conditions

Optimal lighting conditions were used and there were no additional accesories to face. The model was clearly able to detect faces and sufficiently classified the emotion.

![regular](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/347eb2e7-7db4-4dc8-8bb3-5d3f5ac8a847)

#### Sunglasses

Optimal lighting conditions were used and large, dark sunglasses were worn. The model reliably detected happy, sad and neutral emotions while it was not reliably in detection of other emotions. The box would sometimes be drawn twice often detecting two faces when there were only one but would flicker hence screenshots could not be taken.

![sunglass](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e0bbd0ce-cac9-45ad-b085-307183008b5a)



#### Surgical Mask

Optimal lighting conditions were used and a black surgical mask was worn. When the mask was worn the model could not detect the face and even when the chin was covered the model was no longer able to detect the face.

![mask](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e0307cc4-ce02-44fa-a8a8-1e3bd0acdf40)



#### Cap

Optimal lighting conditions were used but cap covered the hair. The model was able to dectect the face and emotion reliably. Happy face seemed to be detected easier with a cap on.

![cap](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/e4457a35-dcb7-456a-a16f-8d635aea9050)


#### Non-optimal lighting conditions

When there was strong backlight, the model was not able to identify any faces in the frame.


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/fb2f6bae-3efc-4119-8988-1c723fe00f7a)


#### Hair near eyebrows

Optimal lighting conditions were used but hair was near the eyebrows. The model was not reliably detecting face when hair was near the eyebrows. Once lifted or parted, the model detected face. This is due to eyebrow shape being a critical aspect in facial recognition.

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/17a85fd4-3e5f-404f-a2f0-d709af7d1a68)



## VIII. Threats to Validity

  1. Data Quality: Data is extremely important for a model accuracy. If data is biased, mislabeled or incomplete, the models accuracy will be affected

  2. Biased Training Data: If data is biased towards certain demographics, the model may not perform well for users from different ethnicities, ages or cultural backgrounds

  3. Environmental Variability: Subjects must have an acceptable camera quality, well-lit environment and a suitable background otherwise the model may not perform as well.

  5. Overfitting: The model may perform well on training data, but face challenges in real-life senarios

  6. Limited Expressions: Training data may not include specific emotions or culturally specific emotions

  7. Context Dependency: Model may underperform when exposed to different and uncontrolled environments

  8. Cultural Differences: Emotion expression can vary significantly across different cultures, and a model trained on data from one culture may not be effective for individuals from other cultural backgrounds.

  9. Limited Labeling Accuracy: Emotion labels provided may not always accurately represent the true emotional state of the subjects.

(OpenAI's ChatGPT, private communication, 31 July 2023).


## IX. Conclusion

The prototype evaluated in this paper used CNN and Cascade Classifier to detect emotions of subjects in real-time videos. The model accuracy is only 17% but with more research in the field, better datasets, and multi-modalily, it is believed that the model accuracy can drastically improve. The model is sensitive to lighting conditions and only detects face is all key features(eyebrows, nose, lips and chin) are being identified. Creating a model for emotion pain detection is more difficult due to various emotions and lack of widely accepted pain scale. For example, one person may express more pain whereas another may not express as much pain on their face. Or gender and culurally different emotions may be expressed[13]. 

The idea of detection emotions and pain in patients is feasible and can be implemented into virtual consultations and aid in diagnosis of diseases. However, the model needs to include detection of the degree of pain in patients to aid doctors effectively. The model would have to be trained on synthetic data keeping in mind all previously mentioned factors. 


## X. Future Work

  ◦ Create synthetic data for pain detection

  ◦ Add more images to the dataset for better accuracies

  ◦ Explore additional methods of emotion and pain detection to see if it can be implemented

  ◦ Find pain images and data from various demographics and ethnicities 

  ◦ Test the current model on pain data

  ◦ Extend the analysis to near real-time video sessions (Facetime, Google Meet)

  ◦ Can this tie to the training of professionals using emotion detection in links with augmented reality?

  ◦ Include audio in the future - transition into audio to add to the algorithm


## XI. Ethical Implications and Recommendations

  ◦ Patient has not given permission to be on camera or recorded: Signed consent forms need to be given before the consultation.

  ◦ Can doctors rely on the model too much?: Doctors may blame the model in an event of an inacurate diagnosis. The model simply aids the doctor but cannot be fully relied on. 

  ◦ Data privacy issues: Data should be encrypted to avoid being seen by others

  ◦ Is there a chance of ghost observers on either end of the conference? Ghost observers are people not seen in the meeting but observing from a side angle where they cannot be seen by a camera.

## XII. Conflict of Intrest

The author declares there is no conflict of Intrest.


## XIII. Aknowledgements

Mentor: Professor Janyl Jumadinova- Thought basics of ML and helped in any questions that I had for her. Giving feedback and guidance for next steps, she was an integral part of the paper.

Naveen Yeri and Meenakshi Yeri- Gave tips along the way and provoked my imagination.

Thejas Bhat- Assisted in running of the prototype. He helped immensly with implementing the prototype and any code related work.

Emotion_Detection_with_CNN[7] by Sunny Kusawa

Kaggle Dataset[12]
## References
[1] F. Alonso-Martín, M. Malfaz, J. Sequeira, J. Gorostiza, and M. Salichs, “A Multimodal Emotion Detection System during Human–Robot Interaction,” Sensors, vol. 13, no. 11, pp. 15549–15581, Nov. 2013, doi: 10.3390/s131115549.

[2] A. Altameem, A. Kumar, R. C. Poonia, S. Kumar and A. K. J. Saudagar, "Early Identification and Detection of Driver Drowsiness by Hybrid Machine Learning," in IEEE Access, vol. 9, pp. 162805-162819, 2021, doi: 10.1109/ACCESS.2021.3131601.

[3] M. S. Bartlett, G. C. Littlewort, M. G. Frank, and K. Lee,“Automatic decoding of facial movements reveals deceptivepain expressions,” Current Biology, vol. 24, no. 7, pp. 738–743, 2014.

[4] S. Ouellet, “Real-time emotion recognition for gaming using deep convolutional network features,” CoRR, vol. abs/1408.3750, 2014.

[5] Root, A A, and J A Stephens. “Organization of the central control of muscles of facial expression in man.” The Journal of physiology vol. 549,Pt 1 (2003): 289-98. doi:10.1113/jphysiol.2002.035691

[6] Gkikas, Stefanos, and Manolis Tsiknakis. "Automatic assessment of pain based on deep learning methods: A systematic review." Computer methods and programs in biomedicine 231 (2023): 107365.

[7] https://github.com/datamagic2020/Emotion_detection_with_CNN

[8] Bengio, Yoshua. "Learning deep architectures for AI." Foundations and trends® in Machine Learning 2.1 (2009): 1-127.

[9] Brownlee, Jason. "Deep learning with Python: develop deep learning models on Theano and TensorFlow using Keras." Machine Learning Mastery, 2016.

[10] J. Z. Lim, J. Mountstephens, and J. Teo, “Emotion Recognition Using Eye-Tracking: Taxonomy, Review and Current Challenges,” Sensors, vol. 20, no. 8, p. 2384, Apr. 2020, doi: 10.3390/s20082384.

[11] Kohler, Christian G., et al. "Differences in facial expressions of four universal emotions." Psychiatry research 128.3 (2004): 235-244.

[12] https://www.kaggle.com/datasets/msambare/fer2013

[13] McClelland, Laura E., and James A. McCubbin. "Social influence and pain response in women and men." Journal of Behavioral Medicine 31 (2008): 413-420.

[14] Ekman, Paul. "Universals and cultural differences in facial expressions of emotion." Nebraska symposium on motivation. University of Nebraska Press, 1971.

[15]  P. Werner, A. Al-Hamadi, R. Niese, S. Walter, S. Gruss, and H. C. Traue, “Automatic pain recognition from video and biomedical signals,” in Proceedings of 2014 22nd International Conference on Pattern Recognition (ICPR), pp. 4582–4587, IEEE, Stockholm, Sweden, August 2014.

[16] R. Kharghanian, A. Peiravi, and F. Moradi, “Pain detection from facial images using unsupervised feature learning approach,” in Proceedings of 2016 38th Annual International Journal of Healthcare Engineering 21 Conference of the IEEE Engineering in Medicine and Biology Society (EMBC), pp. 419–422, IEEE, Orlando, FL, USA, August 2016.

[17] A. B. Ashraf, S. Lucey, J. F. Cohn et al., “)e painful face–pain expression recognition using active appearance models,” Image and Vision Computing, vol. 27, no. 12, pp. 1788–1796, 2009.
