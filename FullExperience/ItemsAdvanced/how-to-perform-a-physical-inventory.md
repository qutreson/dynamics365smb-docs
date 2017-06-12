---
title: "How to: Perform a Physical Inventory"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical counts"
  - "journals, physical"
ms.assetid: 66277f56-a36a-464f-ad03-9aa08b99800d
caps.latest.revision: 11
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Perform a Physical Inventory
You must take a physical inventory, that is, count the actual items on hand, to check if the quantity registered is the same as the physical quantity in stock at the end of a fiscal year, if not more often. If there are differences, you must post them to the item accounts before you do the inventory valuation.  
  
> [!IMPORTANT]  
>  This topic describes how to perform a physical inventory in a non\-directed warehouse setup. For information on how to perform it in a warehouse setup with directed put\-away and pick, see [How to: Perform Warehouse Physical Inventories](../WarehouseActivities/how-to-perform-warehouse-physical-inventories.md).  
  
 Apart from the physical counting task, the complete process involves the following three tasks:  
  
-   Calculate the expected inventory.  
  
-   Print the report to be used when counting.  
  
-   Enter and post the actual counted inventory.  
  
### To calculate the expected inventory  
  
1.  In the **Search** box, enter **Phys. Inventory Journal**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Calculate Inventory**.  
  
3.  In the **Calculate Inventory** window, on the **Options** FastTab, specify the conditions to use to create the journal lines, such as whether to include items that have zero recorded inventory.  
  
4.  Set filters if you only want to calculate inventory for certain items, bins, locations, or dimensions.  
  
5.  Choose the **OK** button.  
  
> [!NOTE]  
>  The item entries are processed according to the information that you specified, and lines are created in the physical inventory journal. Notice that the **Qty. \(Phys. Inventory\)** field is automatically filled in with the same quantity as the **Qty. \(Calculated\)** field. With this feature, it is not necessary for you to enter the counted inventory on hand for items that are the same as the calculated quantity. However, if the quantity counted differs from what is entered in the **Qty. \(Calculated\)** field, you must overwrite it with the quantity actually counted.  
  
### To print the report used when counting  
  
1.  In the  **Phys. Inventory Journal** window containing the calculated expected inventory, on the **Actions** tab, in the **General** group, choose **Print**.  
  
2.  In the **Phys. Inventory List** window, on the **Options** FastTab, specify if the report should show the calculated quantity and if the report should list inventory items by serial\/lot numbers.  
  
     For more information, see [Phys. Inventory Journal](../Topic/\($%20N_392%20Phys.%20Inventory%20Journal%20$\).md).  
  
3.  On the **Item Journal Batch** FastTab, set filters if you only want to print the report for certain items, bins, locations, or dimensions.  
  
4.  Choose the **Print** button.  
  
 Employees can now proceed to count inventory and record any discrepancies on the printed report.  
  
### To enter and post the actual counted inventory  
  
1.  In the **Search** box, enter **Phys. Inventory Journal**, and then choose the related link.  
  
2.  On each line where the actual inventory on hand, as determined by the physical count, differs from the calculated quantity, enter the actual inventory on hand in the **Qty. \(Phys. Inventory\)** field.  
  
     The related fields are updated accordingly.  
  
    > [!NOTE]  
    >  If the physical count reveals differences that are caused by items posted with incorrect location codes, do not enter the differences in the physical inventory journal. Instead, use the reclassification journal or a transfer order to redirect the items to the correct locations. For more information, see [Item Reclass. Journal](../WarehouseActivities/-$-n_393-item-reclass.-journal-$-.md) or [How to: Create Transfer Orders](../DesignAndEngineering/how-to-create-transfer-orders.md).  
  
3.  To adjust the calculated quantities to the actual counted quantities, on the **Actions** tab, in the **Posting** group, choose **Post**.  
  
     Both item ledger entries and physical inventory ledger entries are created. Open the item card to view the resulting physical inventory ledger entries.  
  
4.  In the **Search** box, enter **Items**, and then choose the related link.  
  
5.  Open the item card in question, and then, on the **Navigate** tab, in the **Item** group, choose **Phys. Inventory ledger Entries**.  
  
## See Also  
 [Phys. Inventory Journal](../Topic/\($%20N_392%20Phys.%20Inventory%20Journal%20$\).md)   
 [How to: Perform Warehouse Physical Inventories](../WarehouseActivities/how-to-perform-warehouse-physical-inventories.md)   
 [Design Details: Integration with Inventory](../ApplicationDesign/design-details-integration-with-inventory.md)