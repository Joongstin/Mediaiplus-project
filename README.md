# Mediaiplus Project
* This project from Mediaiplus Co., Ltd. demonstrates the process of collection of clinical data of South Korea's 46 upper general hospitals to support bio venture companies that are in prepartion for clinical trial. In this project, our data team collected profiles of all doctors in every department of a hospital with 7 differnt branches, including general information, specialty, degree, career, awards, Institute Activity, and the paper. 
* Because each hospital has about at least 200 doctors, we used bs4, requests, and re library in Python to collect and clean data. Then, we also used openpyxl library to insert all cleaned data in excel. 
* All of these data are used later to consolidate customized clinical data based information service platform for bio venture company.  

# Initial Step
* As mentioned above, our data team used bs4 and request library for web crawling to collect a vast amount of medical personnel's information. The main concern at the beginning was to come up with the idea of setting proper formation of features to store these data in Database. After a consideartion, we decided to sequentially create features as hospital, major, name, specialty, department, degree, career, Institute activity, awards, and the paper, then include them as pickle file format. pickle files do not store files in text form, but in binary files where necessary parts are stored in forms such as dictionary, list, and tuple. Text files can be parsed one by one and inserted into the DB faster because they are already made in a dictionary form without having to store them in the DB. It is a file saved in the same form as the **Figure 1**  below.
![image](https://user-images.githubusercontent.com/89524942/146409309-9ce5e798-1649-4729-a9bd-fd6ecb9ea70b.png)
(**Figure 1**. Keimyoung University Dongsan Hospital)

# Second Step 
* In the initial pipeline construction stage, our data team determined that it was more efficient to store it as an Excel than as a pickle file, so we changed the format one more time. I changed the code a little and saved each feature as an Excel file by using openpyxl library as shown in **Figure 2** below. I sequentially stored ID number, hospital, doctor's name, and major for general information and always desingate fixed ID number to differntiate other features to establish the format. 

![image](https://user-images.githubusercontent.com/89524942/146485174-c1b8ee29-3e40-4cf0-b233-ed9b52986fd2.png)

(**Figure 2**. Samsung University Hospital's general information)
 
 * **Figure 3** suggests that ID number is always fixed in the first column, so that it is convenient to search for doctor's profile accordingigly. In case of degree, we can confirm information by categorizing the beginning year and the end year in second and third column, respectively. Besides degree, career, Institute activity, awards, and the paper can also be created as this structure. 

![image](https://user-images.githubusercontent.com/89524942/146485087-b3fba888-37da-4beb-b1e3-0999a4eb40f5.png)

(**Figure 3**. Samsung University Hospital's degree)

# Final Step 
* Like Samsung Seoul hospital, I created crawling program to store doctor's data of other hospitals in excel. Because each hospital has differnt HTML strctures, the code varies dependent upon the site's HTML tag and attributes. 
* As shown below in **Figure 4** and **Figure 5**, the algorithm may be similar but the code itself should be altered based on the site's HTML tag and attribute. Furthermore, we had to manually deal with some unclean data that cannot be cleaned by the coding to store in excel. 

![image](https://user-images.githubusercontent.com/89524942/146636588-69c5e18f-378f-4169-b333-f21ff74dbbc6.png)

(**Figure 4**. Samsung University Hospital's degree)

![image](https://user-images.githubusercontent.com/89524942/146636598-51f729cb-8213-4a19-9ba6-0dc427273c3b.png)

(**Figure 5**. Incheon St.Mary Hospital )

