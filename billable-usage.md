# [Customer Data Platform Billable Usage Calculations](https://help.salesforce.com/s/articleView?id=sf.c360_a_billing.htm&type=5)

### Quick Reference
- **Usage Type**: Metrics-defined resources offered by consumption-based products
- **Entitlement**: The amount of usage credits, capacity, or other digital currency your org purchases for a Digital Wallet card
- **Card**: A container for a group of usage types and their entitlements on your homepage
- **Credits**: Increments of usage that are deducted as you interact with certain Digital Wallet-enabled products
- **Capacity**: Increments of usage for certain Digital Wallet-enabled products that allow you to store data or files
- **Customer**: Data Platform orgs are billed based on *contracted entitlements*.

## Billable Usage Areas:
1. **Unified Profiles**:  
   - Billed based on the number of profiles you have, including those from Identity Resolution (IR).  
   - If you exceed your contract entitlement, you’ll be billed for extra profiles.

2. **Segment Publishes**:  
   - Billed based on how many times a segment is published.  
   - Each publication counts as one billable event.

3. **Engagement Events**:  
   - Billed based on the records in objects categorized as Engagement or Other (everything not counted as Unified Profiles).
  
   - 
## Unified Profile Calculation:
- **No Identity Resolution**:  
  The billable count includes all records in Profile-related objects (like Account or Contact), both known and unknown profiles.

- **With Identity Resolution**:  
  The count includes:
  1. Known Unified Profiles (from active IR rules).
  2. All records mapped to Profile-related objects (except those used in Identity Resolution).

- Account Contact
- Contact Point Address
- Contact Point App
- Contact Point Consent
- Contact Point Email
- Contact Point OTT Service
- Contact Point Phone
- Contact Point Social
- Device
- Party Identification

#### Example
This example has two active identity resolution rulesets: Unified Individual.1 with 10,000 records and Unified Individual.2 with 8,000 records. There are two DLOs that are categorized as Profile but aren’t mapped to Individual: The Account DLO has 2,000 records, and the custom DLO has 5,000 records. For this customer, the total billable Unified Profiles is 10,000 + 8,000 + 2,000 + 5,000 = 25,000.


![data cloud Usage](https://resources.help.salesforce.com/images/577aafb2d816f15fd669db999e4c4765.png)




## Factors Affecting Unified Profile Counts:
1. **Multiple IR Rulesets**:  
   - Profiles from all active rulesets are counted, so ensure only necessary rules are active.

2. **Data Stream Growth**:  
   - More data streams (source systems) can increase profile counts.  
   - Check for duplicates or unnecessary data.

3. **Anonymous Profiles**:  
   - These don’t count toward the billable total but must be marked correctly as "anonymous."

4. **DMO Category**:  
   - Ensure that objects mapped as Profiles should be categorized as such.  
   - Incorrect categories may lead to miscounts.

## Segment Publishes:
- Each segment publish counts as one event, even if it has multiple activations.  
- Check all publish schedules for estimates.

## Engagement Events:
- Engagement Events include records in any objects not classified as Unified Profiles.  
- This can include records mapped to non-Profile DMOs or data not part of Identity Resolution.

## Additional Considerations:
- Data from unmapped objects or transformed data (not categorized as Profile) won’t count toward Unified Profiles, but could count toward Engagement Events.

## Data Cloud Credit Consumption (Data Cloud license)

Data Cloud credits are digital currency that you use to pay for Data Cloud service. There are three consumption categories and associated usage types.

- **Connect:** Connect streaming and batch data to Data Cloud. Or connect data from Snowflake, Databricks, or BigQuery using data federation.
    - Batch Data Pipeline
    - Streaming Data Pipeline
    - Data Share Rows Shared (Data Out)
- **Harmonize:** Transform, map, and unify your data in Data Cloud.
    - Batch Profile Unification
    - Segment Rows Processed
    - Batch Calculated Insights
    - Streaming Calculated Insights
- **Activate:** Act on your data by creating insights, building AI functionality, querying for reports and dashboards, integrating data with apps, and creating automations.
    - Accelerated Data Queries
    - Data Queries
    - Data Federation or Sharing Rows Accessed
    - Inferences
    - Real-Time Profile API
    - Streaming Actions (including lookups)
    - Batch Activation


### [Multipliers for Data Cloud](https://www.salesforce.com/products/platform/customer-data-cloud/services/?_ga=2.112804492.920834802.1731484792-352130473.1731484792&_gl=1*fuxdeh*_ga*MzUyMTMwNDczLjE3MzE0ODQ3OTI.*_ga_H6M98GGB18*MTczMTQ4NDc5MS4xLjEuMTczMTQ4NDgyMi4wLjAuMA..*_gcl_au*MTM4NzU4NDg5LjE3MzE0ODQ3OTM.)


#### [Salesforce Customer Data Cloud](https://www.salesforce.com/content/dam/web/en_us/www/documents/platform/data-cloud-platform-services-rate-sheet.pdf)
### Salesforce Customer Data Cloud
Usage TypeUnit Multiplier
- **Segment Rows Processed**:  Per 1 Million Rows Processed  **Multiplier** : 20
- **Batch activation (With or without related attributes)**:  Per 1 Million Rows Processed **Multiplier** : 10
- **Activate DMO** : Streaming Per 1 Million Rows Processed **Multiplier** :  1600













































