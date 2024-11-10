# neural-network-challenge-1
### Background

You work at a company that specializes in student loan refinancing. If the company can predict whether a borrower will repay their loan, it can provide a more accurate interest rate for the borrower. Your team has asked you to create a model to predict student loan repayment.

The business team has given you a CSV file that contains information about previous student loan recipients. With your knowledge of machine learning and neural networks, you decide to use the features in the provided dataset to create a model that will predict the likelihood that an applicant will repay their student loans. The CSV file contains information about these students, such as their credit ranking.

### Files

Download the following files to help you get started:

[Module 18 Challenge filesLinks to an external site.](https://static.bc-edx.com/ai/ail-v-1-0/m18/lms/starter/M18_Starter_Code.zip)

### Before You Begin

Before starting the Challenge, be sure to complete the following steps:

-   Create a new repository for this project called  `neural-network-challenge-1`. Do not add this Challenge assignment to an existing repository.
    
-   Clone the new repository to your computer.
    
-   Inside your local Git repository, add the starter file  `student_loans_with_deep_learning.ipynb`  from your file downloads.
    
-   Push these changes to GitHub.
    
-   Upload  `student_loans_with_deep_learning.ipynb`  to Google Colab and work on your solution there.
    
    -   To track your version history, periodically download your file and push the changes to your repository.

----------

### Instructions

Open the starter file in Google Colab and complete the following steps, which are divided into four parts:

-   Prepare the data for use on a neural network model.
    
-   Compile and evaluate a model using a neural network.
    
-   Predict loan repayment success by using your neural network model.
    
-   Discuss creating a recommendation system for student loans.
    

#### Part 1: Prepare the data for use on a neural network model

Using your knowledge of Pandas and scikit-learn’s  `StandardScaler()`, preprocess the dataset so that you can use it to compile and evaluate the neural network model later.

Open the starter code file and complete the following data preparation steps:

1.  Read the data from  [https://static.bc-edx.com/ai/ail-v-1-0/m18/lms/datasets/student-loans.csvLinks to an external site.](https://static.bc-edx.com/ai/ail-v-1-0/m18/lms/datasets/student-loans.csv)  into a Pandas DataFrame. Review the DataFrame, looking for columns that could eventually define your features and target variables.
    
2.  Create the features (`X`) and target (`y`) datasets. The target dataset should be defined by the “credit_ranking” column. The remaining columns should define the features dataset.
    
3.  Split the features and target sets into training and testing datasets.
    
4.  Use scikit-learn's  `StandardScaler`  to scale the features data.
    

#### Part 2: Compile and Evaluate a Model Using a Neural Network

Use your knowledge of TensorFlow to design a deep neural network model. This model should use the dataset’s features to predict the credit quality of a student based on the features in the dataset. Consider the number of inputs before determining the number of layers that your model will contain or the number of neurons on each layer. Then, compile and fit your model. Finally, evaluate the model to calculate its loss and accuracy.

To do so, complete the following steps:

1.  Create a deep neural network by assigning the number of input features, the number of layers, and the number of neurons on each layer using TensorFlow’s Keras.
    
    **hint**
    
    You can start with a two-layer deep neural network model that uses the  `relu`  activation function for both layers.
    
2.  Compile and fit the model using the  `binary_crossentropy`  loss function, the  `adam`  optimizer, and the  `accuracy`  evaluation metric.
    
    **hint**
    
    When fitting the model, start with a small number of epochs, such as 50 or 100.
    
3.  Evaluate the model using the test data to determine the model’s loss and accuracy.
    
4.  Save and export your model to a keras file, and name the file  `student_loans.keras`.
    
    **note**
    
    Remember to download your saved model from Colab so you can upload it to your GitHub repo.
    

#### Part 3: Predict loan repayment success by using your neural network model

Use the model you saved in the previous section to make predictions on your reserved testing data.

To do so, complete the following steps:

1.  Reload your saved model.
    
2.  Make predictions on the testing data, saving them to a DataFrame and rounding the predictions to binary values.
    
3.  Generate a classification report with the predictions and testing data.
    

#### Part 4: Discuss creating a recommendation system for student loans

### **1. Describe the data that you would need to collect to build a recommendation system to recommend student loan options for students. Explain why this data would be relevant and appropriate.**
To build a robust recommendation system for student loan options, the features you provided are quite comprehensive. However, there are a few additional features that could enhance the effectiveness of the recommendations:

-  **Student Demographics**: Age, gender, and socioeconomic background can help tailor loan options to individual circumstances.
    
-  **Credit Score**: Including the student's credit score would help assess their eligibility for various loan options and interest rates.
    
-  **Income Information**: Details about the student's current income or expected future income would provide insight into their repayment capacity.
    
-  **Loan Preferences**: Data on the preferred loan amount, interest rate, repayment period, and type of loan (federal or private) can help match students with options that meet their specific needs.
    
- **User Interaction Data**: Information on how students interact with different loan options (e.g., viewed, saved, applied for) can provide insights into their preferences and behaviors.
    
-  **Feedback Data**: Ratings or reviews from students who have previously taken out loans can help gauge satisfaction and guide recommendations.
    

By adding these features, the recommendation system can provide more personalized and practical loan options tailored to each student's unique circumstances and preferences

### **2. Based on the data you chose to use in this recommendation system, would your model be using collaborative filtering, content-based filtering, or context-based filtering? Justify why the data you selected would be suitable for your choice of filtering method.**
**Justification**:

-   **Specificity**: Content-based filtering relies on the specific attributes of users and items (in this case, loan options) to make recommendations. The data collected is highly specific to each student and their financial and academic background, making it ideal for content-based filtering.
    
-   **Relevance**: The information about loan products (interest rates, repayment terms, eligibility criteria) is directly relevant to the student's unique profile and preferences, ensuring that recommendations are personalized.
    
-   **User-Centric**: This method focuses on understanding the individual user's needs and characteristics, which aligns well with the goal of providing tailored loan recommendations based on personal circumstances.
    

Overall, the data selected is suitable for content-based filtering as it is rich in attributes specific to each student and the loan products, enabling the recommendation system to make personalized and accurate loan suggestions.

### **3. Describe two real-world challenges that you would take into consideration while building a recommendation system for student loans. Explain why these challenges would be of concern for a student loan recommendation system.**
Building a recommendation system for student loans involves navigating a few significant real-world challenges. Here are two key challenges and their implications:

### 1. **Data Privacy and Security**:

**Concern**: Students' financial, academic, and personal information is highly sensitive. Ensuring that this data is kept secure and private is paramount.

-   **Reason**: The recommendation system would need to handle detailed and potentially sensitive information such as credit scores, income levels, and loan histories. Any data breach or misuse could lead to serious consequences, including identity theft, financial loss, and erosion of trust.
    
-   **Mitigation**: Implementing robust encryption methods, access controls, and compliance with data protection regulations (such as GDPR or CCPA) is essential. Regular security audits and the use of anonymized data where possible can also help protect student information.
    

### 2. **Bias and Fairness**:

**Concern**: Bias in the recommendation algorithm could lead to unfair treatment of certain student groups.

-   **Reason**: If the data used to train the model contains historical biases (e.g., demographic or socioeconomic biases), the recommendations could disproportionately favor or disadvantage certain groups of students. This could result in unequal access to loan options and potentially worsen existing inequalities.
    
-   **Mitigation**: It is crucial to regularly audit and test the recommendation system for bias. Using fairness-aware machine learning techniques and including diverse datasets can help ensure the system provides equitable recommendations. Transparency in the recommendation process and involving stakeholders in model development can also mitigate bias.
    

Addressing these challenges is vital to ensure that the recommendation system is not only effective but also ethical and trustworthy, providing fair and secure loan options to all students.
    

----------

### Hints and Considerations

-   Review previous modules if you need help with data preprocessing.
    
-   Make certain that your training and testing data are preprocessed in the same ways.
    

----------

### Requirements

To receive all points, your Jupyter Notebook file must have all of the following:

#### Prepare the Data for Use on a Neural Network Model (15 points)

-   Two datasets were created: a target (`y`) dataset, which includes the "credit_ranking" column, and a features (`X`) dataset, which includes the other columns. (5 points)
    
-   The features and target sets have been split into training and testing datasets. (5 points)
    
-   Scikit-learn's  `StandardScaler`  was used to scale the features data. (5 points)
    

#### Compile and Evaluate a Model Using a Neural Network (30 points)

-   A deep neural network was created with appropriate parameters. (10 points)
    
-   The model was compiled and fit using the  `accuracy`  loss function, the  `adam`  optimizer, the  `accuracy`  evaluation metric, and a small number of epochs, such as 50 or 100. (10 points)
    
-   The model was evaluated using the test data to determine its loss and accuracy. (5 points)
    
-   The model was saved and exported to a keras file named  `student_loans.keras`. (5 points)
    

#### Predict Loan Repayment Success by Using your Neural Network Model (25 points)

-   The saved model was reloaded. (5 points)
    
-   The reloaded model was used to make binary predictions on the testing data. (10 points)
    
-   A classification report is generated for the predictions and the testing data. (10 points)
    

#### Discuss creating a recommendation system for student loans (30 points)

**For Question 1:**

-   The response describes the data that should be collected to build a recommendation system for student loan options. (4 points)
    
-   The response explains why they think that data should be collected. (4 points)
    
-   The type of data described is appropriate for a recommendation system for student loan options. (2 points)
    

**For Question 2:**

-   The response chose a filtering method. (4 points)
    
-   The student justified the choice of their filtering method. (4 points)
    
-   The choice of filtering method was appropriate for the data selected in the previous question. (2 points)
    

**For Question 3:**

-   The response lists two real-world challenges with building a recommendation system for student loans. (4 points)
    
-   The response explains why these challenges would be of concern for a student loan recommendation system. (6 points)
    

----------

### Grading

This challenge will be evaluated against the requirements and assigned a grade according to the following table:


----------

### Submission

To submit your Challenge assignment, click Submit, and then provide the URL of your GitHub repository for grading.

**note**

You are allowed to miss up to two Challenge assignments and still earn your certificate. If you complete all Challenge assignments, your lowest two grades will be dropped. If you wish to skip this assignment, click Next, and move on to the next module.

Comments are disabled for graded submissions in Bootcamp Spot. If you have questions about your feedback, please notify your instructional staff or your Student Success Manager. If you would like to resubmit your work for an additional review, you can use the Resubmit Assignment button to upload new links. You may resubmit up to three times for a total of four submissions.

**important**

**It is your responsibility to include a note in the README section of your repo specifying code source and its location within your repo**. This applies if you have worked with a peer on an assignment, used code that you did not author or create, source code from a forum such as Stack Overflow, or received code outside curriculum content from support staff, such as an Instructor, TA, Tutor, or Learning Assistant. This will provide visibility to grading staff of your circumstance in order to avoid flagging your work as plagiarized.

If you are struggling with a Challenge or any aspect of the curriculum, please remember that there are student support services available to you:

1.  Office hours facilitated by your TA(s)
    
2.  [Tutoring GuidelinesLinks to an external site.](https://docs.google.com/document/d/1hTldEfWhX21B_Vz9ZentkPeziu4pPfnwiZbwQB27E90/edit?usp=sharing)  (schedule a session in the "Tutor Sessions" section of Bootcampspot)
    
3.  Ask the class Slack channel/get peer support
    
4.  AskBCS Learning Assistants
    

### Reference

Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only. Slack channel/get peer support

AskBCS Learning Assistants

Reference
Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.