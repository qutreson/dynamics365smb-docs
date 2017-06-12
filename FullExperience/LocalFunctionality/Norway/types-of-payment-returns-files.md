---
title: "Types of Payment Returns Files"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payments, return files"
  - "payment returns"
  - "receipts, returns"
  - "settlement, returns"
ms.assetid: 0e14a9e0-8bb6-4cb1-bffc-e1fca45dcf9a
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# Types of Payment Returns Files
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes two types of payment return files that can be imported:  
  
-   Receipt returns  
  
-   Settlement returns  
  
 You can also choose to not use return files by selecting the **Return File Is Not In Use** field in the **Remittance Agreement** table. For more information, see [How to: Set Up Remittance Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-remittance-agreements.md).  
  
## Receipt Returns  
 The receipt return is received from the bank after you have sent the remittance file to the bank. When data is imported, information about the number of invoices that are received correctly and the number that are received with error is displayed. After you import a receipt return, the status of the payments in the **Waiting Journal** table is set to **Approved**.  
  
> [!NOTE]  
>  You may also receive a rejected return from the bank. If the remittance is rejected, the settlement return will not be received.  
  
## Settlement Returns  
 The settlement return is received from the bank after the payment is executed. When data is imported, information about the number of settled invoices is displayed.  
  
 The following occurs when the settlement return is imported:  
  
-   Payment status in the **Waiting Journal** table is set to **Settled**.  
  
-   Information will be transferred from the **Waiting Journal** window to the payment journal.  
  
-   A balancing account will be created for each transaction.  
  
-   Document numbers will be inserted for each transaction.  
  
### Exchange Rates by Settlement  
 For a payment, the exchange rates are managed in the following ways:  
  
-   Payment from an account in local currency \- If a payment in another currency is from an account in LCY, the bank will flag the settlement return with a warning about the exchange rate between LCY and the currency that is used as payment.  
  
-   Payment from a currency account \- If payment is made from a currency account, the exchange rate for this currency and LCY is used. This is because the bank does not inform the system about the exchange rate.  
  
### Warnings on Settlement Returns  
 When the settlement return is imported, warnings can occur. Payment journal lines with warnings are marked with a symbol. To view the information about the warning, you can open the **Settlement Info** window.  
  
## See Also  
 [Electronic Payments to Vendors in Norway](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/recipient-reference-codes.md)   
 [How to: Create Remittance Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-remittance-suggestions.md)   
 [How to: Create Manual Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-export-remittance-payments.md)   
 [How to: Import Payment Return Data](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/remittance-errors.md)   
 [How to: View Remittance Error Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/how-to-cancel-payments.md)