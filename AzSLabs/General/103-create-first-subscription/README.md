# Create the first user Subscription
Even as an Azure Stack Administrator, you're not able to deploy resources within the tenant portal. First of all we've to create a "user" subscription.

 * Goto your Azure Stack Admin Portal (https://adminportal.local.azurestack.external)

**Create an Offer**
1. Click on "More services" and "Offers"
2. Click on "Create Offers" or "+ Add"
3. Enter a Display Name, Resource Name and create a new Resource group "offers"

![img1](img/offer_1.PNG)

4. Click on "Base plans" to add a new Plan to your offer
5. In the "Plan" pane, click on "+ Add" to create a new plan
6. Select a "Display name", "Resource name" and create a new Resource group "plans"

![img2](img/plan_1.PNG)

7. Click on "Services" and select "Compute", "Network" and "Storage"
8. Click on "Quotas" and select the "Default Quota" for "Compute", "Network" and "Storage"

![img3](img/quota_1.PNG)

9. Click "OK"
10. Click "OK" in "New plan"
11. Select the newly created "Default Plan" and click "Select"

![img4](img/plan_2.PNG)

![img5](img/offer_2.PNG)

12. Click on "Create" to create your Default Offer

**Create a Subscription**
1. Click on "More services" and "User subscriptions"
2. In "User subscriptions" click on "+ Add" to create a new subscription
3. Create a "new user subscription" for your AzureAD account
4. Click on "Select an offer" and select your previously created "default-offer"

![img6](img/newsub_1.png)

5. Click on "Create" to create your Subscription

**Tenant Portal**
 1. Reload the Tenant Portal (https://portal.local.azurestack.external)
 2. Click on "More services" and "Subscriptions"
 3. You should now see your newly created subscription
 
 ![img7](img/newsub_2.png)
 
