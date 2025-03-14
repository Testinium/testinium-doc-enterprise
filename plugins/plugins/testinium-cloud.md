# Testinium Cloud

The requirements for _**Testinium Cloud integration**_ are as follows;

_**A. Operations in Companies module;**_ Adding Testinium Cloud as a plugin

_**B. Operations on the Company Details screen;**_ Setting Testinium Cloud settings for the relevant company

_**C. Operations in System Setting module;**_ Cloud test environment group creation

_**D. Procedures during the test run;**_ Plan settings

_**E. Test Run Results;**_ Test results display in Testinium Enterprise and Testinium Cloud

## A. Operations in Companies Module&#x20;

Plugin settings must first be made for the relevant company in Testinium Cloud integration.

{% hint style="info" %}
Plugin settings must be made by the _**system admin**_.
{% endhint %}

The following steps should be followed for plugin settings;

1. Open _**Companies**_ module.
2. Click _**Edit**_ button for the related company.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 13.33.44.png" alt=""><figcaption></figcaption></figure>

3. Click on _**Plugin**_ tab.
4. Testinium Cloud plugin is moved from _**Plugin**_ list to _**Enable Plugin**_ list by clicking _**Add**_ button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 13.35.50.png" alt=""><figcaption></figcaption></figure>

5. a. Click to _**Save**_ button to save plugin setting.                                                                                b. Click the _**Cancel**_ button to cancel plugin adding.

## B. Operations in Company Details&#x20;

Connection settings of the company for Testinium Cloud integration are made in this step.

1. Open the _**Company Details**_ screen from the menu in the upper right corner.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 13.47.25.png" alt=""><figcaption></figcaption></figure>

2. Click on the _**Plugin**_ tab.
3. Click the _**Edit**_ button in the Testinium Cloud section.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 13.48.04.png" alt=""><figcaption></figcaption></figure>

4. Enter the following fields on the screen that opens;

* Web URL ([https://testinium.io](https://devcluster.testinium.io) )
* RestApi URL ([https://testinium.io/Testinium.RestApi/](https://testinium.io/Testinium.RestApi/) )
* Hub URL (  [http://hub.testinium.io/wd/hub](http://hub.testinium.io/wd/hub) )&#x20;
* Auth URL ( [https://account.testinium.com/uaa/oauth/token](https://account.testinium.com/uaa/oauth/token) )
* Testinium Username
* Access Key

{% hint style="info" %}
_**Testinium Username**_ and _**Access Key**_ information is retrieved from the testinium.io web page.

_**Web URL**_, _**RestApi URL**_ , _**Hub URL**_ and _**Auth URL**_ are filled from the default values specified in parentheses.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 13.49.19.png" alt=""><figcaption></figcaption></figure>

5. a. Click to _**Save**_ button to save plugin connection information.                                                                                b. Click the _**Cancel**_ button to cancel the process.

## C. Operations in System Settings&#x20;

Environment grouping must be done for Testinium Cloud integration. This step describes these processes.

The following steps are followed for the grouping process;

1. Open the _**Cloud Test Environments**_ screen in the System Setting module.
2. Click the _**Create New Group**_ button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 14.29.51.png" alt=""><figcaption></figcaption></figure>

3. Enter the group name.
4. Select _**Operating System**_.
5. Create a group by moving the environments in the _**Testinium Cloud Test Environments**_ list to the _**Selected Environments**_ list with arrows.
6. Select _**Test Run Method**_ (random or one by one).

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 14.29.00.png" alt=""><figcaption></figcaption></figure>

7. a. Click to _**Save**_ button to the group.                                                                                                  b. Click the _**Cancel**_ button to cancel the process.

## **D.** **Procedures during the test run**

The steps to be performed in the test plans for Testinium Cloud integration during test runs are as follows;

1. Open the **Plans** screen and select the project.
2. Click the **Edit** button on the scenario line to run.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 15.09.47.png" alt=""><figcaption></figcaption></figure>

3. Select _**Testinium Cloud**_ in the _**Selenium Grid**_ field in the Test Plan Details step on the Test Plan Details screen.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 15.15.28.png" alt=""><figcaption></figcaption></figure>



4. Select the group from the _**Cloud Test Environment Group Selection**_ field (explained how to create it in the previous title) in the next step, Mobile Platform Selection.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-12 at 15.16.21.png" alt=""><figcaption></figcaption></figure>

5. Save the plan after making any other necessary edits to the plan.
6. Run the test plan.

## _**E. Test Run Results**_

The tests run in Testinium Enterprise can be viewed in all reports (Test Executions, etc.) in Testinium Enterprise.

The following steps are followed to view the relevant test execution results in Testinium Cloud;

1. Log in to the system with the connection information entered in the system for Testinium Cloud integration.
2. Open the _**Automated Tests**_ screen.
3. Click on the _**Operation Report**_ tab.  Test results run in Testinium Enterprise are listed in this tab.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 09.25.54 (1).png" alt=""><figcaption></figcaption></figure>

4. Click the _**Details**_ button on the relevant test result for test result details.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-13 at 09.28.21.png" alt=""><figcaption></figcaption></figure>
