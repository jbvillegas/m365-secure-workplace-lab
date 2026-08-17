# Third Objective & Process

- For this third step I will be adding licenses to tenants as well as explaining their differences.

- In this newer versions Microsoft allows Graph PowerShell for querying and managing licenses, as well as examples for group-based licensing. 

## Direct Licensing vs Group-Based Licensing

- By using **direct licensing** we are assigning a product license to an individual user account manually, this is easy to control individual users, better for small changes, testing, or other type of setups. However, when scaling it becomes extremely hard to control. 

- On the other hand, **group-based licensing** works better for larger companies that require automated management because it links licenses to security groups, including those dynamic groups that use rule-based membership. Moreover, it makes the onboarding process a lot faster and less stressful when connected to HR data or other department roles. However, it requires a different entreprise tier which may be more costly. 

## Licenses

- Since I am utilizing the **Microsoft Intune Plan 1** which is the free tier, I am only allowed to assign 25 licenses. For the sake of demonstration I licensed only one user for now. Please see below: 

### Licensed Used

- View from the admin center > licenses: 

![08-licensed-user](/screenshots/08-licensed-user.png)

- View from the admin center > users > Anna Mueller > licenses: 

![09-licensed-user-more](/screenshots/09-licensed-user-more.png) 