---
title: "How to: Create Put-aways from Internal Put-aways"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "picking, creating"
  - "putting away, without a source document"
  - "inbound warehouse, putting away"
  - "outbound warehouse, picking"
  - "picking, without a source document"
  - "internal picks"
  - "internal put-aways"
ms.assetid: 897e8aa2-a592-47b9-8965-acb9c371de80
caps.latest.revision: 7
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
# How to: Create Put-aways from Internal Put-aways
After items have been put away and before they are picked to fulfill the needs of a production order or shipment, they are stored in the warehouse as part of available inventory.  
  
 Situations can arise where items must be taken out of the warehouse pick bins temporarily, perhaps to serve as demonstration models in a sales presentation. These items are still owned by the company and are part of inventory, but they are not available for picking. They are registered in a special purpose bin that you create for this purpose; technically, the items are in the warehouse, but physically, they could be in a conference or demonstration room.  
  
 In another situation, the production unit might unexpectedly need a few parts for a process. You can pick items for the production bins using the internal pick. When the process is over and output is created, you post the consumption of the items and empty the production bin, which in turn decreases the quantity of the item at your location.  
  
 Likewise, items can be returned to the warehouse to be put away. The items may have been taken out of available inventory for a production order, and then not used at all. To make them part of available inventory again, they must be put away in the bin.  
  
 The options **Internal Picks** and **Internal Put\-aways** enable you to perform picks and put\-aways without having to refer to a particular source document. In both of these options, you can easily set up all the information you need to create a pick or put\-away warehouse instruction.  
  
> [!NOTE]  
>  If you are not using internal picks and internal put\-aways, these adjustments can be performed using the methods to move items from bin to bin or to post quantity adjustments in a bin.  
>   
>  When the location uses directed put\-away and pick, and therefore uses bin types, you cannot manually move items in or out of a bin of bin type RECEIVE, because items that are in a RECEIVE\-type bin must be registered as being put away before they are part of available inventory.  
  
### To create a pick from the internal pick  
  
1.  In the **Search** box, enter **Whse. Internal Pick**, and then choose the related link.  
  
2.  Fill in the **No.** field and the **To Bin Code** field on the **General** FastTab. The **To Bin Code** field specifies the bin from which you want to get the items. For production purposes, this bin would be the inbound production bin or the open shop bin. For other purposes, choose a To Bin Code of a bin type that is not used for picking, most likely a staging, shipping or special purpose bin.  
  
3.  Select an item in the **Item No.** field, and fill in the quantities you want to pick.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Create Pick.** A warehouse pick instruction is now ready for a warehouse employee to perform.  
  
### To create a put\-away from the internal put\-away  
  
1.  In the **Search** box, enter **Whse. Internal Put\-away**, and then choose the related link.  
  
2.  Fill in the **No.** and **From Bin Code** fields on the **General** FastTab. The **From Bin Code** field specifies the bin where the items being returned to the warehouse, perhaps from production, are located.  
  
3.  Fill in the item numbers and quantities on the lines.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Create Put\-away**. A warehouse put\-away instruction is now ready for a warehouse employee to perform.  
  
## See Also  
 [Whse. Internal Pick](../Topic/\($%20N_7357%20Whse.%20Internal%20Pick%20$\).md)   
 [Whse. Internal Put\-away](../Topic/\($%20N_7354%20Whse.%20Internal%20Put-away%20$\).md)   
 [Move Items](../WarehouseActivities/move-items.md)   
 [How to: Post Quantity Adjustments for Bins](../WarehouseActivities/how-to-post-quantity-adjustments-for-bins.md)   
 [How to: Register Quantity Adjustments in Warehouse Item Journals](../WarehouseActivities/how-to-register-quantity-adjustments-in-warehouse-item-journals.md)