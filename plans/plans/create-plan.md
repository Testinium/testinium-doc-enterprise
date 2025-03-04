# Create Plan

_**Create Plan**_ is the screen where a new plan definition is made in the system.

The following steps are followed to create a new plan;

1. Select a project from the main Plans screen.

{% hint style="info" %}
If the Create New Plan button is clicked without selecting the Project Name, the system displays the error message regarding the project name selection.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-04 at 14.48.19.png" alt=""><figcaption></figcaption></figure>

2. Create the _**Create New Plan**_ button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-04 at 14.50.04.png" alt=""><figcaption></figcaption></figure>

3. Enter the fields below in the _**Test Plan Details**_ form;

* Project Name
* Plan Name
* Description
* Scenarios of Plan
* Add Parameters / Java Test Parameters; Clicking the Add Parameters button, the system displays the Java Test Parameters field. The following fields are entered to add parameters.
  * Name
  * Value
  * Description

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

* Selenium Grid; The environment where the tests will run, Enterprise or Cloud
* Failed Test Retry Count (Number of Repetitions on Test Fail)
* Parallel Test Limit
* Max Execution Time per Scenario
* Enabled
* Screenshots
* Record Video
* Capture Performans Data; Displayed in browser tests, not in mobile tests. Reports values such as screens on time
* Group Test Plan; If one of the two Mobile Devices is the Receiver and the Other is the Sender, the group is defined as the plan and the Receiver/Sender is defined as the parameter in the Plan. (Only in mobile environment tests)
* Clear App Data (Only in mobile environment tests)
* Fetch File From Device; In mobile tests, the directory of the log file is given where the log file is almost. (Only in mobile environment tests)

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-04 at 14.56.32.png" alt=""><figcaption><p>Test Plan Details 1</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2025-03-04 at 14.56.20.png" alt=""><figcaption><p>Test Plan Details 2</p></figcaption></figure>



4. a. Click _**Next**_ to continue to the next form screen.

&#x20;       b. Click the _**Cancel**_ button to cancel the process of adding a new plan.

5. The next step depends on the project type;

a. If the selected project is _**a web project (Selenium)**_,  _**Browser Selection**_ screen opens.&#x20;

b. If the selected project is _**a mobile project (Appium)**_, _**Mobile Browser Selection**_ screen opens.

c. If the selected project is _**a service project**_, the Schedule screen opens, which is the              next step since no platform selection is made.

![](../../.gitbook/assets/TestPlanForm-MobileSelection.png)

On the Mobile Platform Selection screen that opens;

1. Browser
2. Browser Version

The desired mobile is found from the fields and these selections are added to the Selected Mobile Platform section by clicking the Add button.

Click the Next button and go to the Schedule tab.

If the Back button is clicked, it will be directed to the Test Plan Details tab.

If the Cancel button is clicked, the system cancels the plan definition process.

![](../../.gitbook/assets/TestPlanForm-Schedule.png)

If it is a one-time test plan, the Start Date is entered in the Once option.

If a repetitive test plan is desired, click on the Repetitive tab and on the screen that opens,

1. Start Date
2. Finished Date
3. Days of Week
4. Repeat Period

These values are entered in the form field.

Click the Next button and proceed to the Notifications tab.

If the Back button is clicked, it will be directed to the Schedule tab.

If the Cancel button is clicked, the system cancels the plan definition process.

The system displays the Notifications tab.

![](../../.gitbook/assets/TestPlanForm-Notification.png)

On the screen that opens;

1. Send Notification
2. E-mail
3. Execution Status
4. Test Result Notification
5. Test Result Status

These values are entered and the Add button is clicked. The system displays the added record on the listing screen. This added record can be removed with the Remove button.

Click the Next button and proceed to the Confirm tab.

If the Back button is clicked, it will be directed to the Notifications tab.

If the Cancel button is clicked, the system cancels the plan definition process.

On the Confirm screen that opens, the system displays a summary of all the information in the previously entered tabs.

![](../../.gitbook/assets/TestPlanForm-Confirm.png)

The system admin clicks the Save button. The system saves the new plan definition.

If the Back button is clicked, it will be directed to the Notifications tab.

If the Cancel button is pressed, the system cancels the new plan definition process. 
