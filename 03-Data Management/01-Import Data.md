# Import Data



## Learning Objectives
After completing this unit, you'll be able to:

- Describe and compare the different options for importing data into Salesforce.
- List the steps involved in preparing and importing data from a sample .csv file using the Data Import Wizard.



## Introduction to Data Import
You can easily import external data into Salesforce. Supported data sources include any program that can save data in the comma delimited text format (.csv).

Salesforce offers two main methods for importing data.

- **Data Import Wizard**—this tool, accessible through the Setup menu, lets you import data in common standard objects, such as contacts, leads, accounts, as well as data in custom objects. It can import up to 50,000 records at a time. It provides a simple interface to specify the configuration parameters, data sources, and the field mappings that map the field names in your import file with the field names in Salesforce.
- **Data Loader**—this is a client application that can import up to five million records at a time, of any data type, either from files or a database connection. It can be operated either through the user interface or the command line. In the latter case, you need to specify data sources, field mappings, and other parameters via configuration files. This makes it possible to automate the import process, using API calls.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

With both methods, the number of records you can import depends on your permissions, the type of data you’re importing, and the overall data storage limits for your organization. The type of objects you can import depends on your edition.

## Use the Data Import Wizard When:
- You need ==to load less than 50,000 records.==
- The ==objects you need to import are supported by the wizard.==
- ==You don’t need the import process to be automated.==

## Use Data Loader When:
- You need t==o load 50,000 to five million records.== If you need to load more than 5 million records, we recommend you work with a Salesforce partner or visit the [AppExchange](http://appexchange.salesforce.com/) for a suitable partner product.
- You need ==to load into an object that is not supported by the Data Import Wizard.==
- You want ==to schedule regular data loads, such as nightly imports.==

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Data Loader uses the SOAP API to process records. For faster processing, you can configure it to use the Bulk API instead. The Bulk API is optimized to load a large number of records simultaneously. It is faster than the SOAP API due to parallel processing and fewer network round-trips.



## Prepare for Data Import
Cloud Kicks manufactures custom sneakers, designed and personalized for their customers. Sales superstars Candace and Jose are always eager to get fresh air and exercise, so they schedule a walking meeting with Linda, the company’s Salesforce admin. They want Linda’s help to bring their CRM data into Salesforce. Because they have fewer than 50,000 records, Linda decides to use the Data Import Wizard. When she gets back to her desk after the walk, she preps the data for import.

![ Jose and Candace talk to Linda about importing their data](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/lex_implementation_data_management/lex_implementation_data_import/images/45580dda0f46ccafdc518fb98aef4196_cloudkicks-walking-mtg.png)

Follow these steps before you start importing any data.

1. Use your existing software to create an export file. You'll use this exported data file to now *import* the data into Salesforce. 
2. Clean up the import file for accuracy and consistency. This involves updating the data to remove duplicates, delete unnecessary information, correct spelling and other errors, and enforce naming conventions.
3. Compare your data fields with the Salesforce fields you can import into, and verify that your data will be mapped into the appropriate Salesforce fields. You might need to fine-tune the mapping before starting the import. For details, see [Field Mapping for Data Sources](https://help.salesforce.com/apex/HTViewHelpDoc?id=field_mapping_for_other_data_sources_and_organization_import.htm&language=en_US) in the online help.
4. Make any configuration changes required in Salesforce to handle the imported data. For example, you might need to create new custom fields, add new values to picklists, or temporarily deactivate workflow rules.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Salesforce recommends you import using a small test file first to make sure you’ve prepared your source data correctly. 

View the second video "Data Import: Clean Up Your Import File" in the How To Import Data into Salesforce Series for more information on cleaning up your import file.
https://www.salesforce.com/


## Use the Data Import Wizard
Once you have created an export file and cleaned up the data for import, follow these steps to import data using the Data Import Wizard.

1. Start the wizard.
   1. From Setup, enter Data Import Wizard in the Quick Find box, then select **Data Import Wizard**. 
   2. Review the information provided on the welcome page, then click **Launch Wizard!**

2. Choose the data that you want to import.

   1. To import accounts, contacts, leads, solutions, person accounts, or campaign members, click **Standard Objects**. To import custom objects, click **Custom Objects**.
   2. Specify whether you want to add new records to Salesforce, update existing records, or add and update records simultaneously.
   3. Specify matching and other criteria as necessary. Hover over the question marks for more information about each option.
   4. Specify the file that contains your data. You can specify your data file by dragging the CSV to the upload area of the page or by clicking the CSV category you’re using and then navigating to and selecting the file.
   5. Choose a character encoding method for your file. Most users can accept the default character encoding.
   6. Click **Next**. 

3. Map your data fields to Salesforce data fields. The Data Import Wizard tries to map as many of your data fields as possible to standard Salesforce data fields. If Salesforce can’t automatically map fields, however, you do it manually. Unmapped fields are not imported into Salesforce. To see a list of standard Salesforce data fields, from Setup, at the top of the page, click |  Object Manager. Click the object whose fields you’re interested in, and click     Fields & Relationships. For example, if you want to see a list of standard Salesforce fields for leads, click  Object Manager | Lead | Fields & Relationships.

   1. Scan the list of mapped data fields and locate any unmapped fields.
   2. Click **Map** to the left of each unmapped field.
   3. In the Map Your Field dialog box, choose the Salesforce fields you want to map to and click **Map**. The Map Your Field dialog box also gives you the option of saving data from unmapped fields in a general notes field for accounts and contacts. To do so, choose Account Note or Contact Note from the Map To drop-down list and click **Map**.
   4. To change mappings that Salesforce performed automatically, click **Change** to the left of the appropriate field, then choose the Salesforce fields you want to map to and click **Map**.
   5. Click **Next**.

4. Review and start your import.

   1. Review your import information on the Review page. If you still have unmapped fields that you want to import, click **Previous** to return to the previous page and specify your mappings.
   2. Click **Start Import**.

5. Check import status. From Setup, enter “Bulk Data Load Jobs” in the Quick Find box, then select **Bulk Data Load Jobs**.  The user who starts the data import receives a status email when the import is completed.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Use the zoom option in your browser to adjust (shrink) the size of the content if you can't see the Map button.

The user who starts the data import receives a status email when the import is completed.



## Tell Me More...
This information can help you integrate your imported data into Salesforce.

- New Values for Picklists and Multi-Select Picklists—If you import a picklist value that doesn’t match an existing picklist value:
  - For an unrestricted picklist, the Data Import Wizard uses the value that’s in the import file.
  - For a restricted picklist, the Data Import Wizard uses the picklist’s default value.
- **Multi-Select Picklists**—To import multiple values into a multi-select picklist, separate the values by a semicolon in your import file.
- **Checkboxes**—To import data into a checkbox field, use 1 for checked values and 0 for unchecked values.
- **Default Values**—For picklist, multi-select picklist, and checkbox fields, if you do not map the field in the import wizard, the default value for the field, if any, is automatically inserted into the new or updated record.
- **Date/Time Fields**—Ensure that the format of any date/time fields you are importing matches how they display in Salesforce per your locale setting.
- **Formula Fields**—Formula fields cannot accept imported data because they are read-only.
- **Field Validation Rules**—Salesforce runs validation rules on records before they are imported. Records that fail validation aren’t imported. Consider deactivating the appropriate validation rules before running an import if they affect the records you are importing.


## Resources
- [Data Import FAQ](https://help.salesforce.com/HTViewHelpDoc?id=faq_import_general.htm&language=en_US)
- [Preparing Your Data for Import](https://help.salesforce.com/apex/HTViewHelpDoc?id=import_prepare.htm&language=en_US)
- [Data Loader Overview](https://help.salesforce.com/HTViewHelpDoc?id=data_loader.htm&language=en_US)
- [Explore how to import data more effectively in Salesforce](http://pages.mail.salesforce.com/achievemore/managedata/?utm_source=trailhead&utm_medium=resources&utm_campaign=datamanagement&utm_content=importdata)
- [Data Import Video Series](http://salesforce.vidyard.com/watch/ARIjWm2qrDkJVJxEhReFug)

## Hands-on Challenge

**+500 points**

### GET READY
You’ll be completing this unit in your own hands-on org. Click **Launch** to get started, or click the name of your org to choose a different one.

If you use Trailhead in a language other than English, make sure that your hands-on org is set to the same language as the challenge instructions. Otherwise you may run into issues passing this unit. Want to find out more about using hands-on orgs on Trailhead? Check out [Trailhead Playground Management](https://trailhead.salesforce.com/en/content/learn/modules/trailhead_playground_management).

### YOUR CHALLENGE

Import data using the Data Import Wizard.

Download a CSV file that contains contact data, and import it using the Data Import Wizard.

- Download [this CSV file](https://raw.githubusercontent.com/developerforce/trailhead-files/master/contacts_to_import.csv) by right-clicking and selecting "Save Link As". Make sure you save it as a CSV (.csv) file, and not a text (.txt) file. You don't need to use Excel.

- Use the Data Import Wizard to import the file:

  - Kind of data: **Accounts and Contacts**

  - Type of import: **Add new records**

  - - Match Contact by: **Name**

  - Where is your data located?: **CSV**

  - - File: **Choose File**
    - Character Code: **ISO-8859-1** (the default)
    - Values Separated by: **Comma**

  - Map all fields:

  - - FNAME to Contact: First Name
    - LNAME to Contact: Last Name
    - CELL to Contact: Mobile