# task2
The Terry Stops project aims to address the need for improved efficiency and fairness in law enforcement actions, specifically during Terry stops, also known as "stop and frisk." A Terry stop refers to the temporary detention of an individual by a law enforcement officer based on reasonable suspicion of criminal activity. During this stop, an officer may also conduct a limited pat-down search if there is a reasonable suspicion that the person is armed and poses a threat.
To enhance the decision-making process during Terry stops, the project proposes the development of a predictive model. This model would assist officers in assessing the likelihood of an arrest being made during a Terry stop, helping them make informed and objective decisions. By leveraging data and analytics, law enforcement agencies can potentially reduce false arrests and instances of police misconduct, leading to more efficient and fair law enforcement practices.
Features

This dataset contains the following data:
•	Subject Age Group: Subject Age Group (10 year increments) as reported by the officer.
•	Subject ID: Key, generated daily, identifying unique subjects in the dataset using a character to character match of first name and last name. "Null" values indicate an "anonymous" or "unidentified" subject. Subjects of a Terry Stop are not required to present identification.
•	GO / SC Num: General Offense or Street Check number, relating the Terry Stop to the parent report. This field may have a one to many relationship in the data.
•	Terry Stop ID: Key identifying unique Terry Stop reports.
•	Stop Resolution: Resolution of the stop as reported by the officer.
•	Weapon Type: Type of weapon, if any, identified during a search or frisk of the subject. Indicates "None" if no weapons was found.
•	Officer ID: Key identifying unique officers in the dataset.
•	Officer YOB: Year of birth, as reported by the officer.
•	Officer Gender: Gender of the officer, as reported by the officer.
•	Officer Race: Race of the officer, as reported by the officer.
•	Subject Perceived Race: Perceived race of the subject, as reported by the officer.
•	Subject Perceived Gender: Perceived gender of the subject, as reported by the officer.
•	Reported Date: Date the report was filed in the Records Management System (RMS). Not necessarily the date the stop occurred but generally within 1 day.
•	Reported Time: Time the stop was reported in the Records Management System (RMS). Not the time the stop occurred but generally within 10 hours.
•	Initial Call Type: Initial classification of the call as assigned by 911.
•	Final Call Type: Final classification of the call as assigned by the primary officer closing the event.
•	Call Type: How the call was received by the communication center.
•	Officer Squad: Functional squad assignment (not budget) of the officer as reported by the Data Analytics Platform (DAP).
•	Arrest Flag: Indicator of whether a "physical arrest" was made, of the subject, during the Terry Stop. Does not necessarily reflect a report of an arrest in the Records Management System (RMS).
•	Frisk Flag: Indicator of whether a "frisk" was conducted, by the officer, of the subject, during the Terry Stop.
•	Precinct: Precinct of the address associated with the underlying Computer Aided Dispatch (CAD) event. Not necessarily where the Terry Stop occurred.
•	Sector: Sector of the address associated with the underlying Computer Aided Dispatch (CAD) event. Not necessarily where the Terry Stop occurred.
•	Beat: Beat of the address associated with the underlying Computer Aided Dispatch (CAD) event. Not necessarily where the Terry Stop occurred.
Main Objective

The objective of this project is to develop a classifier that can predict the outcome of a Terry Stop, specifically whether an arrest was made or not, based on the reasonable suspicion of criminal activity. By considering various factors and information available during the Terry Stop, such as the presence of weapons, time of day of the call, and other relevant details, the classifier aims to provide valuable insights to law enforcement officers.
Specific Objectives

•	Address data quality issues (missing values, inconsistent formats, outliers).
•	Develop a cleaning strategy (imputation, outlier detection, normalization).
•	Implement necessary transformation steps (feature engineering, aggregation).
•	Validate the cleaned and transformed dataset for integrity and usability.
Data Preparation
Loading the data
The data set was imported into a Jupyter notebook for processing. The data frame was displayed to visualize the data and to examine the relationships between the variables.
Cleaning data
The data was analyzed and cleaning was done by checking for duplicates and missing values.
Feature Engineering
Feature engineering is the process of creating new features or transforming existing features in a dataset to improve the performance of a machine learning model. It involves selecting, combining, or extracting relevant information from raw data to create informative and predictive features.
These are the steps that were taken:
•	Change Officer YOB to give the officer age
•	Update the Stop Resolution column to binary
•	Change the date column to datetime
•	Group weapons into firearms vs. non-firearms vs. no weapon
•	To categorize this time as either "daytime" or "nighttime"
•	Dropping unnecessary columns
•	Converting categorical data to numeric format through one hot encoding
Outlier Detection
Outlier detection refers to the process of identifying and handling data points that deviate significantly from the majority of the data. Outliers are observations that are unusual, rare, or inconsistent with the rest of the dataset. In this project, I opted to use the statistical technique known as the z-score. This method calculates the deviation of each data point from the mean or median and flags observations that fall beyond a certain threshold.

Data Visualization
26 to 35 year olds are stopped more than any other age group:

![image](https://github.com/IvyNjoroge/task2/assets/111203571/a6eed3e7-3169-4f74-9859-779778291e7e)

 
Most of the weapons found on motorists were non-firearms:
 
![image](https://github.com/IvyNjoroge/task2/assets/111203571/b9403038-23a5-4e2b-acae-e7bba9ffbe66)
