# xMatters Services: Simple create, update, delete workflow for adding ServiceNow services to xMatters
## Integration Overview


---

## Pre-Requisites

- **ServiceNow App Version:** Everbridge Flow Designer  
- **xMatters ServiceNow Integration v2:** Install Instructions  
- **ServiceNow Major Incident Plugin:** Install Instructions  
- **xMatters Account:**  
  - Required. If you don’t have one, sign up before proceeding.  

---

## Files

The following update sets are provided:  

-
-
---

## How It Works

### ServiceNow to xMatters Service Sync

---
# Installation Guide

## 1. Import the ServiceNowMIMBusinessRules Update Set into ServiceNow

### A. Import the XML File
1. Log in to your **ServiceNow** instance with an **administrator role**.  
2. In the left-hand navigation, search for and click on **Retrieved Update Sets** under the **System Update Sets** group.  
3. On the **Retrieved Update Sets** page, scroll to the **Related Links** section and click **Import Update Set from XML**.  
4. On the **Import XML** page:  
   - Click **Choose File**.  
   - Select your update set `.xml` file from your computer.  
   - Click **Upload**.  

### B. Preview and Commit the Update Set
1. After the upload, find your newly uploaded update set on the **Retrieved Update Sets** page.  
2. Click the **name** of the update set to open its record.  
3. Click **Preview Update Set** in the upper-right corner to assess its suitability for your instance.  
4. If there are preview errors, they will appear in the **Preview Problems** related list.  
   - Select the error.  
   - From the **Actions on selected rows** menu, choose **Accept remote update** to resolve it.  
5. Once the preview is successful, click **Commit Update Set** to apply the changes to your instance.  
6. Close the progress dialog box after the commit is complete.  

---

## 2. Ensure the Major Incident Plugin is Enabled

Verify that the **Major Incident Plugin** is active in your ServiceNow instance.

---

## 3. Import the xMatters Workflow

1. Log into **xMatters** as a user with the **Developer role**.  
2. Navigate to **Workflows**.  
3. Click the **Import** button (top right).  
4. Import the file: ServiceNowFlowDesignerv2-MajorIncidentWorkbench.zip


---

## 4. Configure Trigger Profiles in Flow Designer

Configure trigger profiles for:  
- **Incident Task**  
- **Incident Communication Task**

## Trigger Profile: Incident Tasks

To create a trigger profile, navigate to:

**Everbridge Flow Designer → Global Settings → Trigger Profiles**

1. Click **New** in the upper-right corner of the page.  
2. Complete the following fields:

   - **Name:** `Incident Tasks`
   - **Credentials:** Select the configured xMatters Credentials for this integration.
   - **Workflow:** Choose the workflow from the populated list  
     *(e.g., ServiceNow (Flow Designer) v2 – Major Incident Workbench)*.
   - **Trigger:** Select the trigger for Incident Tasks  
     *(ServiceNow Record Alerts Incident Task `[incident_task]`)*.
   - **Trigger URL:** Automatically filled once you select a trigger.
   - **Default Alert Priority:** Select a default priority *(e.g., Medium)*.  
     This value will be sent to Flow Designer unless overridden by the integration.
   - **Default Signal Mode (Optional):** Enter a signal mode value.  
     This may be overridden if an incident is created or updated.
   - **Additional Recipients:** Enter one or more users or groups from xMatters or Everbridge who should also receive alerts.  
     *(Separate recipients with commas).*
   - **ServiceNow API User:** Select the ServiceNow user account that Flow Designer will use to send updates back to ServiceNow.

3. Click **Submit** to create the trigger profile.

<img width="2706" height="974" alt="Incident_Task_TriggerProfile" src="https://github.com/user-attachments/assets/4900c7c5-a050-40a6-b41a-39090c30aad5" />

---

## Trigger Profile: Incident Communication Task (sys_email)

1. Click **New** in the upper-right corner of the page.  
2. Complete the following fields:

   - **Name:** `Incident Communication Task (sys_email)`
   - **Credentials:** Select the configured xMatters Credentials for this integration.
   - **Workflow:** Choose the workflow from the populated list  
     *(e.g., ServiceNow (Flow Designer) v2 – Major Incident Workbench)*.
   - **Trigger:** Select the trigger for Incident Tasks  
     *(ServiceNow Record Alerts Incident Task `[sys_email]`)*.
   - **Trigger URL:** Automatically filled once you select a trigger.
   - **Default Alert Priority:** Select a default priority *(e.g., Medium)*.  
     This value will be sent to Flow Designer unless overridden by the integration.
   - **Default Signal Mode (Optional):** Enter a signal mode value.  
     This may be overridden if an incident is created or updated.
   - **Additional Recipients:** Enter one or more users or groups from xMatters or Everbridge who should also receive alerts.  
     *(Separate recipients with commas).*
   - **ServiceNow API User:** Select the ServiceNow user account that Flow Designer will use to send updates back to ServiceNow.

3. Click **Submit** to create the trigger profile.


---

## 5. Test the Integration




