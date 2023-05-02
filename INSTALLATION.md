# Solution Installation Guide

This document provides instructions on how to download the solution zip file and [install the solution](https://learn.microsoft.com/en-us/power-apps/maker/data-platform/import-update-export-solutions) to your Power Apps Platform environment.

## Import the solution to Power Apps environment

1. Browse to the Releases section of the Github repository.

![image](https://user-images.githubusercontent.com/25781258/235685266-1eeefabd-0cd1-4736-9d22-265ab4165fae.png)

2. Review the assets for the latest release and download the 'ReviewHub.zip' file.

![image](https://user-images.githubusercontent.com/25781258/235686162-7f7421cf-9a8f-44d0-88b5-10beeb2273fc.png)

3. Navigate to the solution page of your target power platform environment and select import solution.

![image](https://user-images.githubusercontent.com/25781258/235689796-a1954045-fa27-4221-a920-15c6cd510be0.png)

4. Select the downloaded zip file to import, then select next until you come across the connections section.

![image](https://user-images.githubusercontent.com/25781258/235691042-00c35c00-6f76-4571-be08-04a7394a199b.png)

![image](https://user-images.githubusercontent.com/25781258/235692103-b0df67d6-af23-47f8-998b-d6350733b9ef.png)

5. On the connections page you’ll be prompted to select the connections you want for each connection reference. If a connection does not already exist, create a new one. Once all connections have been created or selected appropriately, select import.

![image](https://user-images.githubusercontent.com/25781258/235693093-b4769fb3-d266-4ef2-9917-e8f47bd1330f.png)

6. After importing the popup closes and you should see a prompt showing the solution is importing.

![image](https://user-images.githubusercontent.com/25781258/235695301-3fc18de0-365a-4c06-8722-399837151866.png)

7. After your solution successfully imports you should select the solution and navigate to the environment variables section. Each environment variable contains a description of what value it expects and what it is used for.

![image](https://user-images.githubusercontent.com/25781258/235695927-f56a4016-9ae7-484e-a48f-511296893de7.png)

Below is a list of environment variables that will be required to start the solution. Others are still necessary when you want to utilize the solution in full.

   - EnvVar - ReviewHub - Developers: A list of developers emails separated by semi colon. Users within this list will be granted super user access to all aspects of the app. This should include your email.
   - EnvVar - ReviewHub - Read Only Access Group : The group id for the Azure Group utilized to provide access to user who only require read only access.
   - EnvVar - ReviewHub - Read Write Access Group: The group id for the Azure Group utilized to provide access to user who require read and write access. You can start of by creating a group and adding only yourself as the user if you don't have an existing groups that will serve this purpose.

The following list of environment variables are required for specific functions the solution provides and may result in errors when launching the ReviewHub App or accessing those functions they enable.

  - EnvVar - ReviewHub - Access Control Wiki : A link to a wiki on how the access to the application is managed.
  - EnvVar - ReviewHub - Admins: Admin emails separated by a semi colon ';', expected to receive the notifications when an access request is submitted.
  - EnvVar - ReviewHub - BlobStorageURL : The link to the blob storage which  stores the product images to be displayed within the app.
  - EnvVar - ReviewHub - Bulk Import Sharepoint File: Link to SharePoint excel file, which is used for bulk upload of Metrics.
  - EnvVar - ReviewHub - DevOps Base URL : The link to the Azure DevOps Project where all DevOps resources are created.
  - EnvVar - ReviewHub - DevOps QueryID: The query id for the Azure DevOps work items query for Feature Requests and Scorecard Onboarding.
  - EnvVar - ReviewHub - Environment ID : The id of the current environment the solution resides in.
  - EnvVar - ReviewHub - Feature Request Title : Text expected to be found within all project feature requests title, to help filter feature request from other work items within the DevOps Query.
  - EnvVar - ReviewHub - Feature Request URL : The link to a template work items for feature requests.
  - EnvVar - ReviewHub - Feedback URL : The link to the template bug work item for reporting bugs on the application.
  - EnvVar - ReviewHub - How To Video : A link to a video describing how to navigate the app. Microsoft Streams was utilized to host the video.
  - EnvVar - ReviewHub - Notification Email : An email that would be utilized as the sender of all outgoing emails within the solution.
  - EnvVar - ReviewHub - Scorecard Onboarding Request Title : Text expected to be found within all project scorecard onboarding requests title, to help filter scorecard onboarding request from other work items within the DevOps Query.
  - EnvVar - ReviewHub - Scorecard Onboarding Request URL : The link to a template work items for scorecard onboarding requests.
  - EnvVar - ReviewHub - Survey : An id to an internal survey form using form pro.
  - EnvVar - ReviewHub - Team Email : App team email, will be used as the reply to for all outgoing emails.
  - EnvVar - ReviewHub - Temporary Access Team Name : Team name for temporary access team, created in admin center and used to grant temproray read write access to users.
  - EnvVar - ReviewHub - Wiki : A link to application wiki. 


8. Clone the repository to your local machine 

```
git clone https://github.com/microsoft/review-hub.git
```

Or download the repo as a zip file and extract the downloaded zipped file.

![image](https://user-images.githubusercontent.com/25781258/235701116-e11647ea-e272-420f-89bc-8561b9a0b56c.png)


9. Navigate to the cloned or extracted repo folder. Then select the sharepoint-files folder, there you will find the Data Collection Example.xlsx and the factMetricsBulkUpload.xlsx. Move both of these to your sharepoint site if you wish to take advantage of the metric and metric values bulk upload features respectively.

![image](https://user-images.githubusercontent.com/25781258/235701792-3c5f09ad-7d88-4e3d-a16d-d0e882b8b49c.png)


10. In the repo folder you will also find a sample-data folder. In this folder you will find exported sample data that you could import into the solutions dataverse tables to get started with. 

![image](https://user-images.githubusercontent.com/25781258/235705171-349cf197-2f3c-411c-9d8f-1f771fdeafb3.png)

**NB**: First you would have to update the factmetricboard and the users excel sheet by changing the placeholders "Your Name" and "youremali@domain.com" with the details of the account you want to utilize to setup this project. Be careful not to add any personal details to the repo when contributing.

![image](https://user-images.githubusercontent.com/25781258/235707457-584bd3bb-8771-477b-989c-01b6431d6174.png)

Below is a guide to the order in which this files should be imported, as some of these tables contain lookups to each other and importing in the wrong order could lead to errors. 

    - The order is as follows users -> boardhealth -> boardtype -> product -> metricobjective -> metrictemplate -> metrictype -> metrictypedetails -> factmetricboard -> productmetric -> factmetric.
    
To import the tables into the environment you may follow the below guide.

   - Navigate to the tables page of the Review Hub solution and select the users table as it is the first according to the order. And then select import data from excel.
    
       ![image](https://user-images.githubusercontent.com/25781258/235707866-2aa8e013-642a-4813-ae22-60d8ab6d6e89.png)
    
  - When the popup loads, upload the modified users excel sheet.
    
       ![image](https://user-images.githubusercontent.com/25781258/235708416-f6fe7aa9-6025-48c0-bb10-801499c75fc8.png)
    
  - When mapping shows successful select the import on the top right.
    
       ![image](https://user-images.githubusercontent.com/25781258/235708758-637c781d-67bb-4498-a8b3-f5497fcc761f.png)
       
  - After import is complete and successful you should come across the image below.
    
       ![image](https://user-images.githubusercontent.com/25781258/235716261-1d7100a7-3b31-4b5e-9434-94f7c7ee9efa.png)
       
       
11. Once all previous steps have been complete you should be able to launch the Review Hub Application successfully by navigating to apps and clicking on Review Hub. 

![image](https://user-images.githubusercontent.com/25781258/235719765-46553531-8ac3-41e9-bb23-6ff99aca6e43.png)

**NB:** The ReviewHubConfigurator application is a model driven power app used for managing board/review types in the dataverse table ReviewHub Board Types.




