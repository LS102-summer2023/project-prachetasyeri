# LS 102 - Computer Science Research Paper Outline

## Name

Prachetas Yeri

### Research Project Details

* What is the focus of your research project?

Build, design and implement a prototype using computer vision and machine learning to help doctors understand patients emotions, and degree of pain to aid in diagnosis of diseases in a virtual consultation.

* State at least one research question that your project will answer.

Can facial expressions be analyzed to draw out emotions to aid in better diagnosis in virtual consultation sessions between medical caregivers and patients?


* What are the steps you will need to take to complete this project?

PHASE 1:

- Finalize tools and datasets required for the project (Google Colab, python, image dataset, faker.ai, compencv)
- Conduct exploratory data analysis(Dependent, independent, missing data, outliers data inconsisencies)
- Establish emotion indices on face images from the internet
- Write code to arrive at approximate emotion states(happy, sad, angry, pained, neutral, etc.)
- Correlate emotions states with pain index
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
     - During covid times, my grandpa was admitted into the hospital and would not be treated fully until his covid test came back negative. 
     - Made me wonder if his treatment could be done online and diagnosis of the disease could aid in better medical care
     - This could also help people financially challenged, being able to talk to a doctor virtually for less money
     - During covid times we didnt want to take my grandpa to the hospital frequently to reduce risk of being exposed to COVID-19
     - Helps conectivity between a doctor patient (primary doctor/doctor the patient is used to)
     - Increases the availability of doctors so the ratio of doctors to patients increasesmny
     - mny adds ! increases availability of medcal services , especially for rural patients

     + Current State of the Art 
     - Till now emotion detection has been used in several other fields
     - One paper talks about emotion recognition and facial detection to identify sleepy drivers
     - Emotion detection has been used to identify crime or fraud
     - Emotion detection in robotics (human robot interaction)
     - Can this be used in virtual medical diagnosis?
     - Pain detection in indentifying urgency state of the patient in an emergency room.

     + Goals of the Project 
     - To see if emotion detection is feasible in order to aid in diagnosis of patients in a virtual interaction
     - If this aids in diagnosis can the accessibility of doctors increase? 
     - Scale up virtual diganosis in medical fields

* Related work 
     - Talk about other researchers and their acomplishments in this field
     - Analyze the knowledge gap between the related papers and my paper

* Method 
     - Mention and explain algorithms used in the model
     - Include the code
     - Show screenshots of the model detecting images
     - Show progression from emotion detection of single images to real time videos
     - Show accuracy and precision and other metrics of the model
     - Plot accuracy and precision of the model as visual data and explain any corelations +

* Experiments
     + Assumptions
     - Patients have decent to good internet connection for the algorithm to run
     - Patients have a working camera
     - Appropriate level of luminosity is available 

     + Modeling Methadology 
     - Explain OpenCV
     - Discuss Tkinter/MediaPipe
     - Dataset observations
     - Other ML algorithms

     + Evaluation
     - Record accuracy, lag, recall speed and other factors
     - Explore if this is a feasible method

     + Threats to Validity
     - Skin color
     - Specific features
     - Relatively different expression of emotions
     - Accessories worn
     - Religion based attire

* Conclusion

     + Summary of Results
     - Sum up key factors
     - Finally answer the research question. Can emotion detection be used for this application?

     + Future Work
     - Extend the analysis to near real time video sessions (Facetime, Google Meet)
     - Can this tie to training of proffessionals using emotion detection in links with augmented reality?

     + Ethical Implications and Recommendations
          - Patient has not given permission to be on camera/ recorded (HIPA rules)
          - Can doctor rely on the model too much
          - Can ML algorithm read into very minor changes in body language
          - Should camera be running at all times during the video conference. 
          - Data privacies

     + Conclusions
          - Summary of research findings.
     + References
          - 5 articles identified in previous assignment
          - Other research papers found (RefWorks to create bibliography)

---

(Did you remember to write your name at the top of this document?)
