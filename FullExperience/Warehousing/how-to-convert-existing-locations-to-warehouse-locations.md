---
title: "How to: Convert Existing Locations to Warehouse Locations"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "warehouse, locations"
  - "warehouse management, enabling locations"
  - "locations, creating warehouses"
ms.assetid: 772f3fd9-162c-4979-b157-111474df6179
caps.latest.revision: 6
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
# How to: Convert Existing Locations to Warehouse Locations
You can enable an existing inventory location to use zones and bins and to operate as a warehouse location.  
  
 The batch job to enable a location for warehouse operation creates initial warehouse entries for the warehouse adjustment bin for all items that have inventory in the location. These initial entries will be balanced when warehouse physical inventory entries are entered after the batch job is run.  
  
 You can create zones and bins either before or after the conversion. The only bin that you must create before the conversion is the one that is to be used as the future adjustment bin.  
  
> [!IMPORTANT]  
>  To clear all negative inventory and any open warehouse documents before you convert the location for warehouse handling, run a report to identify the items with negative inventory and open warehouse documents for the location. For more information, see [Check on Negative Inventory](../Topic/\($%20R_5757%20Check%20on%20Negative%20Inventory%20$\).md).  
  
### To enable an existing location to operate as a warehouse location  
  
1.  In the **Search** box, enter **Create Warehouse Location**, and then choose the related link.  
  
2.  In the **Location Code** field, specify the location that you want to enable for warehouse processing.  
  
3.  In the **Adjustment Bin Code** field, specify the bin at the location where unsynchronized warehouse entries are stored. For more information, see [Warehouse Adjustment Bin](../WarehouseActivities/warehouse-adjustment-bin.md).  
  
     Using the open item ledger entries for the specified location, warehouse journal lines are created that sum up every combination of Item No., Variant Code, Unit of Measure Code, and, if necessary, Lot No. and Serial No. in the item ledger entries. The warehouse journal lines are then posted. This posting creates warehouse entries that place the inventory in the warehouse adjustment bin. The **Adjustment Bin Code** on the location card is also set.  
  
4.  To see which items were added to the adjustment bin during the batch job, run the **Warehouse Adjustment Bin** report. For more information, see [How to: Post Quantity Adjustments for Bins](../WarehouseActivities/how-to-post-quantity-adjustments-for-bins.md).  
  
5.  When the **Create Warehouse Location** batch job has completed, perform and post a warehouse physical inventory. For more information, see [How to: Perform Warehouse Physical Inventories](../WarehouseActivities/how-to-perform-warehouse-physical-inventories.md).  
  
> [!NOTE]  
>  It is recommended that you run the **Create Warehouse Location** batch job at a time when it will not impact the daily work in the system. This job processes each entry in the **Item Ledger Entry** table, and if there are a large number of item ledger entries, the job can last several hours.  
  
 For those locations that did not use warehouse management documents before the conversion, you must re\-open and release any source documents that were partially received or partially shipped before the conversion.  
  
## See Also  
 [How to: Set Up Locations to Use Bins](../WarehouseActivities/how-to-set-up-locations-to-use-bins.md)   
 [How to: Set Up Warehouse Management](../WarehouseActivities/how-to-set-up-warehouse-management.md)