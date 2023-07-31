# LS 102 - Computer Science Research Paper

## Title

Prachetas Yeri

---
## I. Abstract
There are seven types of human emotions shown to be universally recognizable across
different cultures [2]: anger, disgust, fear, happiness, sadness, surprise, contempt. 


## II. Motivation
During the COVID-19 pandemic, my grandpa suffered from Alzheimer's and Leukemia. As was in a weakened state of health, Coronavirus exposure would have been undesirable. Wondering if we could engage in online consultations with his doctors. Although possible, I quickly understood that online sessions would not be an adequate method compared to face-to-face interactions. I speculated ways in which online consultation between doctors and patients could be improved to help in the diagnosis of diseases and be more effective. If online consultations were more reliable, here are a few ways the public would benefit:

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

The dataset used for the prototype used in this paper is "fer2013" which contains 35,887 images of various classes (0=Angry, 1=Disgust, 2=Fear, 3=Happy, 4=Sad, 5=Surprise, 6=Neutral). The dataset used in the model was downloaded from Kaggle. The dataset consists of 48x48 grayscale images of unique faces. Each face is approximately centered and is the same size in the image to avoid training mismatches. In the current prototype, an 80% (28,709 images) for training data and 20% (7,117 images) for testing data split was used. Below are examples of the dataset and some key feautres identified for each class.




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


Emotion detection using computer vision has attracted significant attention to programmers over the past few years. Many have used different models or methods to create an emotion detection program that analyses images and outputs the emotion predicted by the model. Initially a code from github was found and tesed on. The model was for detecting emotion in images which would not be feasible for this application. In a virtual consultation between medical practitioners and patients, the model should be able to detect emotion using real time video which would allow for live feed being available for the doctor.


![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/816365ca-4158-46b7-9120-0a14746f7877)

###### _Fig 2.0 - All packages used in this prototype_

The prototype uses pythons Keras, Tensorflow and Cascade Classifier to predict emotions in real time videos. Keras is an open-source library that provides a Python interface for artificial neural networks(ANN) and Deep Learning(DL). ANN is inspired bt the structure of neurons in the human brain[8]. It was developed to make deep learning models as quickly and as easily as possible. Keras runs on Python 2.7 or 3.6 and on TensorFlow[9].

Tensorflow is another open source library for fast numerical computing. It was created and is maintained my Google. It can run on single CPU systems, GPUs and mobiles[9]. Tensorflow is used to build artificial intelligence(AI) and Machine learning(ML) algorithms. 

![image](https://github.com/LS102-summer2023/project-prachetasyeri/assets/136471736/5fbf1acc-de0e-4446-9905-03e41e4795b9)

###### _Fig 2.1 - Shows the interest of Tensorflow over the last five years according to Google Trends_


Videos are nothing but a series of static images. In emotion detection of real-time videos these static images are analyzed and the emotion predicted is displayed on the module.Cascade Classifier was used identify faces and classify them into  their emotion classes.

### Steps to train the model

  1.  All necessary packages are imported

 

  2. All training data was rescaled using image data generator

  

  3. Training data was preproccessed to grayscale



  4. Model structure is created



  5. Model is trained (Took around an hour on an i7 10th Gen, RTX 2060 and 16GB RAM)



  6. Moddel structure is saved in the .json file



  7. Trained model weight is saved in the .h5 file



### Steps to train the model

  1.  All necessary packages are imported




  2. Load .json file and create model



  3. Load weights into new model




  4. Start webcam feed or pass the video path




  5. Draw a box around the identified face

    


  6. Preprocess each face detected

  


  7. Predict and display the emotion




## VI. Results

## VII. Evaluation

## VIII. Threats to Validity


## IX. Conclusion






## X. Future Work



## XI. Ethical Implications and Recommendations


## XII. Conflict of Intrest

The author declares there is no conflict of Intrest.




## XIII. Aknowledgements
Professor Janyl Jumadinova- Allegheny University Professor of Computer Science


Naveen Yeri


Meenakshi Yeri


Thejas Bhat

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
