## SD Interface EDI Releases

### 8.4.1

#### Enhancements

- AppSource App - A new event, OnBeforeSalesHeaderModify, was created in the ProcessSalesOrder function in the SDY EDI Import Manager Codeunit. This event is called just before modifying the Sales Header record during the EDI sales order import and can be used to inject custom logic before the header is finalized, apply peer-specific adjustments and to log or validate header data based on queue or peer context.

### 8.4.0

#### Enhancements

- AppSource App - Grouping by VAT Caption was implemented for Credit Note Document Types.

- AppSource App - An option to disable archiving of Master Data was added to the Peer Card. 

- AppSource App - A new Licence Install and Setup Wizard was created.

- AppSource App - The notification to activate the app, displayed on fresh install of SD Document Sender, was added to the standard Business Central role centres.

- AppSource App - Changes were made to the Manage Subscriptions page.

- AppSource App - A minor change was made to the About page.

### 8.3.0

#### Enhancements

- AppSource App - A new action was added to the VAN Card to copy VAT Identifiers from VAN to VAN.

- AppSource App - A new action to copy a Peer from one VAN to another was added to the VAN Card.

- AppSource App - A new VAT Reg No. field was added to the VAN Card.

- AppSource App - A change was made to avoid a runtime error when generating messages if a field defined on data builder is missing from the table.

- AppSource App - The Copy Settings From VAN functionality on the File Transfer Settings FastTab in the VAN Card was reworked.

- AppSource App - A new action was added to the Setup Card called View Our Apps. This action opens a page on AppSource pointing to all our Simply Dynamics Ltd apps.

- AppSource App - The Lead Subscription Link from the Request Subscription action in the Product Activation page was updated.

#### Bug Fixes

- AppSource App - The VAN filter on the EDI Statistics FactBox was cleared when the VAN Card was opened. This was fixed.

### 8.2.1

#### Bug Fixes

- AppSource App - A fix was made to an error on Sales Order pre processing when the codeunit was run through the Job Queues.

### 8.2.0

#### Bug Fixes

- AppSource App - A fix was made to an error thrown when VAT Identifier settings on the VAN card were grouped by caption.

### 8.1.0

#### Enhancements

- AppSource App - A change was made to raise an error in the inbound queue that the sales order has already been created if the incoming sales order (Generated File) already exists in the EDI History Detail. This will flag, for situations where the order file is presented more than once, that the incoming order file has already been processed and the order created.

- AppSource App - A new field, History Item Exists, was added to the Queue Detail table.

- AppSource App - A new field was added at VAN level, Files Transferred Per API Call, to transfer one file at a time, or a specific number of files at a time, from Blob Storage to SFTP. Once the file is transferred the blob file is deleted. This applies to both inbound and outbound files.

- AppSource App - Minor changes were made to the SDY EDI File Transfer functionality code.

- AppSource App - 7 day KPI cues for the SFTP File Transfers, with drill through to the File Transfers Log, were added to the Role Centre.

- AppSource App - Two new actions, Deleted Selected and Download File, were added to the Azure File List so files can be viewed before pre-processing or allocation routines have been run.

### 8.0.1

#### Enhancements

- AppSource App - A change was made to the SD Interface EDI Job Queue logic to ensure that the incoming message file is deleted after the Inbound Queue Entry is created in SD Interface EDI even if the Job Queue fails or an error is thrown.

- AppSource App - A new routine was added to delete the file content from the EDI History Detail and the routine to delete the File Transfer Logs was reworked.  

### 8.0.0

#### Enhancements

- AppSource App - Changes were made to implement DRS on Celtrino Sales Invoices.

- AppSource App - A new Trading Units table was created to calculate DRS lines in Sales Invoice and Credit Memo files by the number of traded units. A Traded Unit Code can be applied to an Item. If an Item has a traded unit assigned, the Qty. per UOM is overwritten in the Sales Invoice and Sales Credit files. If there is no traded unit assigned, the original Qty. per UOM is used.  

- AppSource App - Changes were made to the VAT Identifiers Table. A new Boolean field Group VAT by Caption allows grouping of VAT Amount Lines and Identifiers using the Identifier Caption and VAT % in the xml data file. The VAT Amount Lines are amalgamated into one line grouped by Identifier Caption and VAT %.

- AppSource App - The Sales Invoice Line and the Sales Credit Memo line were extended with two new fields, SDY Shipment Reference and SDY VAT Identifier.

- AppSource App - UI change to the Role Centre to highlight the File Allocation Errors Today in red. 

- AppSource App - An event was added in CodeUnit 43012018 SDY EDI Allocation Mgt. called OnAfterRunAllocation to handle any unallocated files after the File Allocation process.

### 7.1.0

#### Enhancements

- AppSource App - A new event OnBeforeItemParseFailure was added to Codeunit 43012017 SDY EDI PO. Conf. Batch.

- AppSource App - A new event OnBeforeReleaseSalesOrder was added to Codeunit 43012003 SDY EDI Import Manager.

- AppSource App - Changes were made to the Export File routine surfaced in the SD Interface EDI Setup Card.

- AppSource App - A change was made to the import of Assisted Data Setup.

- AppSource App - A change was made to the licence expiry notification. The logic for checking for expiry dates was reworked.

- AppSource App - Enhancements were made to the App Request Subscription page.

- AppSource App - ToolTips were updated in the About, Product Activation, and Tenant Subscription pages.

- AppSource App - Additional phrases were added as search phrases for the SD Interface EDI pages.
  
### 7.0.7

#### Enhancements

- AppSource App - A change was made to allow for unidirectional sftp transfer of files in SD Interface EDI.

- AppSource App - The logo in the SD Interface EDI App was updated to use our new logo.

### 7.0.6

#### Enhancements

- AppSource App - Some file allocation enhancements were made for Celtrino. The VANs GLN number is now picked up from the incoming file.

#### Bug Fixes

- AppSource App - The azure function that transfers files from blob storage to a folder in sftp was copying files to two locations.

### 7.0.5

#### Enhancements

- AppSource App - A new option was added to the VAN Card to allow for insertion of blocked items on creation of inbound orders.

- AppSource App - A new option was added to the VAN Card to allow auto release of EDI Sales Orders on creation.

- AppSource App - The links in the About page were updated.

- AppSource App - Some ToolTips on the VAN Card were updated.

### 7.0.4

#### Enhancements

- AppSource App - A change was made to Master Data Messages. The System Record ID is now used to generate the Master Data records.

- AppSource App - For Messages of Document Type Master Data the Multiple Documents per File checkbox is set to enabled by default and cannot be edited.  

### 7.0.3

#### Enhancements

- AppSource App - An extension was created on certain standard tables to stamp the VAN Code on the Credit Notes, Sales Order Acknowledgement, Sales Invoices, Sales Shipments, Purchase Orders, incoming Purchase Order Confirmations and incoming Sales Orders. The VAN Code field is not surfaced on any pages but allows sites to distinguish which VAN is associated with the document.

- AppSource App - Allow filtering of outbound messages at message card level. This allows for situations where a site might not want every document type set up to send through SD Interface EDI to be added to the outbound queue. Outbound messages include Sales Credit Note, Sales Invoice, Sales Order Acknowledgement, Purchase Order, and Sales Shipment. 

### 7.0.2

#### Enhancements

AppSource App - The File Name Mask field on the Messages table was not used elsewhere in the App. The field was updated to Filename and is now used as the filename for Outbound Master Data Files in Live mode.  If a Filename is not entered, then the Filename Series is used for Outbound Master Data files.  

AppSource App - A minor change was made to the FTP connection functionality.

### 7.0.1

#### Enhancements

- AppSource App - A new Identifier Caption field was added to the VAT Identifiers FastTab on the VAN Card. This field can be used to display an alternative value for the VAT Identifier at message summary level for VAT details if required.

### 7.0.0

#### Enhancements

- AppSource App - Functionality was created for File Transfer Capability using Azure functions. 

- AppSource App - File Transfer implementation was added to the VAN Card. 

- AppSource App - Functionality was created to allow for inbound file preprocessing capabilities. 

- AppSource App - A new inbound file preprocessing capability was implemented for Wasp. 

- AppSource App - Multiple files for multiple peers may be received from a VAN in a single file dump. File Allocations in SD Interface EDI allows you to specify how you want these files allocated to the different folders in azure blob storage for message processing. This functionality has been extended for Wasp. 

- AppSource App - Master Data Field Filters were added to the SD Interface EDI Message Card. 

- AppSource App - A File Transfer cue was added to the Role Centre. 

- AppSource App - Changes were made to some field captions and properties on fields in the File Transfer Settings FastTab on the VAN Card. 

- AppSource App - A small number of UI changes were made to the SD Interface EDI History Document List. 

- AppSource App - Tooltips on the SD Interface EDI Setup Card were updated. 

- AppSource App - Some fields on the VAN Card were recaptioned. 

- AppSource App - ToolTips were updated on the VAN Card. 

#### Bug Fixes

- AppSource App - When requeuing a history file the container name was not revalidated. This was fixed. 

### 6.2.0

#### Enhancements

- AppSource App - The Create Outbound Messages action was changed to exclude the Master Data document type.

- AppSource App - New functionality was added to create outbound Master Data files.

- AppSource App - New actions were added to the SD Interface EDI Role Centre and Worksheet to create Master Data files.

- AppSource App - A new Wasp message type was created for Customer Master Data.

- AppSource App - A new Wasp message type was created for Item Master Data.

- AppSource App - A new Wasp message type was created for Inbound Sales Orders

#### Bug Fixes

- AppSource App - Files were not deleted from blob storage when creating inbound queues for Peers that had the Multiple Documents Per File option on. This was fixed.

- AppSource App - An event that was exposed to handle situations where an item does not exist on an incoming Sales Order was changed so that the default behaviour is to raise an error when the message is processed.

### 6.1.0

#### Enhancements

- AppSource App - Multiple files for multiple peers may be received from a VAN in a single file dump. File Allocations in SD Interface EDI allows you to specify how you want these files allocated to the different folders in azure blob storage for message processing. This functionality has been extended for Celtrino.

- AppSource App - An event was added to place filters on incoming documents.

- AppSource App - An event was added that would allow for situations where an inbound Purchase Order Acknowledgement could come through more than once.

- AppSource App - An event was added to handle situations where an item does not exist on an incoming Sales Order.

- AppSource App -  An event was added to allow for custom routines to be called before the standard SD Interface EDI file allocation routine is run.

- AppSource App - A new File Structure Template for PIPE_IN was created.

### 6.0.9

#### Bug Fixes

- AppSource App - Fixed an issue where a message stating that the record in table SDY EDI History already exists is being intermittently raised. 

### 6.0.8

#### Enhancements

- AppSource App - A function to get the PO record was added to the BatchPOConfirmation Codeunit. 

### 6.0.7

#### Enhancements

- AppSource App - A new SD EDI Interface History List was created. This list allows users to search for individual processed documents. This list is accessible by drilling through on the History Documents cue on the SD Interface EDI Role Centre.

#### Bug Fixes

- AppSource App - Choosing the Remove Selected action in the EDI Worksheet did not always refresh the remaining records correctly. Users had to choose to refresh the EDI Worksheet page. This was fixed.

### 6.0.6

#### Enhancements

- AppSource App - A new field, Max Documents Per Queue, was added to the SD EDI Setup Card to limit the amount of documents that can be added to a queue. Business Central by default closes the API call to the EDI transformation function if a response is not received back after a certain amount of time.

- AppSource App - Functionality was added to allow for file deletion from the File Allocation lists which also deletes the files from Azure Blob storage.

- AppSource App - The Document Log action was surfaced on the SD EDI Worksheet.

- AppSource App - An event was added to Sales Order Processing in the SD EDI Queue to allow for an extension to give warnings instead of errors when items cannot be found on incoming sales orders.

#### Bug Fixes

- AppSource App - When generating Outbound Messages for Sales Credit Notes and Sales Invoices, if documents existed with no lines on the document, then an error was raised. This was fixed.

- AppSource App - In Live Mode the Filename Series was not being used if the Multiple Documents per File option was turned on for Outbound Message Types.

### 6.0.5

#### Enhancements

- AppSource App - A change was made to create Outbound Purchase Order messages only for released Purchase Orders.

- AppSource App - An event was surfaced in the SDY EDI Queue Manager codeunit to allow application of specific filters to Outbound Purchase Orders during Outbound Message creation.

### 6.0.4

#### Bug Fixes

- AppSource App - Fixed an issue where Sales Order Acknowledgements were not created if entries for the inbound Sales Order exist in the EDI History Log.

### 6.0.3

#### Enhancements

- AppSource App - Minor Mods were made to the File Folder Allocations for Sales Orders and Purchase Order Confirmation files for a specific Batch implementation.

### 6.0.2

#### Enhancements

- AppSource App - Multiple files for multiple peers may be received from a VAN in a single file dump. File Allocations in SD Interface EDI allows you to specify how you want these files allocated to the different folders in azure blob storage for message processing. This functionality can be extended for specific VANs.

- AppSource App - A new field PO Confirmation Implementation was added to the SD Interface EDI Message Types table and list to allow for easy setup of site specific functionality for individual message types.

#### Bug Fixes

- AppSource App - Fixed an issue where the inbound Purchase Order Confirmation file had an error in the EDI Worksheet but this Error was not displaying in the Purchase Order Confirmation page.

### 6.0.1

#### Enhancements

- BCv21 App - Drag and drop file management was added to SD Interface EDI to upload and delete files to Azure Blob Storage.

- BCv21 App - A new Message List with a FactBox was created to allow for upload, deletion and download of files to and from Azure Blob Storage.

- BCv21 App - Functionality was added to allow for drag and drop of multiple files to the Azure Files FactBox.

- BCv21 App - A change was made to allow for selection of multiple files in the Azure Files FactBox for deletion.

- BCv21 App - A change was made to prompt the user when they choose to delete files from the Azure Files FactBox.

- BCv21 App - The Delete Line action in the Azure Files FactBox was removed as the delete action is used to delete the files.

### 6.0.0

#### Enhancements

- BCv21 App - The existing C/AL code base was converted to AL extensions. 

- BCv21 App - Captions on the Peer Usage FactBox were updated. 

- BCv21 App - The New action was surfaced on the Data Builders List to allow users create new data builder definitions. 

- BCv21 App - When inserting a new record in the Peers Page Part of the VAN Card the user was prompted if they wanted to update related records. The key was changed. 

- BCv21 App - The Links in the About Page were updated to point to our new website. 

- BCv21 App - The latest ISV Licence Controller was added to the product. 

- BCv21 App - The Latest Version of the product and the AppSource URL was added to the About Page. 

- BCv21 App - A test app was created for AppSource submission. 

- BCv21 App - Tooltips were added to the SD Interface EDI app. 

- BCv21 App - The product was readied for AppSource submission. 

- BCv21 App - Captions on objects were updated to allow for future translation requests. 

- BCv21 App - The Application Area and Usage Category were added to the SD EDI Interface pages and reports so they are searchable in the Tell Me. 

- BCv21 App - The SD Interface EDI objects were renamed with an SDY prefix. 

- BCv21 App - Permission sets were created for SD EDI Interface and the standard Permission Sets of Exten. Mgt., D365 BUS FULL ACCESS, and D365 BASIC were extended to include the SD EDI Interface permission sets. 

- BCv21 App - Standard Dynamics 365 BC Code, Name and Description fields referenced in the SD Interface EDI were increased in length as per standard Dynamics 365 BC. 

- BCv21 App - Assisted Setup was added to the product. 

- BCv21 App - Added the latest version of the Licence Controller to the product. 

- BCv21 App - Various changes were made to the SD Interface EDI Role Centre and the Role Centre is now searchable from the Tell Me. 

- BCv21 App - Functionality was added to the SDY EDI Job Queue Entry Card to allow the new SD Interface EDI document types to be selected from the list of Document Types. 

- BCv21 App - A FactBox similar, to the FactBox in the EPOD Orders page, was added to the Purchase Order Confirmations page, . 

- BCv21 App - The Message Document Type was changed from Purchase Invoice to Purchase Order Confirmation. 

- BCv21 App - Functionality was added to SD Interface EDI to process new Document Types of Sales Order Acknowledgements, Purchase Orders and Purchase Order Confirmations. 

- BCv21 App - The SD Interface EDI Celtrino template files were updated. 

- BCv21 App - Layout changes were made to the SD Interface EDI - Statistics page, headings and fields were grouped together and statistic fields for Purchase Orders and Purchase Invoices were added to the page. 

- BCv21 App - The caption on the SD EDI Blob List Page  was updated to SD Interface EDI Azure File List to match the action in the Role Centre. 

- BCv21 App - The caption on the SD EDI Role Centre was updated from SD Interface EDI to SD Interface EDI - Overview for clarity when searching the Tell Me. 

- BCv21 App - The caption on SD EDI Process Log List was updated from SD Interface EDI Log to SD Interface EDI Process Log for clarity when searching the Tell Me. 

- BCv21 App - Purchase Order, Purchase Order Confirmation, Sales Order Acknowledgement Message Types were created for Batch. 

- BCv21 App - Minor visual changes were made to the Setup Card. FastTabs were renamed, fields were promoted on FastTabs and actions were reordered. 

- BCv21 App - Actions on the SD EDI Role Centre were reordered. 

- BCv21 App - To clean up the SD Interface EDI Role Centre, the actions for VANs, Peers, Message Types and VAT Identifiers were removed from the Role Centre as these can be accessed through the SD Interface EDI Setup Card. 

- BCv21 App - A field caption in the EPOD list was updated. 

- BCv21 App - All actions in the EPOD Orders page were changed to promoted to improve visibility of available actions. 

- BCv21 App - Actions in the EDI Worksheet were regrouped.  

- BCv21 - The message displayed when users choose to generate messages with an expired SD Interface EDI licence was changed. 

- BCv21 App - The SD Interface EDI Licence Message was updated on first install of the App to prompt the user to activate a free trial and choose Assisted Setup to create demo data. 

- BCv21 App - A change was made to the code whereby if an Inbound Sales Order or an EPOD file is ignored on the blob storage, not brought into the queue, the file will not be deleted. 

- BCv21 App - The new Inbound Container and Outbound Container fields on the Peer Card had their property set to additional importance. 

- BCv21 App - Minor layout changes were made to the Storage Setup Card. 

- BCv21 App - The flowfield count of Storage Containers setup in SD Interface EDI was added as a Cue in the KPIs FastTab in the EDI Setup Card. 

- BCv21 App - In the SD EDI Setup Card, to keep related actions grouped together, the Storage Containers action was moved to the first action in the list before the Test Azure Function. 

- BCv21 App - A change was made to allow users create a new Storage Container record from the Container list that is dsiplayed in the drilldown of the Default Storage Container in the EDI Setup card. 

- BCv21 App - The layout of SD Interface EDI - Statistics in the Role Centre was changed. 

- BCv21 App - Functionality was created to allow for different sources to be defined for the container storage. 

- BCv21 App - The File List action on the Role Centre was renamed to Azure File List. 

- BCv21 App - The Sales Header table was extended to stamp Sales Orders that are created by importing EDI files. 

- BCv21 App - SD Interface EDI licencing checks were added to the code. 

- BCv21 App - Add an alert notification to display in the Role Centre when the SD Interface EDI licence is due to expire in 5 days. 

- BCv21 App - The About page had extra space at the top of the page. This was fixed. 

- BCv21 App - In the SD Interface EDI Setup card, the caption of the Active Vans cue in the KPIs FastTab was updated to Active VANs. 

- BCv21 App - In the SD Interface EDI Setup Card, text was surfaced on the Function App FastTab as per the text on the Azure Blob Storage FastTab to display when details are validated. 

- BCv21 App - The Captions in the SD EDI Create Queue Items Report were updated. Peer Type was renamed to Type and Peer Key was renamed to No. 

- BCv21 App - The message displayed when multiple Entries in the EDI Worksheet are selected for removal was updated. 

- BCv21 App - In the Message Card the Peer Key field was changed to Peer No. 

- BCv21 App - A KPI FastTab was added to the SD Interface EDI Setup card. 

- BCv21 App - A small typo was fixed on the Process Log action on the SD Interface EDI Peers List. 

- BCv21 App - The Enabled field was surfaced in the Peers ListPart Page displayed on the VAN Card. 

- BCv21 App - A page was created to display all installed Simply Dynamics Apps and Subscription details for the tenant. 

- BCv21 App - The Licence Controller Licence Expiry Message and Notification of Expiry Message were updated to show the App name. 

- BCv21 App - The Product Activation Page was updated to point to the new CRM URL. 

- BCv21 App - A report was created to output record fields as XML in EDI format. This xml output can be used to create/update data builders. 

- BCv21 App - The SD Interface EDI File List was created to display blob files in EDI azure blob storage where users can set up custom filters and save the filtered pages as views. 

- BCv21 App - True Commerce Default Messages for release with SD Interface EDI were created for EPOD, Inbound Sales Order, and Sales Invoice document types. 

- BCv21 App - Celtrino Default Messages for release with SD Interface EDI were created for  Inbound Sales Order, Sales Invoice, Sales Credit Note, and Advanced Shipping Notice. 

- BCv21 App - A page was created to show the users the files that are waiting to be processed on the Azure Storage. This page was surfaced on the Role Centre via an action captioned Azure File List. 

- BCv21 App - A URL link was added to the SD EDI Interface Setup Card from where users can download Microsoft Azure Storage Explorer. 

- BCv21 App - Changes were made to SD Interface EDI to allow for the creation of Master Data Outbound Files. 

- BCv21 App - The Pending EPOD list of Sales Orders based on an active EPOD message queue was reviewed. 

- BCv21 App - Fields on the History List were recaptioned in line with changes made on the Queue Entry page. 

- BCv21 App - The Process Log action caption in the Related group of the Setup Card was updated. 

- BCv21 App - Changes were made to the menu actions in the SD EDI File Structure Engine List. The View Content and View Info actions were missing. 

- BCv21 App - Menu Action Groups were removed in the File Structure Engine Card to allow for easier access to and visibility of actions. 

- BCv21 App - Changes were made to the steps to create a new version of a File Structure Engine. 

- BCv21 App - Changes were made to the File Structure Engine Card to promote the Code field and Direction to the General FastTab. 

- BCv21 App - Menu Action Groups in the Data Builder Card were removed for easier visibility of, and access to, the actions on the page. 

- BCv21 App - A change was made to the Data Builder Card to promote the Code field and Document Type to the General FastTab. 

- BCv21 App - A change was made to the Data Builder Card to promote the Code field and Document Type to the General FastTab. 

- BCv21 App - The menu action groups were removed from the Field Mapping Card for easier visibility of the actions on the page. 

- BCv21 App - Menu Action Groups were removed in the EDI Field mapping List to allow for easier access to, and visibility of, actions. 

- BCv21 App - Changes were made to the steps for creating a new version of a Field Mapping file. 

- BCv21 App - The action to delete the version line in the Versions SubList on the Data Builder Card was removed. Users have to import lines to up the version and keep track of changes made. 

- BCv21 App - Changes were made to the flow of creating a new version of a Field Mapping file. Importing a Field Mapping File creates a new version. 

- BCv21 App - Changes were made to the menu actions in the EDI Data Builder List to allow for easier access to, and visibility of, actions. 

- BCv21 App - Changes were made to the Actions on the Message Types list for easier visibility of the functionality. 

- BCv21 App - Field Mapping and Data Builder for True Commerce Sales Invoice was created. 

- BCv21 App - Fields were added and fields renamed on the SD Interface EDI Worksheet. 

- BCv21 App - Fields were added and other fields were renamed on the SD Interface EDI Queue SubList page. 

- BCv21 App - Fields on the Queue Entry page were renamed. Peer Type to Type. Peer Key to No. Peer to Name. 

- BCv21 App - In the EDI Worksheet and the EDI Queue the Card action was renamed to Queue Entry. 

- BCv21 App - The Queue Card was renamed to Queue Entry.  

- BCv21 App - A small typo was fixed on an action in the VAN Card. 

- BCv21 App - The actions in VAN Card were moved from a menu group to the menu to allow for easier access to the actions on the card. 

- BCv21 App - The VAN Code field in the VAN Card was set to promoted in the General FastTab. 

- BCv21 App - Promote fields in SD Interface EDI Setup Card FastTabs. 

- BCv21 App - The link in the ToolTips was updated to our new website. 

- BCv21 App - Added filters to the EDI EPOD Files page to show EPOD files only. 

- BCv21 App - Reviewed the CEL_ORD Message Type with CSV_IN File Structure Engine Code. 

- BCv21 App - Reviewed the True Commerce TRCM_ORD Message Type with XML_IN File Structure Engine Code. 

- BCv21 App - Reviewed the CREDIT_NOTE Data Builder with CEL_CN Message Type. 

- BCv21 App - Reviewed the CREDIT_NOTE Data Builder with TC_CN Message Type. 

- BCv21 App - Reviewed the SALES_SHIPMENT Data Builder with TC_ASN Message Type. 

- BCv21 App - Reviewed the CEL_ASN Message Type and regeneration of ASN Messages after files were processed and logged to History. 

- BCv21 App - Reviewed the SALES_INVOICE Data Builder with the TC_INV Message Type. 

- BCv21 App - Reviewed the SALES_INVOICE Data Builder with GXS_INV Message Type. 

- BCv21 App - The EDI files generated and placed out in the Azure folders were using the Document Number and not the specified number sequence. 

- BCv21 App - The SALES_INVOICE Data Builder with CEL_INV Message Type was reviewed. 

- BCv21 App - Functionality was added not to create blank folder names in file paths when a user inserts too many backslashes in the file path. 

- BCv21 App - The menu groups were removed from the SD EDI Interface Worksheet to allow easier access to the actions on the page. 

- BCv21 App - The SD EDI Worksheet was surfaced on the SD Interface EDI Role Centre. 

- BCv21 App - The action to delete the line in the Engine Versions SubList on the File Structure Engine Card was removed. Users can import files or create a new line and up the version of the File Structure Engine rather than delete the version. 

- BCv21 App - The Document Type on the Message Card was changed from P.O.D. Confirmation to POD Confirmation. 

- BCv21 App - Some small typos were fixed on the Message Card. 

- BCv21 App - The Card Action on the Messages ListPart on the Peer Card was removed as there is an Edit and a View action on the ListPart. 

- BCv21 App - The VAN field caption on the Peer card was updated from V.A.N. to VAN. 

- BCv21 App - In the VAN Card the Enabled option was moved to the General FastTab. 

- BCv21 App - Captions in the EDI Statistics FactBox were changed. 

- BCv21 App - A new file for the SD Interface EDI Message Types to use in the Assisted Setup action for version 6.0.0 of SD Interface EDI was created.  

- BCv21 App - Captions in the Testing FastTab on the SD Interface EDI Setup Card were updated. 

- BCv21 App - The action to delete the version line in the Versions SubList on the Field Mapping Card was removed. Users have to import lines to up the version and keep track of changes made. 

#### Bug Fixes

- BCv21 App - An error was raised in the Assisted Setup import if non sequential enum values exist in the imported data. This was fixed. 

- BCv21 App - Incoming Purchase Order Confirmations with errors were not displayed in the Purchase Order Confirmation list. 

- BCv21 App - Actions were recaptioned on the Role Centre and the duplicate Sales Orders action was removed. 

- BCv21 App - The Document Type for Sales Order Acknowledgement, Purchase Order and Purchase Order Confirmation did not show up in the History Documents list. This was fixed. 

- BCv21 App - In the EPOD List, drilling through on the Missing Orders cue when there was a flowfield value raised an error that there were no orders found to show. This was fixed. 

- BCv21 App - A change was made to the ISV Licence Notification procedure in SD Interface EDI to fix an issue that would raise an error when the language is changed from English to another language. 

- BCv21 App - Fixed an issue where choosing Create Inbound Message in Worksheet with no files in inbound folders raised a specified blob did not exist error. 

- BCv21 App - When processing Outbound Files an attempted to divide by zero error was raised. This was related to the progress dialog and was fixed. 

- BCv21 App - Inbound Messages were being created for a disabled VAN. This was fixed. 

- BCv21 App - Inbound processing was not picking up files at the VAN inbound container level. This was fixed. 

- BCv21 App - The Reprocess queue was not removing temp components from the blob container. This was fixed. 

- BCv21 App - When History files were reprocessed Outbound Messages were not recreated. This was fixed. 

- BCv21 App - A fix was made to an error that was raised when importing a new version of a File Structure Engine that contained a value EPOD_IN. 

- BCv21 App - A Ping Pong message was displaying in the SD Interface EDI Role Centre. 

- BCv21 App - A fix was made to the code for licence key checks on the SD Interface EDI Role Centre. 

- BCv21 App - Deleting multiple queues in the EDI Worksheet using the Remove Selected action raised an error. This was fixed. 

- BCv21 App - An issue was fixed where importing file/creating new File Structure Engine version threw a rec already exists error. 

- BCv21 App - An issue was fixed where the message number series defined for the message was not used as the filename when the outbound files were created.  

- BCv21 App - Documents that were successfully processed through the EDI Queue and moved to History were being recreated again in the EDI Worksheet. This was fixed. 

- BCv21 App - Updating a Code on the VAN Card raised an error. 

- BCv21 App - Drilling down on the Versions field on the Version SubList in the Field Mapping Card showed the Stores page. This drilldown was removed. 

- BCv21 App - The Product Activation page was changed to disable the Activate button unless the Product Key is filled in to avoid an error being raised when Activate is chosen. 

- BCv21 App - The code was reviewed to ensure that Inbound processing of multiple document files was deleting the file post-processing. 

### 5.1.1

#### Enhancements

- Added A VAT Line Identifier.

### 5.1.0

#### Enhancements

- Ported NAV2013R2 code base to NAV2016.

### 5.0.1

#### Enhancements

- Update Documentation.

### 5.0.0

#### Enhancements

- Created a Demo Configuration.
- Created an About Page.
- Created an XML Processing XSLT Engine.
- Made change whereby the Root folder on the System Setup decides, based on codes, the sub folders to use. Boolean option on VANto override.
- Added import/export just for Field Mappings. Split Engine/Template to just export Engine on Engine export.
- Changed Type: Sales Invoice for inbound to Sales Order.
- Added Direction to File Structure Engine.
- Created Message and Message Types. Split Document Type to Message and Message Type. Assign Message to Peer.
- Added functionality whereby instead of removing a Batch or Document, allow it to be forced to process.
- Renamed nodes and restructured Data Builder.
- Created XMLPort to upgrade from Version 4 to Version 5 of SD EDI.
- Renumbered objects.
- Generated EDI Help files
- Changed Table order and renamed. Renamed and renumbered Pages related to tables.
- Removed Record IDs and instead used link to Table Primary Keys.
- Moved data generation to on creation of Queue item, not during processing.
- Created Worksheet Page for SD EDI.
- Codeunit restructure around Queue functionality.
- Job Queue Management.
- Created Data Link.
- Improved XSLT Error handling.
- Made a change to Data Link.
- Created List Page for XSLT Version Table (For Lookup).
- Changed Group Document to "Single Document Per File".
- Reviewed and cleaned up all Page layouts.
- Added setup sections for Peers and VANs to the Navigation Pane.
- Removed Source Table from Queue detail, use Document Type to determine Source Table.
- Created a repeater on Worksheet instead of sub-Page.
- Settled on Document Types and ensured all Document Types fields are consistent.
- Port the NAV2013R2 codebase to NAV2016.

#### Bug Fixes

- Fixed Bug where Blank lines were allowed on VAT Identifiers.
- Removed wildcards from VAT Identifiers.

### 4.2.0

#### Enhancements

-  Made improvements to the general Page flow.
- In the VAN List Page add Actions and a Statistics FactBox.
- In the VAN Card add Actions and a Statistics FactBox.
- In the Peers List Page add Actions, add a Statistics FactBox and remove display fields.
- In the Peer Card, move the Stores FastTab, add an Action, and add a Statistics FactBox.
- For the Templates and Engines, create In-Use Statistics for Peers and VANs.
- Setup Page. Add links to Log and History. Changes to Version List for Template/Engine.
- Changes to the History Page.
- Added warning message if Items are in Test mode when processing.
- Created Data XMLPort.
- Allowed removal of a document from a History batch.
- Fixed VAT calculations. Added filename to History List.
- Excluded zero amount Invoices.
- Moved Export/Import serialization to XMLPorts for All Setup tables.
- Moved Export/Import serialization to XMLPorts for Engines.
- Added custom VAT look up. Created a custom look up for a custom VAT Identifier based on VAT Bus. Group, VAT Prod Group, VANand Document Type.
- Created a third item lookup. Created an additional fall through lookup for item codes when creating orders.
- Included Item data within Canonical XML.
- Created functions on Inbound processing to allow current date to be set on Inbound processing.

#### Bug Fixes

- Included the Item No and the Barcode when an on inbound Item not found error is raised.
- Fixed Page Captions, Page and Table Names.
- Removed the Create New and the Edit Selected Actions from the VAN Card Page.
- Created sub lists for Document Types and Peers to resolve the Document/Stores on the Peer Card update issue.
- Fixed Queue Display bug.

### 4.1.1

#### Enhancements

- Implemented Atlas Mappings.
- Allow deletion of Queue Item.
- Removed Alternative Supplier GLN.
- Template Adjustments.
- Added function to CSV Outbound Engine to remove any commas within the data.
- Created Declaration for xml documents to utf16 for all XML documents.
- Adjusted length for UOM, Credit Notes and Invoices.
- Made adjustments for save to stream.
- Added fixed length inbound Engine.
- Adjusted Tradacoms Invoice and Credit Notes.
- Adjusted Sales Order inbound Template.
- Created Customer filter from documents on Create Outbound Messages.
- Created Document number filter on create Outbound Messages.

#### Bug Fixes

- Added VAN to the key on the Peer child tables.
- Added Table Relation to Document Type Peer Field.
- SD-EDI Queue Inbound Codeunit refactoring.
- SD-EDI Create Inbound Codeunit refactoring.
- SD-EDI Queue Outbound Codeunit refactoring.
- SD-EDI I/O Codeunit refactoring.
- When creating outbound items, validate the Document Type and Engine versions. If not valid, log a warning and skip the item.
- Fixed file numbering bug.
- Split Sub folder to inbound and outbound sub folder on the peer.
- Created Celtrino EDIT Credit Note Template.
- Fixed transfer fields from XML bug.
- Fixed rounding issue on footer fields for Celtrino.
- Fixed Celtrino ASN Generation bug.

### 4.1.0

#### Enhancements

- Implemented the GXS Outbound Sales Invoice format.
- Implemented the GXS Inbound Sales Order format.
- Added a Description field to the Peer.
- Added an Alternative GLN field.

#### Bug Fixes

- Fixed bug in non multi-document file generation - when Peer is set to non multi-document, a single file is still generated.
- Fixed File Import bug - when re-importing a Mapping/Engine, the data is not refreshed.

### 4.0.0

#### Enhancements

- Job Queue - altered the OnRun method of the main code unit.
- Added Base Unit of Measure for the Item for the Tradacoms Template.
- Developed the Inbound Engine around the Celtrino Inbound Sales Order.
- Implemented the XSLT Engine and Template naming convention.
- Encoded the File Mappings and Engines for export.
- Action Items on Queue list in Role Center.
- Updated Templates for the Peer/Document Type split.
- Peer split - item generation. Made changes to the item generation Engine to handle the Peer/Document Type split. A Message forthe Queue will be generated per VAN/Document Type combination.
- Peer split - processing engine. Made changes to the processing Engine to handle the Peer/Document Type split.
- Peer split - updated the Message List and Card to reflect the Peers. Generated Document Type Card and List.
- Peer split - tables. Split the Message table into Peers and Document Types.
- Adjusted the import/export functionality to handle the Peer/Document Type Split.
- Created a custom field on the EDI Setup for a Company Code.
- Added the Customer Name to the Message format and Stores. Added a free text description on the Message formats.
- Added a section to the Tradacoms outbound Invoice Template.
- Tradcoms Outbound ASN.
- Celtrino Outbound ASN.
- Tradacoms Inbound Order.
- Developed User Role Center.
- Created EDI Template Pages.
- Created EDI Engine Pages.
- Created tables.
- Created EDI Setup Page.
- Created CSV Engine.
- EDI Engine.
- Core features. Reprocessing Messages, logging of user and system actions, batching option or single document option based onVAN/Entity/Document Type, event system for posted documents, inbound/outbound processing list, different file formats(Templates) and Document Types, multiple VANS.

#### Bug Fixes

- Filter out deleted Posted Sales Invoices when creating items for the Queue.

### 1.1.0

#### Enhancements

- Implemented Outbound formats for Tradacoms Invoice and Credit Notes; Celtrino Outbound ASN; Tradacoms ASN.
- Implemented the Inbound structures for Sales Orders for the Celtrino and Tradacoms formats.
- Implemented the structures and formats for the Tradacoms Outbound Sales Invoice.
- Adjusted the Celtrino Templates to use the new engine calculation functions.
- Added functionality to generate multi-batches. Split batches based on Document Types when generating the batch Queues.
- Implemented the structures and formats for the Tradacoms Outbound Sales Credit.

#### Bug Fixes

- Fixed functionality to allow to process multiple invoices per file.
- Fixed error on processing multiple batches.

### 1.0.0

#### Enhancements

- The initial release only handles outbound Sales Invoices in a Celtrino format.



