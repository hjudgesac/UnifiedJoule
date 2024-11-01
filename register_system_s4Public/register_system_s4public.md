1. Access [BTP Cockpit URL](https://cockpit.btp.cloud.sap).
2. Select the BTP Global Account that has the Joule entitlements and click **Continue**.</br>                       
![run_booster](1.png)

3. From the Navigation Pane on the left, select **System Landscape**.</br> 
![register_system](2.jpg)

4. Click **Add System**.</br>                              
5. Specify a **System Name** of your choice and select **SAP SuccessFactors** from the **System Type** dropdown.</br>  
![register_system](3.jpg)

6. Click **Get Token**.</br>        
![register_system](4.jpg)

7. Copy the **Registration Token** value and share it with your SuccessFactors Admin.  Close the token registration screen.</br>                                                         
![register_system](5.jpg)

8. Log into SAP SuccessFactors as an admin user and search for **Extension Center**.</br>                                                                                                                   
![register_system](6.jpg)
**Note**: If you don't have access to Extension Center, follow the steps in the preparation section.

9. Paste the token received from the BTP admin into the **Integration Token** text box and click **Add**.</br>                                      
![register_system](7.jpg)

10. Confirm the integration status shows **Integrated** in SuccessFactors system.</br>                                                                                                                   
![register_system](8.jpg)

11. Confirm the status is updated to **Registered** in the BTP Cockpit.</br>                                                                                                                   
![register_system](9.jpg)
**Note**: You may have to refresh the BTP Cockpit browser session to see the updated status.
