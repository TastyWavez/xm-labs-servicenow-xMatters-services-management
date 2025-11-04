# xMatters Services: Simple create, update, delete workflow for adding ServiceNow services to xMatters
## Integration Overview


---

## Pre-Requisites

- **ServiceNow App Version:** Everbridge Flow Designer  
- **xMatters ServiceNow Integration v2:** Install Instructions  
- **xMatters Account:**  
  - Required. If you don’t have one, sign up before proceeding.  

---

## Files

A ServiceNow Update Set and xMatters Workflow is provided:

- ServiceNowBusinessServicesxMattersServicesStepsv2FlowDesigner.zip

- xMatters_flowDesigner_V2_Services.xml
---

## How It Works

### ServiceNow to xMatters Service Sync

- **Creating Services:**
- When a new service is added in ServiceNow a POST to xMatters is triggered and the service is created.
-  **Updating Services:**
-  When a service is updated in ServiceNow and a relevant change is detected e.g. name, business criticality, support group etc.. the corresponding service in xMatters to reflect the changed attributes. 
-  **Deleting Services:**
-  When a service is deleted in ServiceNow the corresponding xMatters service is deleted. 

---
# Installation Guide





