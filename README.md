# Mediaiplus Project
* This project from Mediaiplus Co., Ltd. demonstrates the process of collection of clinical data of South Korea's 46 upper general hospitals to support bio venture companies that are in prepartion for clinical trial. In this project, our data team collected profiles of all doctors in every department of a hospital with 7 differnt branches, including general information, specialty, degree, career, awards, Institute Activity, and the paper. 
* Because each hospital has about at least 200 doctors, we used bs4, requests, and re library in Python to collect and clean data. Then, we also used openpyxl library to insert all cleaned data in excel. 
* All of these data are used later to consolidate customized clinical data based information service platform for bio venture company.  

# Initial Step
* As mentioned above, our data team used bs4 and request library for web crawling to collect a vast amount of medical personnel's information. The main concern at the beginning was to come up with the idea of setting proper formation of features to store these data in Database. After a deep consideration, we decided to sequentially create features as hospital, major, name, specialty, department, degree, career, Institute activity, awards, and the paper, then include them as pickle format. pickle files do not store files in text form, but in binary files where necessary parts are stored in forms such as dictionary, list, and tuple. Text files can be parsed one by one and inserted into the DB faster because they are already made in a dictionary form without having to store them in the DB. It is a file saved in the same form as the **Figure 1**  below.
![image](https://user-images.githubusercontent.com/89524942/146409309-9ce5e798-1649-4729-a9bd-fd6ecb9ea70b.png)
(**Figure 1**. Keimyoung University Dongsan Hospital)

# Second Step 
* In the initial pipeline construction stage, our data team determined that it was more efficient to store it as an Excel than as a pickle file, so we changed the format one more time. I changed the code a little and saved each feature as an Excel file by using openpyxl library as shown in **Figure 2** below. I sequentially stored ID number, hospital, doctor's name, and major for general information and always desingated fixed ID number to differentiate other features to establish the format. 

![image](https://user-images.githubusercontent.com/89524942/146485174-c1b8ee29-3e40-4cf0-b233-ed9b52986fd2.png)

(**Figure 2**. Samsung University Hospital's general information)
 
 * **Figure 3** suggests that ID number is always fixed in the first column, so that it is convenient to search for doctor's profile accordingly. In case of degree, we can confirm information by categorizing the beginning year and the end year in second and third column, respectively. Besides degree, career, Institute activity, awards, and the paper can also be created as this structure. 

![image](https://user-images.githubusercontent.com/89524942/146485087-b3fba888-37da-4beb-b1e3-0999a4eb40f5.png)

(**Figure 3**. Samsung University Hospital's degree)

# Final Step 
* Like Samsung Seoul hospital, I created crawling program to store doctor's data of other hospitals in excel. Because each hospital has different HTML strctures, the code varies dependent upon the site's HTML tag and attributes. 
* As shown below in **Figure 4** and **Figure 5**, the algorithm may be similar but the code itself should be altered based on the site's HTML tag and attribute.  For example, the tag used in **Figure 4** for name differs from that of **Figure 5** and same applies for the department. Furthermore, we had to manually deal with some raw data that cannot be cleaned by the coding to store in excel. For example, Kyungbook University hospital has their doctor profiles with only single HTML table that consists of all branches, including name, department, degree, career, etc. in comparison to other university hospitals, such as Samsung and Incheon St.Mary that have multiple HTML tables corresponding to each branches. So, it was easier to extract data in Samsung and Incheon hospital rather than Kyungbook University hospital and store them into excel.

![image](https://user-images.githubusercontent.com/89524942/146640323-a45a02a7-97d8-4181-ba80-c603e0da46ea.png)

(**Figure 4**. Samsung University Hospital's degree)

![image](https://user-images.githubusercontent.com/89524942/146640498-05d4b8fa-196e-4774-a5b9-b537026b9c89.png)

(**Figure 5**. Incheon St.Mary Hospital )

# Conclusion 

* It took plenty of times to determine the final data format in a short period time, so our data team were able to store 16 out of total 46 upper general hospitals by using crawling program. Above are sample codes and excel files of datasets of Samsung University Hospital, Incheon St.Mary Hospital, and ChungAng University Hospital. Although it was a one month intern, I realized that it is most important to have meticulous work of preprocessing to obtain clean data, feeling that having a consolidated pipeline will later facilitate the future development and EDA before launching a serivce. 
