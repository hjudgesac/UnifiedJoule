1. If necessary, navigate to your BTP Global Account.<br/>
![run_booster](1.jpg)

2. From the Navigation Pane on the left, click **Boosters** >> search for **Joule** >> click **Start** on Setting up Joule tile.<br/>
![run_booster](2.png)

3. Confirm the pre-requisites check is successful and click **Next**.</br>
![run_booster](3.png)

4. From the Subaccount dropdown select the **Joule** subaccount created earlier and click **Next**.</br>
![run_booster](4.png)

5. From the Products dropdown select all SAP applications which will be setup with Joule.  For example, SAP S/4HANA Cloud Public Edition and SAP SuccessFactors in my setup. 
 Choose whether the integration is for **Testing or Production** and click **Next**.</br>
![run_booster](9.jpg)

6. Confirm the selected applications chosen in previous step are listed under the Capability Pacakages dropdown. Click **Next**.<br>
![run_booster](10.jpg)

7. Leave the default **Formation Name**.  Under the Include System area choose the following and click **Next**. </br>
  SAP Build WorkZone System: <Choose the SAP Build Work Zone created earlier>
  SAP Cloud Identity Services System: <Choose the Cloud Identity Services Tenant>
  Additional systems based on your specific scenario. In this example we are setting up Joule for SAP SuccessFactors and SAP S/4HANA Cloud Public Edition so choose the appropriate sytem that is registered in the System Landscape for those respective solutions.
![run_booster](11-1.jpg)

10. Confirm the validation check is successful and click **Next**.</br>
  ![run_booster](12.jpg)

11. Review the configuration settings and click **Finish**.</br>
  ![run_booster](13.jpg)

12. Confirm the booster execution is successful and click **Close**.</br>
![run_booster](7.png)
