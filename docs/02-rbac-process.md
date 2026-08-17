# Second Objective & Process

## Users 
- The first objective of this second phase was to create test users and populate all the following fields: 
    
    - Display Name
    - First Name
    - Last Name
    - User Principal Name
    - Department
    - Job Title

![02-test-users](/screenshots/02-test-users.png)

### User/s with Populated Fields

![03-user-properties](/screenshots/03-user-properties.png)

![04-user-properties-more](/screenshots/04-user-properties-more.png)

## Groups

- Furthermore, I have implemented Microsoft Entra groups which are widely used in Intune apps to implement policies, configurations, and administrative permissions. 

- I have created **5** administrative groups, which abide to the following naming convention:

    SG = Security Group

    SG-**<Department>**-Users

- These are some examples: 

    1. SG-Operations-Users
    2. SG-Finance-Users
    3. SG-IT-Users

    Some differ due to their uniqueness and are named in the following manner: 

        1. SG-M365-Standard
        2. SG-Intune-Windows

    This aspect is extremely important because it helps the company maintain clear standards.

### Groups Following Naming Conventions

![05-group-membership](/screenshots/05-group-membership.png)

### Groups Populated with Users

![06-group-populated](/screenshots/06-group-populated.png) 

### User's Groups

![07-users-groups](/screenshots/07-users-groups.png)