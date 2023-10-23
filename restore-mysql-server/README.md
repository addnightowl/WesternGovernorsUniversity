### C916 Scripting and Automation – Task 2

## Requirements
<#

.SYNOPSIS

This script restores Active Directory OU's and reconfigures SQL Server 2019.

.DESCRIPTION

A. Create a PowerShell script named “restore.ps1” within the “Requirements2” folder. For the first line, create a comment and include your first and last name along with your student ID.

Note: The remainder of this task shall be completed within the same script file, “restore.ps1.”

B. Write a single script within the “restore.ps1” file that performs all of the following functions without user interaction:

1. Create an Active Directory organizational unit (OU) named “finance.”

2. Import the financePersonnel.csv file (found in the “Requirements2” directory) into your Active Directory domain and directly into the finance OU. Be sure to include the following properties:

• First Name

• Last Name

• Display Name (First Name + Last Name, including a space between)

• Postal Code

• Office Phone

• Mobile Phone

3. Create a new database on the UCERTIFY3 SQL server instance called “ClientDB”.

4. Create a new table and name it “Client_A_Contacts.” Add this table to your new database.

5. Insert the data from the attached “NewClientData.csv” file (found in the “Requirements2” folder) into the table created in part B4.

C. Apply exception handling using try-catch for System.OutOfMemoryException.

D. Run the script within the uCertify environment. After the script executes successfully, run the following cmdlets individually from within your Requirements2 directory:

1. Get-ADUser -Filter * -SearchBase “ou=finance,dc=ucertify,dc=com” -Properties DisplayName,PostalCode,OfficePhone,MobilePhone > .\AdResults.txt

2. Invoke-Sqlcmd -Database ClientDB –ServerInstance .\UCERTIFY3 -Query ‘SELECT * FROM dbo.Client_A_Contacts’ > .\SqlResults.txt

Note: Ensure you have all of the following files intact within the “Requirements2” folder, including the original files:

• “export.ps1”

• “restore.ps1”

• “AdResults.txt”

• “SqlResults.txt”

.NOTES Version: 1.0 Author: Anthony Dewayne Davis Creation Date: 21 August 2021 Purpose: Initial Script Development

#>