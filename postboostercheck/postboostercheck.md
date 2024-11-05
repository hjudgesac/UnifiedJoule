## Check Formations in BTP Global Account
1. If necessary, navigate to your BTP Global Account.

2. Under **System Landscape** click **Formations** and ensure the formation is created successfully.  The formations should have all the system that were selected during the booster execution.</br> 
![postbooster](1.jpg)

## Check Joule Subscription and Destinations setup in BTP Subaccount
1. Click **Account Explorer** and select the Subaccount used for Joule setup.</br>
 ![postbooster](3.jpg)
2. Click **Services -> Instances and Subscriptions** and confirm **Joule** application is subscribed successfully.</br>
  ![postbooster](4.jpg)
3. Click **Connectivity -> Destinations** and confirm the destinations are successfully created.  The destinations shown will vary based on the systems selected during the booster execution.  See screenshot below for relevant destinations if the booster was executed for S/4HANA Public Cloud and SuccessFactors.</br>
![create_wz](2.jpg)  


## Configure SAP Build Work Zone to use SAP Cloud Identity Services - Identity Authentication
For more information on this, see [Switching to SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/switching-to-sap-cloud-identity-services-identity-authentication?q=identity+authentication)
1. From the Navigation Pane in BTP Cockpit, select **Security >> Users** and click the arrow to open user details.</br>
![create_content_provider](13.jpg)

2. Scroll down to role collections section and click **Additional Details** icon >> **Assign Role Collections**.</br> 
![create_content_provider](14.jpg)   

3. Select the **Launchpad_Admin** and click **Assign Role Collection**.</br>
![create_content_provider](15.jpg) 

4. From the Navigation Pane on the left, select **Instances and Subscriptions***. Click **SAP Build Work Zone, standard edition** to launch the application.</br>  
![create_content_provider](16.jpg) 

5. Select **Default Identity Provider**.</br>
![create_content_provider](17.jpg)

6. Click the **Settings** icon and select **Identity Authentication** tab.  Make sure the checkbox is selected and click **Enable**.</br>
![create_content_provider](18.jpg)

7. Confirm the Identity Authentication is enabled successfully.</br>
![create_content_provider](19.jpg)

8.  In the BTP cockpit, navigate to your BTP Global Account.</br>
![create_wz](11-1.jpg)
15.  Under **System Landscape** and confirm that you now also see a new system of type **SAP Build Work Zone** listed as a registered system.  This system is automatically added to the System Landscape from the SAP Build Work Zone subscription that you created earlier.  Make a note of the **System Name** for this system as it will come in handy later when executing the Joule booster.</br>
![create_wz](20.jpg)