Before you can activate Joule there are certain number of pre-requisites that must be met.  This section describes those pre-requisites and outlines some details that need to be captured prior to running through the activation steps.

## 1. User Personas Required for Joule activation

Activation of Joule requires configuration in multiple systems.  It's important to have the right stakeholders involved when setting up the configuration.  In order to setup Joule the following user personas are required:
* Admins of the system for which Joule will be setup.  For example, SAP SuccessFactors, SAP S/4HANA Cloud Public Edition etc.
* SAP BTP Global Account Admin
* SAP Cloud Identity Services Admin
  
## 2. Verify Global Account Entitlements

1. Access [BTP Cockpit URL](https://cockpit.btp.cloud.sap).
2. Select the BTP Global Account and click Continue.</br>
   ![Preparation](1.png)
3. From the Navigation Panel expand **Entitlements** and click **Service Assignments**.
4. Search for **Joule** and validate that plan below is available.
   
    | Application     | Technical Name | Plan        | Required Quota | Remaining Quota |
    | ----------- | ----------- | ----------- | -------------- | --------------- |
    | Joule      | das-application      | foundation       |     1            |          limited       |
  
    ![Preparation](2.jpg)

5. Clear existing search text and search for **SAP Build Work Zone, standard edition**.  Validate that following 2 plans are available for SAP Build Work Zone:

    | Application     | Technical Name | Plan        | Required Quota | Remaining Quota |
    | ----------- | ----------- | ----------- | -------------- | --------------- |
    | SAP Build Work Zone, standard edition   | SAPLaunchpad       | foundation or standard       |      1           |       limited          |
    | SAP Build Work Zone, standard edition      | build-workzone-standard      | foundation or standard      |     1            |          limited       |
  
     ![Preparation](3.jpg)  

If the entitlements are not visible, it could be due to one of these reasons:
  * You don't have licenses for Joule.
  * Joule entitlements were added to different BTP Global Account to which you don't have Global Account Admin access.
  * The start date for the Joule contract is at future date hence the entitlements won't be visible in BTP until that date.

  In the scenarios above, please work with Account Executive, BTP Customer Success Partner or SuccessFactors Customer Success Partner to resolve the entitlements issue prior to proceeding further with this mission.

## 3. Choose Data Center for Joule Setup

Joule is BTP Service that works with multiple SAP solutions.  The number of SAP solutions supported with Joule is growing on a regular basis so it's important to choose a data center for Joule setup that can work for various SAP systems that you may have in your landscape - even if those systems are not in scope for Joule setup now.  There are several factors that determine which data center to choose for Joule setup.  Some factors to consider:
1) What are the currently supported datacenters for Joule?</br>
2) Which SAP solutions will Joule be setup for and what are datacenters of those solutions?</br>
3) Are there any legal requirements to choose a datacenter in particular region?</br>
4) Do you have prefernce for particular hyperscalar such AWS, Azure, Google etc.?</br>

The picture below depicts the process to follow to determine data center selection.
 ![Preparation](4.jpg)
For Step 1, review the list of Joule supported data centers from the help page: [Data Centers Supported for Joule](https://help.sap.com/docs/joule/serviceguide/data-centers-supported-by-joule)</br>
Step 2 requires finding the data centers for the respective SAP systems for which Joule will be setup.  This will be different for each system so refer to solution specific documenation to find the respective data centers.</br>

Let's take a look at a hypthetical scenario shown in the picture below.  In this scenario, majority of the systems are in North American datacenters so it makes sense to choose one of the North American data centers for Joule setup.  The choice between US EAST (VA), US (Virginia), or US Central (IA) is entirely up to you based on your hyperscaler preference.</br>
 ![Preparation](5.jpg)

## 4. Confirm same authentication setup used across SAP systems

To setup a Joule instance that works across different SAP systems the following 3 conditions must be met:
   1) Systems must be integrated with same SAP Cloud Identity Service tenant.
   2) The trust setup between SAP Cloud Identity Authentication Service(IAS) and the SAP system should be using the same domain.
   3) If using a Corporate Identity Provider, the Conditional Authentication settings for the applications must be setup the same way.

SAP provides a production and non-production instance of SAP Cloud Identity Services free of charge to SAP customers.  All non-prod SAP systems should be integrated with same non-prod Cloud Identity Services tenant and production ones with the production tenant.

SAP systems which are in scope for Joule setup must be integrated with SAP Cloud Identity Services using the same domain.  SAP Cloud Identity Services can use ondemand.com or cloud.sap domain hence it's important that systems that will use the same Joule instance have consistency on domain used to integrate with SAP Cloud Identity Services.  If that's not the case in your environment, then it's not possible to use a single Joule instance that works across different SAP systems.

Furthermore, if your SAP Cloud Identity Authentication Service is setup to use a Corporate Identity Provider, all of your applications must be configured to use the same Corporate Identity Provider.  For example, if you are planning to run the booster for SAP SuccessFactors and SAP S/4HANA Cloud Public Edition, the conditional authenticaton settings for both of these applications in SAP Cloud Identity Authenticaton Service should be setup the same way.  If that's not the case in your environment, then it's not possible to use a single Joule instance that works across different SAP systems.  The screenshot below depicts a scenario where SAP SuccessFactors is configured to use MS Entra ID while SAP S/4HANA Cloud Public Edition is setup to use OKTA.  In this scenario, the applicaitions conditional authentication settings do not match, hence unified Joule instance can't be used.</br>
![Preparation](8.jpg)

## 5. Validate Identity Federation Settings in SAP Cloud Identity Services

In order for Joule to work, it requires certain attributes from the user profile in SAP Cloud Identity Services.  Specifically the Global User ID(GUID) field is used by the Joule application.  To ensure this attribute is read from SAP Cloud Identity Services user profile, the **Identity Federation** Settings may have to be enabled in your system.  This setting is relevant:
  * if you have a Corporate Identity Provider configured in SAP Cloud Identity Services
  * and your application is configured to delegate the authentication request to that corporate IDP

To enable this settings, ensure **Use Identity Authentication user store** toggle is enabled under the Identity Federation Settings of your Corporate Identity Provider setup in SAP Cloud Identity Services.  For more information on this setting, refer to [Configure Identity Federation](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/corp-idp-configure-identity-federation?version=Cloud&q=identity+Federation)</br>
![Preparation](9.jpg)

## 6. Register Systems in SAP BTP

To setup Joule for SAP systems, it's important that those systems are registered under BTP **System Landscape**.  It's possible that the systems are already registered automatically or as part of another project.  If that's not the case, you may have to register the systems using the subsequent steps mentioned in this mission.  For the purpose of this mission I am using SAP SuccessFactors and SAP S/4HANA Cloud Public Edition to showcase the setup process.  Few things to note:
  * Register a new system only if it's not already there.
  * System Type of **SAP Cloud Identity Services** should already be listed by default.  Ensure that the SAP Cloud Identity Services tenant for the applications that are in scope for Joule setup is listed.
  * Not all systems have to registered up front.  For example, if you are only going to run the booster for S/4HANA Cloud, there is no need to ensure that SuccessFactors is also registerd under the System Landscape.</br>
![Preparation](10.jpg)
