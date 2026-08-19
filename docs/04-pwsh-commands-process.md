# Fourth Objective & Process

- For this phase I am going to start using user-management commands manually in PowerShell.

## Setup

- Microsoft recommends to use the PowerShell 7+ along with Microsfot Graph PowerShell, hence: 

    - PowerShell 7+:

    ![10-pwsh-version](/screenshots/10-pwsh-version.png)

    - Microsfot Graph PowerShell: 

    ![11-pwsh-graph-version](/screenshots/11-pwsh-graph-version.png)

- Next, I will be taking advantage of Microsoft's granular permissions and I will connect my company to my PowerShell. I have only requested access for things I need right now. 

    - Command used: 

        ```PowerShell 
        Connect-MgGraph -Scopes ` "User.ReadWrite.All", "Group.ReadWrite.All", "Directory.ReadWrite.All"
        ```
    - Output: 

    ![12-mggraph-connection](/screenshots/12-mggraph-connection.png)

    - Context: 

    ![13-mggraph-context](/screenshots/13-mggraph-context.png)

## Manual Commands 

- List Users:

! [14-getuser-command](/screenshots/14-getuser-command.png)

    - By adding a **"| Select-Object"** after "-All" we can choose the attributes from the user that we would like to list, such as **DisplayName** or **Department**.

- List Groups:

![15-getgroup-command](/screenshots/15-getgroup-command.png)

- Find a Group: 

![16-findgroup-command](/screenshots/16-findgroup-command.png)

## Check

- Now that I know that the environment is ready and functional, I can move to the next objective: **Building the Automated Onboarding Script**