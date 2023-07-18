# LS 102 - Computer Science Research Paper Outline

## Name

Prachetas Yeri

### Research Project Details

* What is the focus of your research project?

Build, design, and implement a prototype using computer vision and machine learning to help doctors understand patients' emotions and degree of pain to support diagnosis of diseases in a virtual consultation.

* State at least one research question that your project will answer.

Can facial expressions be analyzed to draw out emotions to aid in better diagnosis in virtual consultation sessions between medical caregivers and patients?


* What are the steps you will need to take to complete this project?

PHASE 1:

- Finalize tools and datasets required for the project (Google Colab, python, image dataset, fakerjs.dev, OpenCV, MediaPipe)
- Conduct exploratory data analysis(Dependent, independent, missing data, outliers data inconsistencies)
- Establish emotion indices on face images from the internet
- Write code to arrive at approximate emotion states(happy, sad, angry, pained, neutral, etc.)
- Correlate emotion states with pain index
- Validate model and analyze model performance (accuracy, precision, recall)

PHASE 2:
- Source Video data
- Convert video to threaded images
- Repeat phase 1 analysis on video (accuracy of model, precision, etc)

PHASE 3: 
- Display model performance as graphs or visual comparison
- Write the paper

---

### Outline

* Introduction 

     + Motivation 
          - During covid periods we didn't want to take my grandpa to the hospital frequently to reduce the risk of being exposed to COVID-19
          - Helps connectivity between a doctor and a patient (primary doctor/doctor the patient is used to)
          - Increases the availability of doctors so the ratio of doctors to patients increases
          - Increases availability of medical services, especially for patients from rural areas

     + Current State of the Art 
          - Till now, emotion detection has been used in several other fields
          - One paper talks about emotion recognition and facial detection to identify sleepy drivers
          - Emotion detection has been used to identify crime or fraud
          - Emotion detection in robotics (human-robot interaction)
          - Can this be used in virtual medical diagnosis?
          - Pain detection in identifying the state of urgency of the patient in an emergency room.

     + Goals of the Project 
          - To see if emotion detection is feasible to aid in the diagnosis of patients in a virtual interaction
          - If this helps in diagnosis of diseases, can the accessibility of doctors increase? 
          - Scale up virtual diagnosis in medical fields

* Related work 
          - Talk about other researchers and their accomplishments in this field
          - Analyze the knowledge gap between the related papers and my paper

* Method 
     - Mention and explain algorithms used in the model
     - Include model code and show how algorithms were implemented
     - Show screenshots of the model detecting emotion
     - Show progression from emotion detection of single images to real-time videos
     - Display accuracy, precision, and other metrics of the model
     - Plot accuracy and precision of the model as visual data and explain any correlations 

* Experiments
     + Assumptions
          - Patients have a working and manageable quality camera
          - Appropriate level of luminosity is available 

     + Modeling Methodology 
          - Explain OpenCV
          - Discuss Tkinter/MediaPipe
          - Dataset observations
          - Other ML algorithms

     + Evaluation
          - Record accuracy, lag, recall speed, and other factors
          - Explore if this is a feasible method

     + Threats to Validity
          - Skin color
          - Specific features
          - Relatively different expression of emotions
          - Accessories worn
          - Religion-based attire

* Conclusion

     + Summary of Results
          - Sum up key factors
          - Answer the research question. Can emotion detection be used for this application?

     + Future Work
          - Extend the analysis to near real-time video sessions (Facetime, Google Meet)
          - Can this tie to the training of professionals using emotion detection in links with augmented reality?
          - Include audio in the future - transition into audio to add to the algorithm

     + Ethical Implications and Recommendations
          - Patient has not given permission to be on camera/ recorded (HIPA rules)
          - Can doctors rely on the model too much?
          - Do the ML algorithms read into minor changes in body language?
          - Should the camera be running at all times during the video conference? 
          - Data privacy issues 

     + Conclusions
          - Summary of research findings.
     + References
          [1] A. I. Siam, N. F. Soliman, A. D. Algarni, F. E. Abd El-Samie, and A. Sedik, “Deploying Machine Learning Techniques for Human Emotion Detection,” vol. 2022, pp. 8032673–16, 2022, doi: 10.1155/2022/8032673.
          [2] P. Yellowlees, S. Richard Chan, and M. Burke Parish, “The hybrid doctor-patient relationship in the age of technology - Telepsychiatry consultations and the use of virtual space,” vol. 27, no. 6, p. 476, 2015, doi: 10.3109/09540261.2015.1082987.
          [3] N. Shah, A. Thakrar, S. Visvanathan, and S. Thamban, “Virtual online consultation platforms for secondary care: a review of the options,” vol. 7, no. 1, pp. 135–140, Jan. 2021, doi: 10.1136/bmjinnov-2020-000470.
          [4] P. Dutta and N. M, “Facial Pain Expression Recognition in Real-Time Videos,” vol. 2018, pp. 7961427–23, Jan. 2018, doi: 10.1155/2018/7961427.
          [5] Y. Jain, H. Gandhi, A. Burte and A. Vora, "Mental and Physical Health Management System Using ML, Computer Vision and IoT Sensor Network," 2020 4th International Conference on Electronics, Communication and Aerospace Technology (ICECA), Coimbatore, India, 2020, pp. 786-791, doi: 10.1109/ICECA49313.2020.9297447.
          
          
          
          - Other research papers found (RefWorks to create bibliography)

---

(Did you remember to write your name at the top of this document?)
