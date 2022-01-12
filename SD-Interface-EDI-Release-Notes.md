## SD Interface EDI Releases

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

