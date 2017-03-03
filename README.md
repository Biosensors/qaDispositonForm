# qaDispositonForm
QA Disposition Form

This file is used by the warehouse to processes returns (RGAs) and create the disposition form for the QA department. 
Note: this file is documented in agile (ECO-and needs to be maintained accordingly.
How to use it
When the warehouse received a return, they need to create a QA disposition form. The user opens the Excel file and fills out all the fields in the “QA dispo Follow up” tab. When done, the user clickes on the “Start Scanning” button and scans all of the products they have received. If a given product cannot be scanned (for various reasons, such as missing/unreadable bar code, non-barcoded product, etc.) the user may click on the “Add Manual Entry” button in order to enter the product’s information. The user must select the status of each product in column “K”. There are some rules for final dispositions (based on product status, UBD, etc.) which may be manually copied over to the “Final Disposition” column (column “O”) by clicking the “Copy suggested disposition to Final disposition” button. When done, the user clicks on “Print”. The default printer set in Windows is used to print this document.
Notes for developers
As this file is part of QA, it needs to have a certain level of error control. When the user enters a product’s reference manually, the programs checks whether this is a valid product. In order to do that, the “ZMMMR_SAP_SQL_EXPORT_MM” SAP job is running daily and exports the list of all the materials and their batches to the “Z_ExcelSolutions” database’s “ZMM_SQL_MATLICHA” on server “MOSQ04.besa.bsi.corp”. If the value entered by the user isn’t recognized, the program won’t go any further.
When printing, a set of sub procedures is called, creating a specific layout, such as depicted in agile. 
Code / project source
\\mofasa.besa.bsi.corp\shared\IT\BESA\Peter's Projects\QA Disposition
