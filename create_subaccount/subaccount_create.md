## **Create Subaccount and Cloud Foundry Space**


1. Access [BTP Cockpit URL](https://cockpit.btp.cloud.sap).
2. Select the BTP Global Account that has the Joule entitlements and click **Continue**.</br>                       
![run_booster](1.png)

3. From the Navigation Pane on the left, select **Account Explorer**.  Click **Create** >> **Subaccount**.</br> 
![run_booster](3.jpg)

4. Specify **Display Name** and **Region** and click **Create**.</br>                              
![run_booster](3-1.jpg)   
**Note**: The **Region** must be from one of the supported data centers for Joule.  See [Data Centers Supported by Joule](https://help.sap.com/docs/JOULE/3fdd7b321eb24d1b9d40605dce822e84/8b4d8708f6d646a995fdc50f8c508f1f.html?version=CLOUD)

5. Click **Enable Cloud Foundry**.</br>  
![run_booster](4.jpg)

6. Leave the default settings and click **Create**.</br>        
![run_booster](5.jpg)

7. From the Navigation Pane, expand **Cloud Foundry** and click **Spaces**.</br>                                                         
![run_booster](6.jpg)

8. Click **Create Space**.</br>                                                                                                                   
![run_booster](7.jpg)

9. Specify a **Space Name** and click **Create**.</br>                                      
![run_booster](8.jpg)


## **Add Entitlements**


1. From the Navigation Pane, select **Entitlements** and click **Edit**.</br>
![run_booster](9.jpg)

2. Click **Add Service Plans**.</br>                        
![run_booster](10.jpg)

3. Search for "Joule".  Click **Joule** and choose **foundation (Application)** from the list of available plans.</br>
![run_booster](11.jpg)

4. Search for "workzone".  Click **SAP Build Work Zone, standard edition** and choose the **foundation** and **foundation (Application)** plans.  Click **Add 3 Service Plans**.</br>
**NOTE**: Use the **standard** and **standard (Application)** plan instead if you also want to setup Joule for SAP Build Work Zone.
![run_booster](12.jpg)

5. Click **Save**.</br>                
![run_booster](13.jpg)


## **Add Trusted Domains**


1. From the Navigation Pane, select **Settings** and click **Add**.</br>
![run_booster](14.jpg)

2. Add your **SuccessFactors tenant URL** and click **Add**.  For example, https://hcm-us10.hr.cloud.sap.                  
**NOTE**:  Do not add trailing slash(/) at the end of the URL.</br>    
![run_booster](15.jpg)

3.  Click the **Add** button again to add URLs for additional applications (such as S/4AHANA Cloud Public Edition).
![run_booster](16.jpg)

4. Similarly add URLs for other applications that will be setup for Joule.
 
