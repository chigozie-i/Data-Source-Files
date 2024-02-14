![Connecting To Files](https://github.com/chigozie-i/Data-Source-Files/blob/main/Connecting%20To%20Files.png)
## OVERVIEW:

This document centers on data analysis utilizing Microsoft Power BI. It is a component of a series of documentation projects aimed at exploring methods for connecting to your data source. This document seeks to underscore the critical significance of selecting an appropriate data source connection method and to offer comprehensive guidance on the diverse approaches available for establishing connectivity to your data source prior to initiating any essential data transformations tailored to your analytical objectives.

The primary goal of this endeavor is to establish a dependable repository for your data, fostering operational efficiency and ensuring the accuracy of reporting in alignment with the business requirements.

The method by which you establish connectivity to your data source holds considerable importance, as it directly influences the efficiency of your analytical tools and shapes the user experience. Moreover, it plays a pivotal role in determining the effectiveness, precision, and trustworthiness of the analytical processes and resulting reports.


## DATA SOURCES:
Sometimes, you may be required to build Microsoft Power BI reports, with data sourced from various databases and files. These data sources vary, with some housed in Microsoft SQL Server and others in Microsoft Excel, yet they are all interconnected.

![Data Sources](https://github.com/chigozie-i/Data-Source-Files/blob/main/Data%20Sources.png)

Prior to report creation, it's essential to extract data from the various data sources. As the interaction with the sources differ, familiarizing yourself with the intricacies of the source platforms is imperative to report building within Power BI.

#### Data Sources:

1.	Files
2.	Relational Data Sources | Create Dynamic Reports with Parameters
3.	NoSQL Database 
4.	Online Services
5.	Azure Analysis Services

This documentation project focuses on Files.

## CONNECTING TO FILES:

Companies frequently export and archive data into files, with one common format being a flat file. A flat file consists of a single data table where each row conforms to the same structure, devoid of any hierarchical organization. You're likely acquainted with prevalent types of flat files, including comma-separated values (.csv) files, delimited text (.txt) files, and fixed-width files. Additionally, output files from various applications, such as Microsoft Excel workbooks (.xlsx), also fall into this category.
Suppose the Sales department at Imaginary Inc. possesses a flat file containing sales data. They've tasked you with building Power BI reports using this dataset alongside data from other sources. 
The first step would be deciding the preferred file location for exporting and storing the data.

![File location](https://github.com/chigozie-i/Data-Source-Files/blob/main/file%20location.png)

Your Excel files might exist in one of the following locations:

•	Local: Data from a local file can be imported into Power BI. With this method, the file is not moved into Power BI nor is a persistent link to it. Instead, Power BI generates a new semantic model, incorporating data from the Excel file. Consequently, alterations made to the original Excel file do not update the Power BI semantic model. Importing local data is suitable for static datasets that remain unchanged.

•	OneDrive: Whether you're using OneDrive for Business or personal OneDrive, both options enable seamless integration with Power BI. By pulling data from your OneDrive account, you ensure synchronization between Excel files and your Power BI semantic model, reports, and dashboards. Power BI regularly connects to your OneDrive files, automatically updating your semantic model, reports, and dashboards whenever changes are detected. While using OneDrive for Business offers direct integration benefits, accessing data from personal OneDrive accounts requires signing in with personal credentials and enabling the "Keep me signed in" option. It's advisable to consult your system administrator to confirm if personal OneDrive connections are permitted within your organization.

•	SharePoint - Team Sites: Storing your Power BI Desktop files on SharePoint Team Sites mirrors the process of saving to OneDrive for Business, with a slight variation in file connection methods within Power BI. You have the option to specify a URL or connect directly to the root folder.

Utilizing cloud solutions like OneDrive or SharePoint Team Sites proves to be the most efficient method for maintaining synchronization between your files and the associated semantic model, reports, and dashboards in Power BI. Nevertheless, if your data experiences infrequent changes, saving files locally on your computer remains a viable alternative.

## HOW TO CONNECT TO DATA IN A FILE:

Connecting to a data source, starts with Get Data. On the Home tab, select Get data and then the option that you require (such as Text/CSV or XML). In this case it’s Excel Workbook.

![Get Data](https://github.com/chigozie-i/Data-Source-Files/blob/main/Get%20Data.png)

Based on your selection, you'll be required to locate and access your data source. If necessary, you may encounter a prompt to log in to a service like OneDrive to verify your request. In this scenario, you'll access the Sales Data Excel workbook stored on the Desktop.

![Excel File](https://github.com/chigozie-i/Data-Source-Files/blob/main/Excel%20Selection.png)

The Navigator window pops up once the file is connected to Power BI Desktop. This window displays the available data within your data source. You have the option to select a table or entity to preview its contents, ensuring that the correct data is loaded into the Power BI model.

Upon selecting the check box(es) of the table(s) you wish to import into Power BI, the Load and Transform Data buttons become active. At this point, you can proceed by clicking the Load button to automatically load your data into the Power BI model or opt for the Transform Data button to launch the Power Query Editor. In the editor, you can review and cleanse your data before importing it into the Power BI model.

![Navigator](https://github.com/chigozie-i/Data-Source-Files/blob/main/Navigator%20window.png)

## FILE CONNECTION PATH:

During development or in the event of a change in file storage location, you may find it necessary to modify the source file's location for a data source. To ensure the continued accuracy of your reports, it's important to update the file connection paths in Power BI.
When updating a file path, it's crucial to reconnect to the same file with its original structure intact. Any modifications to the file's structure, such as column deletions or renaming, can disrupt the reporting model.

Power Query provides many ways for you to accomplish this task. 
•	Data source settings.
•	Query settings.
•	Advanced Editor.

In the Queries section of Power BI desktop Home tab, select Transform data, and then Data source settings.

![File Path](https://github.com/chigozie-i/Data-Source-Files/blob/main/File%20Path.png)

The Data source settings window pops up, select Change Source, and define the source data file path.

![File Path 2](https://github.com/chigozie-i/Data-Source-Files/blob/main/File%20Path%202.png)

## DATA STORAGE MODE:

Within Microsoft Power BI Desktop, you have the capability to designate the storage mode for a table, which governs how the software temporarily retains table data in-memory for reports. When establishing a connection to your data source, you can opt for one of three storage modes:
• Import
• DirectQuery
• Dual (Composite)

The prevalent method for utilizing data in Power BI involves importing it into a Power BI semantic model. Importing data entails storing it within the Power BI file and subsequently publishing it alongside the Power BI reports. This process facilitates direct interaction with the data. However, this approach may not be suitable for all organizations. It's crucial to ensure that business requirements are met when importing data into Power BI.

In scenarios where security constraints prevent direct data importation, or when semantic models are excessively large and loading them into Power BI would result in considerable delays, it's imperative to avoid creating performance bottlenecks. Power BI addresses these challenges through the DirectQuery storage mode, allowing direct querying of data in the data source without importing a copy into Power BI. DirectQuery proves beneficial as it guarantees access to the most current data.

In Dual mode, you can designate certain data to be directly imported while others must be queried. Tables configured with this setting can function either with cached or uncached data, depending on the query context submitted to the Power BI semantic model. Some queries are fulfilled using cached data, while others trigger on-demand queries to the data source.
You can access storage modes by switching to the Model view, selecting a data table. 

![Storage Mode](https://github.com/chigozie-i/Data-Source-Files/blob/main/Storage%20mode%201.png)

In the resulting Properties pane, selecting which mode that you want to use from the Storage mode drop-down list.

![Storage Mode 2](https://github.com/chigozie-i/Data-Source-Files/blob/main/Storage%20mode%202.png)

![Storage Mode 3](https://github.com/chigozie-i/Data-Source-Files/blob/main/Storage%20mode%203.png)

## LESSONS LEARNT:

This project aims to contribute to a deeper understanding of data analytics with Power BI. Some key reflections include:

1. Importance of Flexibility: Being able to adapt to changes in data source locations is crucial for maintaining the accuracy and relevance of analytical reports. Power Query offers versatile tools for updating connection paths seamlessly.

2. Syncing Data with Cloud Options: Utilizing cloud options such as OneDrive and SharePoint Team Sites facilitates the synchronization of data and analytical models, ensuring real-time updates and enhancing collaboration among team members. Emphasizing the advantages of cloud-based solutions could further streamline data management processes.

3. Continuous Learning: The field of data analytics is dynamic, with new tools and techniques emerging regularly. Embracing a mindset of continuous learning and staying updated with the latest advancements in Power BI can enhance analytical capabilities and drive better decision-making processes.

Moving forward, potential areas for further improvement include:

1. Exploring Advanced Features: Delving deeper into advanced features of Power BI, such as DAX calculations, data modeling, and interactive visualizations, can unlock additional insights and enhance the sophistication of analytical reports.

2. Enhancing Data Governance: Implementing robust data governance policies and practices ensures data integrity, security, and compliance with regulatory standards. Integrating governance frameworks within Power BI workflows can mitigate risks and bolster trust in analytical outputs.

3. Collaboration and Knowledge Sharing: Encouraging collaboration among team members and fostering a culture of knowledge sharing can accelerate learning and innovation within the organization. Establishing forums, training sessions, and documentation repositories can facilitate the exchange of best practices and insights among stakeholders.

## CONCLUSION:
This project series delves into various data sources, aiming to uncover valuable insights into the complexities of data analytics using Power BI. It underscores the significance of efficient data source connectivity and ongoing learning. Through reflection on lessons gleaned and pinpointing areas for enhancement, organizations can fully leverage Power BI's capabilities to facilitate informed decision-making and attain strategic goals.

## REFERENCE:
https://learn.microsoft.com
https://docs.microsoft.com

