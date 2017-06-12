---
title: "How to: Create Tax Registers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax registers"
  - "tax registers, sections"
  - "tax registers, creating"
  - "tax journals"
ms.assetid: a4f4a66c-56ca-49aa-8e18-a56581aabb6c
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Create Tax Registers
The following procedure shows how to create tax registers.  
  
1.  Click **Financial Management**, click **Tax Accounting**, click **Setup**, click **Tax Register**s, and then click **Sections**.  
  
2.  In the **Tax Register Sections** form, click the **Functions** button.  
  
3.  Select one of the following fields:  
  
    -   **Copy Section** \-Copies data from one tax register to another.  
  
    -   **Clear Registers** \-Clears data already created in the tax registers and is used for debugging conditions to re\-count tax registers.  
  
    -   **Create Registers** \-Creates data in the tax registers**.**  
  
4.  To create data, click **Create Register**. The **Tax Register Create** form opens.  
  
5.  On the **General** tab, enter the fields described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**Periodicity**|Enter a period to create data in tax accounting registers. The allowed values are:<br /><br /> -   **Month**<br />-   **Quarter**<br />-   **Year** **Note:**      If you select a month, the data in the selected registers will be created especially for that month. If you select a quarter, the data will be created for each of the three months of that quarter. If you select a year, the data will be created for each of the 12 months of that year.|  
    |**Accounting Period**|The value entered in this field depends on the value selected in the Periodicity field. Select the accounting period \(**Month**, **Quarter**, or **Year**\).|  
    |**From, To**|These fields are filled in automatically and show start and end dates of the chosen period.|  
    |**G\/L Entries, Vend's\/Cust's, Items, Fixed Asset, Fut. Exp., Payroll, Templates**|Select the fields to calculate registers of the appropriate type.|  
    |**Status**|This field displays information about the version of the tax register.|  
    |**Starting Date, Ending Date**|This field displays the dates given when setting the tax register version.|  
  
6.  Click **OK** to create the tax register.  
  
    > [!NOTE]  
    >  If the creation of registers for an already counted period is selected, a warning is displayed. At this stage of the tax register creation, it is possible either to continue counting and delete all existing data, or stop.  
  
7.  To view the calculated information in the **Tax Register Accumulation** form, click **Financial Management**, click **Tax Accounting**, click **Reporting,** and then click **Profit Tax**.  
  
8.  Using the register list, you can view the contents of any register or using the arrows at the top of the window, you can view the information going from one register to another.  
  
9. With the arrows and buttons in the lower\-left corner of the window, you can view the contents of the registers for previously counted periods.  
  
10. Click the **Drill\-down** button in the **Amount** field to view the sources based on which this was counted. A source can be a tax register or a list of transactions forming this amount, depending on the settings. If the source forming the sum is a tax register, click the **Drill\-down** button to open the window where the source tax register information is displayed. Then click the **Drill\-down** button in the **Amount** field on this form to get a list of transactions forming the amount.  
  
11. Select a document and click **Navigate** to get all the transactions of the selected document.  
  
12. Click **Show** to view all the transactions of any entry ledger that is created.  
  
## See Also  
 [Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-accounting.md)   
 [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md)   
 [How to: Set Up Tax Register Sections](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-tax-register-sections.md)   
 [Collecting Profit Tax Information for Tax Declaration](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/collecting-profit-tax-information-for-tax-declaration.md)