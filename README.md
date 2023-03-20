# Review Hub

Review Hub leverages the power of Power Apps, a low-code platform, to provide an intuitive interface that makes it easy for users to create and share dynamic dashboards, reports, and presentations. The solution eliminates the need for manual data entry and saves time by automating the generation of review content. With Review Hub, users can access a centralized repository of information that provides a comprehensive view of their business performance, allowing them to make data-driven decisions quickly and accurately. 

The solution is designed to support businesses of all sizes, from small startups to large enterprises. It integrates seamlessly with other Microsoft tools, such as Excel, Power BI, Dataverse and SharePoint, allowing users to access and visualize data from a wide range of sources. The platform’s interface makes it easy to customize and personalize dashboards and reports to meet the specific needs of each business. 

In addition to providing an efficient way to conduct business reviews, Review Hub also helps organizations to streamline their review process and increase collaboration among team members. The solution’s collaborative features, such as real-time commenting, shared workspaces, and version control, make it easy for teams to share feedback and work together to achieve their goals. 

Overall, Review Hub is a powerful solution that empowers organizations to drive their business forward by providing them with the insights and information they need to make informed decisions. By optimizing performance and streamlining processes, Review Hub enables organizations to focus on what matters most – growing their business.

# Getting started.

To utilize review hub you will need a power apps premium plan as some of the connections utilized are premium connectors. And a power apps environment setup where you can import the solution.

## Prerequisites

- Power Apps Environment.
- Power Apps Premium Plan.
- A sharepoint site.
- Azure subscription.
- Azure Devops.

The following connections are utilized within the solution. There a Data Loss Policy(DLP) which allows the use of all these connections should be assigned. To learn more about DLPs please visit [Data Loss Prevention Policies](https://learn.microsoft.com/en-us/power-platform/admin/wp-data-loss-prevention)

- Azure Devops
- Power BI
- Dataverse
- Azure Blob Storage
- Azure AD
- Approvals
- Office 365 Users
- Sharepoint
- Excel Online
- Outlook

## Installation

- Clone the repository to your local machine 
```
git clone https://github.com/microsoft/review-hub.git
```
- Import the zipped solution file named Review Hub from the latest release into your environment.

- After providing all the connections, you will be required to provide values for all the environment variables viable for your use case. The description for these variables are present within the solution.

- You will also need to move the Data Collection Example.xlsx and the factMetricsBulkUpload.xlsx from the Sample Files folder to your sharepoint site if you wish to take advantage of the metric and metric values bulk upload features respectively.

- Then lastly you could upload the exported dataverse tables sample data located in the Exported Tables folder under Sample Files to your environment to get started with.

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

For details on how to contribute to the repo see [CONTRIBUTING.md](CONTRIBUTING.md).

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
