# Spreadsheet Mail Merge - Group Data


When performing a <a href="http://help.devexpress.com/#WindowsForms/CustomDocument16257">mail merge</a> with the <a href="http://help.devexpress.com/#WindowsForms/clsDevExpressXtraSpreadsheetSpreadsheetControltopic">SpreadsheetControl</a>, you can sort data to be merged and split it into groups based on identical values in the specified data field.<br>This example contains the<a href="http://help.devexpress.com/#WindowsForms/CustomDocument17018"> mail merge template</a> to generate invoices using data from the <strong>Invoices</strong> view of the <strong>Northwind</strong> database. The <em>nwind.mdb</em> database file is included in the project. This file ships with the XtraSpreadsheet Suite installation. The template is bound to the data source via the <a href="http://help.devexpress.com/#CoreLibraries/DevExpressSpreadsheetIWorkbook_MailMergeDataSourcetopic">IWorkbook.MailMergeDataSource</a> and <a href="http://help.devexpress.com/#CoreLibraries/DevExpressSpreadsheetIWorkbook_MailMergeDataMembertopic">IWorkbook.MailMergeDataMember</a> properties in code.<br><br>Run the application and review the prepared template (the <em>MailMergeTemplate_GroupData.xlsx</em> file) that is automatically loaded into the SpreadsheetControl.<br>On the <strong>Mail Merge</strong> tab, enable the <strong>Mail Merge Design View</strong> to highlight the template structure. The template consists of the following ranges.<br>- <strong>Header</strong><br>The <strong>Header</strong> range contains the current date to be displayed above each invoice.<br>- <strong>Detail<br></strong>The <strong>Detail</strong> range contains fields for merging order data (general order information, products ordered and order totals). In this range, the <strong>OrderID</strong> data field is set as a criterion for sorting data. To make sure of this, check that the <strong>OrderID</strong> field is displayed in the <strong>Sort Fields</strong> dialog (to invoke this dialog, select any cell within the <strong>Detail</strong> range and click the <strong>Sort Fields</strong> button on the <strong>Mail Merge</strong> tab), and the SORTFIELD0 <a href="http://help.devexpress.com/#WindowsForms/CustomDocument14691">defined name</a> for the <strong>OrderID</strong> field is added to the worksheet's collection of defined names (you can see this defined name in the <strong>Name Manager</strong> dialog when you click the corresponding button on the <strong>Formulas</strong> tab).<br>- <strong>GroupHeader<br></strong>All general information for a group of records is located within the <strong>GroupHeader0</strong> range. In this example, each group is an order. Thus, the group header contains information about the order, customer, salesperson, dates, delivery, etc. The existing <strong>OrderID(Ascending)</strong> sort field is used as a criterion for creating groups in the merged document (this sort field was selected when the <strong>GroupHeader</strong> range was created). In the <strong>Name Manager</strong> dialog, you can see the GROUPHEADER0 defined name that corresponds to this group header range.<br>- <strong>GroupFooter</strong><br>The <strong>GroupFooter0</strong> range displays totals at the end of a group of records (in other words, at the end of an order). It is also created based on the <strong>OrderID(Ascending)</strong> sort field and saved in the template document as a defined name (GROUPFOOTER0).<br>In this template, the mail merge mode is set to <strong>Multiple Sheets</strong>. Thus, each order will be inserted in a separate worksheet. To review the result, click the <strong>Mail Merge Preview</strong> button on the <strong>Mail Merge</strong> tab.

<br/>

