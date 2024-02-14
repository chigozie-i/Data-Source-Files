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
