---
title: "Walkthrough: Logging Email Interactions in the Microsoft Dynamics NAV Database"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Outlook, email logging"
  - "email logging, Outlook"
  - "email logging, setting up"
  - "interactions, email logging"
ms.assetid: 03d4c25b-4be1-4e62-affc-f7d478caec1c
caps.latest.revision: 26
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# Walkthrough: Logging Email Interactions in the Microsoft Dynamics NAV Database
In managing your relationships with contacts, it helps keep track of email correspondence. Email logging in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] is designed to help you with that. It lets you keep records of your email correspondence in both [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] and Microsoft Exchange Server. For example, you can send an email message to a contact about an upcoming event. The contact replies, and confirms interest in participating. Both messages are logged on the contact card. Or, you might receive a complaint from a contact via an email message. You can track that contact's message and your response to it by using email logging.  
  
 The email logging feature makes it possible to log all inbound and outbound email messages. The only requirement is that the email address be one that [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] recognizes. The address must belong to a salesperson or to a contact. The messages can be created in Outlook. They are logged automatically when you have email logging enabled. This gives you flexibility to choose the solution that best suits your needs.  
  
 After you have implemented email logging, you can make email correspondence available to all employees, even if a message was sent to a specific recipient. You do this by taking advantage of Exchange public folders. This improves knowledge sharing and enables better user productivity, because information is stored in one common location.  
  
 Because email logging is server\-based, email messages are kept in their native environment instead of in the application. This makes it easier to administer and optimize database storage.  
  
## About This Walkthrough  
 This walkthrough describes how to install and maintain email logging for Microsoft Exchange Server in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)].  
  
 This walkthrough illustrates the following tasks:  
  
-   Installing and configuring email logging.  
  
-   Testing and using email logging.  
  
-   Performance fine\-tuning.  
  
### Roles  
 This walkthrough provides tasks that are generally performed by the following user roles:  
  
-   IT Engineer\/Technical End User\/Power User  
  
-   Salesperson\/Marketing Account Manager  
  
### Prerequisites  
 Before you can perform the steps in this walkthrough, you must do the following.  
  
 To complete this walkthrough, you will need:  
  
-   [!INCLUDE[demolong](../../ApplicationDesign/includes/demolong_md.md)].  
  
-   [!INCLUDE[nav_admin](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)].  
  
-   A connection to Microsoft Exchange Server 2013 or Microsoft Exchange Server 2010.  
  
-   Access to Microsoft Exchange Public Folders. For more information, see [Public folders in Exchange Server 2013](http://go.microsoft.com/fwlink/?LinkId=526140).  
  
-   Microsoft Outlook 2013 or Microsoft Outlook 2010.  
  
## Story  
 This walkthrough focuses on two aspects of email logging. In the first, the IT engineer is called upon to set up email logging. This can also be done by a technical end user onsite at the company. In the second aspect, a salesperson is using email logging to keep track of emails that have been sent to a contact. The salesperson's manager can see a record of the interactions in a log.  
  
## Installing and Setting Up Email Logging on Microsoft Exchange Server  
 To use email logging, you must be connected to Microsoft Exchange Server and have an email account.  
  
> [!NOTE]  
>  For use in this walkthrough, consider creating a domain user email account that is not tied to specific individual. If you do this, you will also want to add the domain account to [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] as a Windows user who has a SUPER permission set.  
>   
>  However, in a production environment, we recommend that you set up your service account that is assigned the minimum required [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] permissions, especially if you are running the service on a dedicated server instance.  
  
 In Outlook, you will have to create two Exchange public folders to contain your mail. These folders are used to process messages and to archive them. This procedure must be completed before you continue to set up email logging in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)].  
  
> [!NOTE]  
>  If you are an Exchange administrator, you can also use the Exchange Management Console to accomplish this task. For more information, see [Exchange Management Console](http://go.microsoft.com/fwlink/?LinkId=246184).  
  
> [!NOTE]  
>  The email account that is used to configure email logging in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] must have certain permissions with regard to the public folders.  
>   
>  -   When you configure email logging setup in the **Marketing Setup** window, the user name that is used for the validation of setup must have **Read** access to the public folders.  
> -   When email logging is running on the [!INCLUDE[nav_server](../../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)], the user account credentials that are used on the server instance must have full **Read**, **Write**, and **Delete items** permission levels set on the public folders.  
  
 For more information, see [Managing Public Folder Permissions](http://go.microsoft.com/fwlink/?prd=12036).  
  
#### To set up Microsoft Exchange Server folders for email logging  
  
-   In Microsoft Outlook, in your mailbox, create two public folders.  
  
    |Folder|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |------------|---------------------------------------|  
    |Queue|Email messages are copied by a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] user, typically a salesperson, to the queue folder, according to rules that you have set up.|  
    |Storage|Incoming and outgoing messages are logged and automatically copied to the storage folder.|  
  
    > [!NOTE]  
    >  [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] does not support folder paths that are longer than 250 characters. Accordingly, you should set up your public folder structure to be able to handle this limitation.  
  
     For more information, search Microsoft Outlook Help for "Create a folder."  
  
 For more information, see [Public folders in Exchange Server 2013](http://go.microsoft.com/fwlink/?LinkId=526140) and [Public folder procedures](http://go.microsoft.com/fwlink/?LinkId=526141).  
  
## Configuring [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]  
 After you have set up public mail folders in Microsoft Outlook, you next configure [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] to interact with them. One aspect of setup requires that you specify how you want interactions to be recorded in an interactions log. The other aspect is to identify the folders in which you log your activities. The following steps require that you be logged in as a SUPER user who has all permissions.  
  
#### To configure email logging  
  
1.  In the **Search** box, enter **Interaction Template Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **E\-Mails** field, select a template. For this walkthrough, select **EMAIL**. Choose the **OK** button. For more information, see [Interactions](../../Marketing/interactions.md).  
  
3.  In the **Search** box, enter **Marketing Setup**, and then choose the related link.  
  
4.  Expand the **E\-Mail Logging** FastTab and in the **Autodiscovery E\-mail Address** field, enter the email address of a user in your company who has an email account on a Microsoft Exchange Server.  
  
5.  In the **Queue Folder Path** field, choose the **AssistEdit** button. The **Exchange Public Folders** window opens.  
  
6.  Select a folder name for your public folder, and on the **Home** tab, choose **Get Subfolders**. Navigate to the queue folder that you created in Outlook.  
  
7.  In the **Storage Folder Path** field, choose the **AssistEdit** button. Navigate to the storage folder that you created in Outlook.  
  
8.  In the **Email Batch Size** field, enter 20. This value specifies how many email messages to process at a time.  
  
9. To make sure that the address and setup are valid on the Exchange Server, on the **Actions** tab, in the **Functions** group, choose **Validate Email Logging Setup**.  
  
## Enabling a Job Queue for Email Logging  
 To keep an email logging system running at all times, you must use it together with a job queue. You can set up a job queue to run on a separate server instance to service your email logging system.  
  
#### To set up Microsoft Dynamics NAV Server  
  
1.  Open [!INCLUDE[nav_admin](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)]. For more information, see [Microsoft Dynamics NAV Server Administration Tool](../Topic/Microsoft%20Dynamics%20NAV%20Server%20Administration%20Tool.md).  
  
2.  Create a new server instance called EMAIL. For more information, see [How to: Create a Microsoft Dynamics NAV Server Instance](../Topic/How%20to:%20Create%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md). To prevent collisions with the default server port settings, set port information as follows.  
  
    |Port|Setting|  
    |----------|-------------|  
    |Management Services|7145|  
    |Server|7146|  
    |SOAP Services|7147|  
    |OData Services|7148|  
  
     Set the Service Account. Select **User Account**, and specify the required information for user name, domain, and password. To complete this walkthrough, select the user account that you used to configure the email logging setup.  
  
3.  Choose **Edit**. On the **NAS Services** FastTab, in the **Startup Codeunit** field, enter the following parameter: *450*. In the **Company** field, enter the name of the company. The company name field is case sensitive.  
  
4.  Choose **Save**, and then choose the **OK** button.  
  
 After you set up the job queue, which is described in the following procedure, you will return to the administration tool to start the server instance.  
  
 For your company, you set up a job queue that you want to run every day. You also specify that you want the process to run every 5 minutes. Finally, you specify that the job queue should stop on the last day of the year, December 31.  
  
 In order to set up the job queue for email logging, a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] user with sufficient permission sets is required. Consider using the permission sets BASIC and JOBQUEUESETUP as defined in the [!INCLUDE[demolong](../../ApplicationDesign/includes/demolong_md.md)]. The user must also be granted an explicit permission to run codeunit 5065. For more information, see [How to: Create Job Queue Entries](../../SetupAndAdministration/how-to-create-job-queue-entries.md).  
  
#### To start the job queue  
  
1.  In the **Search** box, enter **Job Queue Category**, and then choose the related link.  
  
2.  Choose **New**, and create a new category code called LOGGING. In the **Description** field, enter Email Logging. Choose the **OK** button.  
  
3.  In the **Search** box, enter **Job Queues**, and then choose the related link.  
  
4.  Choose **New**, and create a new queue code called ELQ. In the **Description** field, enter **Email Logging Queue**.  
  
5.  Choose the **Job Queue Category Filter** field and set to LOGGING. Select the **Start Automatically From NAS** check box. Choose the **OK** button.  
  
6.  In the **Search** box, enter **Job Queue Entries**, and then choose the related link.  
  
7.  Choose **New**, and fill in the **Job Queue Entry** card as follows.  
  
    ### General FastTab  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|Value|  
    |---------------------------------|-----------|  
    |**Object Type to Run**|Codeunit|  
    |**Object ID to Run**|5065|  
    |**Description**|Email Logging Job|  
    |**Job Queue Category Code**|Logging|  
    |**Max. No. of Attempts to Run**|3|  
    |**Expiration Date\\Time**|December 31|  
    |**Earliest Start Date\/Time**|One day earlier than today's date|  
  
    ### Recurrence FastTab  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|Value|  
    |---------------------------------|-----------|  
    |**Recurrence**|Set all days to True|  
    |**Starting Time**|6:00:00 AM|  
    |**Ending Time**|6:00:00 PM|  
    |**No. of Minutes Between Runs**|5|  
  
     Choose the **OK** button.  
  
8.  In the **Job Queue Entries** window, select the job queue. On the **Home** tab, choose **Set Status to Ready**.  
  
### To start and test the job queue  
  
1.  Open [!INCLUDE[nav_admin](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/includes/nav_admin_md.md)].  
  
2.  Select the EMAIL server instance, and start it.  
  
     For more information, see [Managing Microsoft Dynamics NAV Server Instances](../Topic/Managing%20Microsoft%20Dynamics%20NAV%20Server%20Instances.md).  
  
3.  Return to the [!INCLUDE[rtc](../../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/rtc_md.md)], and in the **Search** box, enter **Job Queue Log Entries**, and then choose the related link. To verify that the job queue is working as expected, note whether an entry is logged every five minutes.  
  
## Testing Email Logging  
 Before you put a system into production, you can try some simple tests to see whether it is working as expected. The following procedure is representative of how a salesperson and his manager would use the system. The task has several prerequisites to make testing easy. First, you should set the email address of a test salesperson so that it is the same email account that you used for autodiscovery. The test salesperson should have an email address that you can use for testing. Next, set up a test contact that has an email address that you can verify receives mail.  
  
 In your tests and in production, we recommend that you copy mail messages, and not move them. This makes sure that all mails from customers are seen, even if they contain invalid data that prevents email logging from processing them.  
  
#### To test email logging  
  
1.  Open the test salesperson card.  
  
2.  On the **Navigate** tab, choose **Contacts**. Add your test contact to the salesperson's list. Create a new contact, if needed.  
  
3.  Choose **Edit** to open the contact card.  
  
4.  Expand the **Communications** FastTab, and in the **E\-mail** field, choose the button with a picture of an envelope on it. An Outlook window opens in which you can create and send a simple message.  
  
5.  Send a message from the salesperson to the contact. Also send a message from the contact to the salesperson.  
  
6.  From the salesperson Outlook Sent folder, copy the message that you sent to the contact to the public queue folder. From the Outlook Inbox of the salesperson, copy the message from the contact to the public queue folder.  
  
     If the job queue is working as expected, you can proceed to the next step.  
  
7.  On the salesperson card, on the **Navigate** tab, choose **Interaction Log Entries**. Verify that the email message that you sent is in the list. On the **Home** tab, choose **Show** to open the mail message.  
  
    > [!IMPORTANT]  
    >  Email messages received through the Internet can have fake sender addresses. That means that interaction log entries in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] that are created from email logging could potentially include fake addresses and should be reviewed with security in mind.  
  
#### To integrate mail messages with public folders  
  
1.  In your Outlook Sent box, select the email messages that you want to archive for future reference.  
  
2.  Copy the messages to the public folder that you have designated to be your queue folder.  
  
    > [!TIP]  
    >  You can use Outlook rules to automate this process. For example, you can set up a rule to always copy mail from a certain contact to your public queue folder. Make your rules as specific as possible to avoid copying spam to the queue folder. For more information, search Outlook Help for a topic called "Manage messages by using rules."  
  
## Using Email Logging and Interaction Logs  
 To verify your interactions, you can review the information that is recorded in the **Interaction Log Entries** window.  
  
 For more information, see [How to: Set Up Email Logging for use with the Job Queue](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md)  
  
## See Also  
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)   
 [Folders](../Topic/\($%20N_5320%20Folders%20$\).md)   
 [Relationship Management Setup](../Topic/\($%20N_5094%20Relationship%20Management%20Setup%20$\).md)   
 [Security Considerations for Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/security-considerations-for-email-logging.md)   
 [Troubleshooting: Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md)