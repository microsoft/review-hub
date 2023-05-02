- Clone the repository to your local machine 
```
git clone https://github.com/microsoft/review-hub.git
```
- Import the zipped solution file named Review Hub from the latest release into your environment.

- After providing all the connections, you will be required to provide values for all the environment variables viable for your use case. The description for these variables are present within the solution.

- You will also need to move the Data Collection Example.xlsx and the factMetricsBulkUpload.xlsx from the Sample Files folder to your sharepoint site if you wish to take advantage of the metric and metric values bulk upload features respectively.

- Then lastly you could upload the exported dataverse tables sample data located in the Exported Tables folder under Sample Files to your environment to get started with.

  - First you would have to update the factmetricboard and the users excel sheet by changing the placeholders "Your Name" and "youremali@domain.com" with the details of the account you want to utilize to setup this project. Be careful not to add any personal details to the repo when contributing.
 
  - Then the excel files have to be uploaded in a certain order to avoid errors, the order is as follows users -> boardhealth -> boardtype -> product -> metricobjective -> metrictemplate -> metrictype -> metrictypedetails -> factmetricboard -> productmetric -> factmetric.