---
title: Debug add-ins in Office Online
description: ''
ms.date: 12/04/2017
---

# Debug add-ins in Office Online


You can build and debug add-ins on a computer that isn't running Windows or the Office 2013 or Office 2016 desktop client - for example, if you're developing on a Mac. This article describes how to use Office Online to test and debug your add-ins. 

## Prerequisites

To get started:

- Get an Office 365 developer account, if you don't already have one, or have access to a SharePoint site.
    
  > [!NOTE]
  > To sign up for a free Office 365 developer account, join our [Office 365 developer program](https://dev.office.com/devprogram).
     
- Set up an add-in catalog on Office 365 (SharePoint Online). An add-in catalog is a dedicated site collection in SharePoint Online that hosts document libraries for Office Add-ins. If you have your own SharePoint site, you can set up an add-in catalog document library. For information, see [Publish task pane and content add-ins to an add-in catalog on SharePoint](../publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog.md).
    

## Debug your add-in from Excel Online or Word Online

To debug your add-in by using Office Online:

1. Deploy your add-in to a server that supports SSL.
    
    > [!NOTE]
    > We recommend that you use the [Yeoman generator](https://github.com/OfficeDev/generator-office) to create and host your add-in.
     
2. In your [add-in manifest file](../overview/add-in-manifests.md), update the **SourceLocation** element value to include an absolute, rather than a relative, URI. For example:
      
    ```xml
    <SourceLocation DefaultValue="https://localhost:44300/App/Home/Home.html" />
    ```
    
3. Upload the manifest to the Office Add-ins library in the add-in catalog on SharePoint.
    
4. Launch Excel Online or Word Online from the app launcher in Office 365, and open a new document.
    
5. On the Insert tab, choose  **My Add-ins** or **Office Add-ins** to insert your add-in and test it in the app.
    
6. Use your favorite browser tool debugger to debug your add-in.

## Potential issues    

The following are some issues that you might encounter as you debug:
    
- Some JavaScript errors that you see might originate from Office Online.
      
- The browser might show an invalid certificate error that you will need to bypass.
      
- If you set breakpoints in your code, Office Online might throw an error indicating that it is unable to save.

## Additional resources

- [Best practices for developing Office Add-ins](../overview/add-in-development-best-practices.md)
- [Validation policies for apps and add-ins submitted to the Office Store (version 2.2)](https://dev.office.com/officestore/docs/validation-policies)  
- [Create effective Office Store apps and add-ins](https://dev.office.com/officestore/docs/create-effective-office-store-listings)  
- [Troubleshoot user errors with Office Add-ins](testing-and-troubleshooting.md)
    
