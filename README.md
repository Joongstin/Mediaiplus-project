# Mediaiplus Project
* This project from Mediaiplus Co., Ltd. demonstrates the process of collection of clinical data of South Korea's 46 upper general hospitals to support bio venture companies that are in prepartion for clinical trial. In this project, our data team collected profiles of all doctors in every department of a hospital with 7 differnt features, including general information, specialty, degree, career, awards, Institute Activity, and the paper. 
* Because each hospital has about at least 200 doctors, we used bs4, requests, and re library in Python to collect and clean data. Then, we also used openpyxl library to insert all cleaned data in excel. 
* All of these data are used later to consolidate customized clinical data based information service platform for bio venture company.  

# Initial Stage 
* As mentioned above, our data team used bs4 and request library for web crawling to collect a vast amount of medical personnel's information. The main concern at the beginning was to come up with the idea of setting proper formation of features to store these data in Database. After a consideartion, we decided to sequentially create features as hospital, major, name, specialty, department, degree, career, Institute activity, awards, and the paper, then include them as pickle file format. pickle files do not store files in text form, but in binary files where necessary parts are stored in forms such as dictionary, list, and tuple. Text files can be parsed one by one and inserted into the DB faster because they are already made in a dictionary form without having to store them in the DB. It is a file saved in the same form as the picture below.
![image](https://user-images.githubusercontent.com/89524942/146409309-9ce5e798-1649-4729-a9bd-fd6ecb9ea70b.png)

