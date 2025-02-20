# Azure Devops Board

1. Log in to the system through the Login screen.
2. Fill in the following fields on the displayed screen:

* **Username**
* **Password**

3. Click the **Sign In** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-19 at 10.31.00.png" alt=""><figcaption></figcaption></figure>

4. The Azure DevOps Board plugin must be added as a plugin to the selected Company. After logging in, navigate to the Companies page from the left sidebar on the Dashboard screen.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-19 at 10.35.43.png" alt=""><figcaption></figcaption></figure>

5. On the Company Listing page, click the **Edit** button for the company where the plugin will be integrated.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 10.07.34.png" alt=""><figcaption></figcaption></figure>

6. On the displayed screen, navigate to the **Plugin** page for the selected Company.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-19 at 23.34.19.png" alt=""><figcaption></figcaption></figure>

7. From the listed plugins, select **Azure DevOps** and click the **Add** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-19 at 23.36.16.png" alt=""><figcaption></figcaption></figure>

8. After the plugin is added to the system, Azure DevOps Board account settings must be configured. Click on the Testinium user in the top right corner of the Dashboard, then select **Company Details**.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 00.00.23.png" alt=""><figcaption></figcaption></figure>

9. On the Company Details page, click on the Plugins page to configure the Azure DevOps Board account settings.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 00.15.40.png" alt=""><figcaption></figcaption></figure>

10. From the listed plugins, select **Azure DevOps** and click the **Edit** button.

    On the displayed page, fill in the following details:

    * **Organization Server URL** (Azure DevOps Board Link)
    * **Organization Name**
    * **Access Token**

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 00.52.44.png" alt=""><figcaption></figcaption></figure>

11. For Azure DevOps integration in Testinium, a token must be generated from the Organization Server URL page.

* Navigate to the **Organization Server URL**.
* Click on **User Settings** and select **Personal Access Tokens** from the displayed menu.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 00.58.33.png" alt=""><figcaption></figcaption></figure>

12. On the Personal Access Token screen, click the **New Token** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 00.59.13.png" alt=""><figcaption></figcaption></figure>

13. On the displayed screen, fill in the following fields: **Name, Organization,** and **Expiration**. In the Scopes section, select **Full Access**.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.00.27.png" alt=""><figcaption></figcaption></figure>

14. Click the **Create** button to generate the token. Copy the generated token and paste it into the relevant field in Testinium.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.02.35.png" alt=""><figcaption></figcaption></figure>

16. After adding the plugin and configuring the Azure DevOps Board account settings, follow the steps below to set up project-based configurations:

* Navigate to the Projects page from the Dashboard and select the project to be integrated.
* Click the **Edit** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.03.30.png" alt=""><figcaption></figcaption></figure>

17. On the Project Edit page, click the **Edit Azure DevOps Settings** button to configure the integration settings.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 10.08.28.png" alt=""><figcaption></figcaption></figure>

18. On the displayed screen, fill in the following fields:
    * **Assigned User**
    * **Azure Project** (The project where issues will be created in Azure DevOps Board)
    * **Issue Type**
    * **Selected Fields**

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.09.01.png" alt=""><figcaption></figcaption></figure>

19. The Fields section is listed based on the selected **Issue Type**. Use the arrow icon in the Fields list to move the selected fields to the **Selected Fields** section. (The **Title** field is mandatory for creating an issue in Azure DevOps.)

    **Note:** The available fields in the **Fields** section vary depending on the selected **Issue Type**. For specific requests or custom fields, please contact the Support team.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.10.37.png" alt=""><figcaption></figcaption></figure>

20. After completing the Azure DevOps integration settings for the project, follow the steps below to create an issue in Azure DevOps within the related project:
    * Open the **Plans** page.
    * Select the relevant project from the Project Name field. The plans associated with the project will be listed.
    * Click the **Test Report** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.16.18.png" alt=""><figcaption></figcaption></figure>

21. On the displayed screen, the test executions related to the selected project and plan are listed (Test Execution List (Auto) page). Click the **Show** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.19.36.png" alt=""><figcaption></figcaption></figure>

22. The Test Result screen opens for the selected test execution. Click the **Show** button to open the Test Result Details page.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.22.06.png" alt=""><figcaption></figcaption></figure>

23. Click the **Create Azure DevOps Issue** button.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.23.55.png" alt=""><figcaption></figcaption></figure>

24. Fill in the required fields in the Azure Issue Form. Click the **Create** button to generate the issue in Azure DevOps.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.25.16.png" alt=""><figcaption></figcaption></figure>

25. After the issue is created, the Create Azure DevOps Issue button on the Test Result Details screen is updated to View Azure DevOps Issue. Click the **View Azure DevOps Issue** button to open the created issue in the Azure DevOps Board.

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.26.56.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2025-02-20 at 01.28.37.png" alt=""><figcaption></figcaption></figure>
