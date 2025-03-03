Machine Learning-Based Test Failure Prediction Using Multinomial Naïve Bayes

Overview

This project demonstrates how to leverage the Multinomial Naïve Bayes machine learning algorithm to perform real-time sentiment analysis and failure prediction for test cases across any test framework.

For this implementation, I used the MS VSTest framework, where test results are stored in XML format. However, the code can be modified to parse other XML files for different test frameworks.


Project Structure

TRX_Merger

TRX_Merger is a command-line tool that merges multiple TRX files into a single TRX file containing all relevant test execution data. Additionally, it generates an HTML report for easier analysis.
This component is based on the open-source GitHub repository: trx-merger.

TRX_Parser

TRX_Parser contains the SQL database scripts required to implement real-time AI-based failure prediction.The ML_model.sql file (located under the MachineLearning folder) contains stored procedures for training and storing the Naïve Bayes model 
in the database.The trained model is used to predict test failures in real time based on historical test data.

TRX_Parser_Sourcecode

This folder includes the source code for parsing TRX files, extracting test results, and using the ML_model stored procedure to generate failure predictions.Predictions are stored in a results table and displayed via a UI for users.

CI/CD Pipeline Integration

The Sampleenvdeployment.groovy file provides an example Jenkins pipeline for integrating this workflow into CI/CD, enabling automated test failure predictions as part of your deployment process.

Getting Started

Set up the database using the scripts in TRX_Parser/ML_model.sql.
Run the TRX_Parser tool to extract test case results from TRX files and store them in the database.
Train the Naïve Bayes model using historical test data.
Use the stored procedures to generate real-time predictions for test case failures.
Integrate with Jenkins to automate predictions in CI/CD pipelines.


Contributions

Feel free to contribute by improving the model, adding support for more test frameworks, or enhancing the integration with other CI/CD tools.


 
