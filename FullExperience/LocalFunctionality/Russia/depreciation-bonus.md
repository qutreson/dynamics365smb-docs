---
title: "Depreciation Bonus"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "depreciation bonus, setting up"
  - "depreciation bonus, canceling"
  - "depreciation bonus, calculating"
ms.assetid: 4c299d98-ca5d-42aa-b970-a0cb4faeb6df
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Depreciation Bonus
*Depreciation bonus* is an accelerated depreciation method applied in tax accounting because of provisions in the Russian tax laws. A depreciation bonus enables you to include fixed asset and capital investment expenses in the current period at the rate of 10 percent or 30 percent.  
  
## Depreciation Bonus Calculation  
 A depreciation bonus can be calculated and applied for the following types of transactions:  
  
-   Acquisition costs of fixed assets.  
  
-   Acquisition costs and appreciation of capital investments for all previous periods excluding the current period.  
  
 The rate of the depreciation bonus is 10 percent or 30 percent, depending on the class of the fixed asset. The rate is set for a depreciation group using the **Depr. Bonus Percentage** field in the **Depreciation Group** window.  
  
 After the depreciation bonus is calculated and posted for a period, all transactions are cleared in preparation for the next period.  
  
## Depreciation Bonus Settings  
 Before depreciation bonus is calculated, you will have to make sure that the appropriate settings have been applied in the **Tax Register Setup** window. Use the information in the following table to apply depreciation bonus settings.  
  
|[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|---------------------------------|---------------------------------------|  
|**Rel. Act as Depr. Bonus Base**|Select if you want fixed asset releases to be used to calculate the depreciation bonus base.|  
|**Depr. Bonus TD Code**|Enter a tax difference code that is used to calculate the depreciation bonus. The selected tax difference code should be identified as a depreciation bonus during tax difference setup.|  
|**Depr. Bonus Recovery from**|Enter the starting date from which depreciation is recovered if the fixed asset is sold. If the fixed asset is sold before this date and the depreciation bonus has already been applied, the depreciation bonus will not be recovered.|  
|**Depr. Bonus Recov. Per. \(Year\)**|Enter the period in which the depreciation bonus is recovered if the fixed asset is sold.|  
|**Depr. Bonus Recovery TD Code**|Enter the tax difference code that is used to calculate the depreciation bonus recovery amount in tax accounting.|  
  
## Selecting and Canceling Depreciation Bonus Transactions  
 Depreciation bonus transactions should be posted before the monthly depreciation amount is calculated and posted.  
  
 To select depreciation bonus transactions for posting for a period, select **Depr. Bonus** in the [Fixed Asset Journal](../Topic/\($%20N_5629%20Fixed%20Asset%20Journal%20$\).md) window and the [Fixed Asset G\-L Journal](../Topic/\($%20N_5628%20Fixed%20Asset%20G-L%20Journal%20$\).md)window.  
  
 You can cancel depreciation bonus transactions by running the **Cancel FA Ledger Entries** batch job. After posting the depreciation bonus cancellation, all operations that are included in the depreciation bonus base must be manually selected as the depreciation bonus base.  
  
## See Also  
 [How to: Create Fixed Assets](../../Finance/how-to-create-fixed-assets.md)   
 [Fixed Asset Card](../Topic/\($%20N_5600%20Fixed%20Asset%20Card%20$\).md)   
 [Fixed Asset Journal](../Topic/\($%20N_5629%20Fixed%20Asset%20Journal%20$\).md)   
 [Fixed Asset G\-L Journal](../Topic/\($%20N_5628%20Fixed%20Asset%20G-L%20Journal%20$\).md)   
 [FA Depreciation Book](../Topic/\($%20T_5612%20FA%20Depreciation%20Book%20$\).md)   
 [Depreciation Group](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_12476-depreciation-group-$-.md)   
 [Tax Register Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_17236-tax-register-setup-$-.md)