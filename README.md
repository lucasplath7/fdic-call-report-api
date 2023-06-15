# fdic-call-report-api

# Purpose
This package is essentially three functions to enable a user to easily retrieve call report data for any federally insured bank.  This is public data, but automating its retrieval is somewhat cumbersome through the FDIC's system of SOAP requests. Using fdic-call-report-api a user can leverage three simple functions to pull the data. One fetches valid available call report period end dates, the second fetches ID's of institutions that filed call report data for those periods, and the last one fetches the actual call report data provided a filer id and reporting period end date.

# Prerequisite
To execute these functions a user requires an ffiec user id and api token (free).

Follow the instructions here to create your account and access your token https://cdr.ffiec.gov/public/PWS/PWSPage.aspx

# Functions
retrieveReportingPeriods
  
  args:
    
    - username (string): ffiec account username
    
    - passwordText (string): ffiec api token
  
  returns:
   
    - array (strings): array of all valid reporting period end dates

retrieveFilers
  
  args:
   
    - username (string): ffiec account username
    
    - passwordText (string): ffiec api token
   
    - fromPeriodDate (string): valid report end period date
   
    - toPeriodDate (string): valid report end period date
 
  returns:
    
    - array (strings): ids of any filers who submitted call report data for the provided date range

retrieveCallReport
  
  args:
   
    - username (string): ffiec account username
    
    - passwordText (string): ffiec api token
   
    - fedId (string): valid fed id for financial institution
   
    - periodEndDate (string): valid report end period date

  returns:
    
    - object: keys are the codes for call report values with associated values