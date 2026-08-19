# Fifth Objective & Process

- For this objective I will running through the steps needed to create the  **Automated Onboarding Script**

- These are the following steps: 

1. Load the **csv** file: 

    ![17-load-users](/screenshots/17-load-users.png)

2. Basic loop to print out **First + Last Name:**

    ![18-loop-through-users](/screenshots/18-loop-through-users.png) 

3. Loop to generate the UPN:

    Command used: 

    ```Powershell
    foreach ($user in $users) {
    $firstName = $user.FirstName.ToLower()
    $lastName = $user.LastName.ToLower()
    $upn = "$firstName.$lastName@testlogisticslab.onmicrosfot.com"
    }
    ```

    ![19-upn-generation](/screenshots/19-upn-generation.png)

4. Temporary password creation: 

    - After creating the temporary password I will run the following command which holds the temporary password for the first login and for the second one it forces the user to change the password: 

    ```PowerShell
    $passwordProfile = @{                                               
    Password = $tempPassword
    ForceChangePasswordNextSignIn = $true
    }
    ```

    ![20-temp-password-setup](/screenshots/20-temp-password-setup.png)

- The **aim** of these initial 4 steps is to demonstrate a proper **lifecycle behavior.**


## Users & Workflow

- Create users with error handling, these changes get automatically reflected in **Entra**: 

    ```PowerShell
    $users = Import-Csv ./users.csv
    $domain = "testlogisticslab.onmicrosoft.com"

    foreach ($user in $users) {
    $firstName = $user.FirstName.ToLower()
    $lastName  = $user.LastName.ToLower()
    $upn       = "$firstName.$lastName@$domain"
    
    $passwordProfile = @{
        Password = "testlogisticslab2026!"
        ForceChangePasswordNextSignIn = $true
    }

    try {
        Write-Host "Creating $upn..."

        New-MgUser `
            -DisplayName "$($user.FirstName) $($user.LastName)" `
            -GivenName $user.FirstName `
            -Surname $user.LastName `
            -UserPrincipalName $upn `
            -MailNickname "$firstName.$lastName" `
            -Department $user.Department `
            -JobTitle $user.JobTitle `
            -AccountEnabled `
            -PasswordProfile $passwordProfile

        Write-Host "SUCCESS: $upn"
    }
    catch {
        Write-Host "ERROR creating $upn"
        Write-Host $_.Exception.Message
    }
    }
    ```

- Output:

    ```PowerShell
    SUCCESS: julia.schmidt@testlogisticslab.onmicrosoft.com
    Creating michael.huber@testlogisticslab.onmicrosoft.com...
    ```