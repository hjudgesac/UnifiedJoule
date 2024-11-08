1. From the Navigation Pane on the left, select **Trust Configuration**.  Click **Establish Trust**.</br>
![create_trust](1.jpg)

2. From the list of available SAP Cloud Identity Services tenants, choose the one that is also used by your SuccessFactors tenant and click **Next**.      
**Note**: It's important to the choose the correct SAP Cloud Identity Services tenant.  The tenant chosen here must be the same as the one used by SuccessFactors instance for which Joule is being configured.  Refer to the preparation steps section if unsure of what tenant to select from the list.</br>      
![create_trust](2.jpg)   

3. Choose the appropriate domain for your SAP Cloud Identity Services tenant.  Select either **ias.accounts.ondemand.com** or **ias.accounts.cloud.sap** and click **Next**.            
**Note**: Refer to the preparation steps section.  All apps which will be configured for Joule setup should be integrated with IAS using the same domain.  In most cases setup the BTP subacccount trust using **cloud.sap** domain.</br>           
![create_trust](3.jpg)       

4. Leave the default settings and click **Next**.</br>        
![create_trust](4.jpg)

5. Review the information is correct and click **Finish**.</br>                                                       
![create_trust](5.jpg)

6. Confirm the new trust with SAP Cloud Identity Services is visible under **Custom Identity Provider for Applications**.</br>                                     
![create_trust](6.jpg)
