---
layout: default
title: "HP Helion Public Cloud CLI Software for Windows PowerShell Installation"
permalink: /cli/windows/installation/
product: win-cli
published: false

---
<!--PUBLISHED-->
# HP Helion Public Cloud CLI Software for Windows PowerShell Installation #

To get the HP Helion Public Cloud CLI Software for Windows PowerShell installed and running properly you must complete the following tasks:

*  [Installation Prerequisites](#InstallationPrerequisites)
*  [Run the installer package](#RuntheInstallerPackage)
*  [Choose the appropriate Windows PowerShell executable](#ChooseExecutable)
*  [Supply your credentials](#SupplyyourCredentials)
*  [Navigate to the command line](#NavigatetotheCommandLine)
*  [Load the shell and register the module](#LoadtheShellandModuleRegistration)

This page also describes how to [upgrade to a new version](#Upgrading) of the Windows CLI software.

[Please download the latest version of the HP Helion Public Cloud CLI software package for Windows PowerShell here (Version 1.3.3.9)](/file/WinCLI-1.3.3.9.zip)! 

##Installation Prerequisites## {#InstallationPrerequisites}

The following are prerequisites for installing and running the HP Helion Public Cloud CLI Software for Windows PowerShell.

###Install the Microsoft .NET Framework

This product requires the full (not client profile) 4.0 or higher version of the Microsoft .NET Framework to install properly which can be downloaded [at the Microsoft web site](http://www.microsoft.com/net/).

###Set the Required Execution Policy### {#SettingtheRequiredExecutionPolicy}

To use the HP Helion Public Cloud CLI Software for Windows PowerShell, you must make sure that your Powershell environment is capable of executing 3rd party modules. 

**Note**: If you are performing a re-installation of the software package, you can skip this step.  This step is applicable only for a fresh installation.

Open a PowerShell window as the administrator and issue the command `set-executionpolicy -ExecutionPolicy Unrestricted`:

    PS C:\Projects\Outgoing\HP> set-executionpolicy -ExecutionPolicy Unrestricted
    
    Execution policy change
    The execution policy helps protect you from scripts that you do not trust. Changing the execution policy
    might expose you to the security risks described in the about_Execution_Policies help topic. Do you want to
    change the execution policy?
    [Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
    PS C:\Projects\Outgoing\HP> 

<!--<img src="media/LicenseDialo.png" width="580" height="179" alt="" />-->

Close the Powershell window and reopen as administrator for the policy changes to take effect.

 
##Run the Installer Package## {#RunningtheInstallerPackage}

Download the latest HP Helion Public Cloud CLI software package for Windows PowerShell.  (See the [Release Notes](/cli/windows/release-notes/) for details on the current release.) 

Launching the Windows installer package loads the following wizard.

<img src="media/WizardP1.jpg" width="519" height="424" alt="" />

Click the `Next` button.  In the License Agreement dialog, select the `I Agree` radio button and click `Next`.  

<img src="media/LicenseDialog.png" width="519" height="424" alt="" />

The next window allows you to select your installation folder:

<img src="media/wincli_install02_0.png" width="580" height="475" alt="" />

Unless you need to have the installation files reside in a different folder, we recommend you just stay with the defaults and click `Next`, which takes you to the installation confirmation window:

<img src="media/wincli_install03_0.png" width="580" height="475" alt="" />

The installation now proceeds on your system.

<img src="media/wincli_install04.png" width="580" height="475" alt="" />

<img src="media/wincli_install05.png" width="580" height="475" alt="" />


##Choose the Appropriate Windows PowerShell Executable## {#ChooseExecutable}

Always use the `powershell.exe` appropriate for your OS. From the Windows command line, for 64-bit systems, use `\SysWOW64\powershell.exe`; for 32-bit systems, use `\System32\powershell.exe`.  From the Windows `Start` menu, make sure you select the appropriate PowerShell program.


##Supply your Credentials## {#SupplyyourCredentials}

The first time that you run the shell you must supply the access key, secret key, and tenant ID assigned during the registration process; You can find the values for these variables through the [HP Helion Public Cloud Console](https://horizon.hpcloud.com). Click the project menu and select *Manage Access Keys* and *Account Info*.  You can also define the availability zone during the initial setup.**

**Note: During a new configuration, 
<img src="media/api_keys-2.jpg" width="580" height="471" alt="" />

The shell detects that this is your first time logging in and prompts you for these items. 

    ===============================================================
    Welcome to the HP Helion Public Cloud Powershell Environment.
    ===============================================================
    
       --> Registering Providers. . .
    
    ------------------------------------------------------------------------------------------------------
    We've noticed that you haven't supplied any credentials yet. To continue we need to get your Access Key,
    Secret Key, and the Tenant Id provided to you during the sign up process. If you haven't signed up
    for any services yet, just to go https://console.hpcloud.com for details on how to get started today!
    ------------------------------------------------------------------------------------------------------
    
    Please enter your Access Key :
    
You only need to enter these credentials the first time you run the shell.  After the system verifies your credentials, they are stored and re-used the next time you open the shell.

**Note**: If you see errors at this point, double-check that you are using the [correct powershell executable](#ChooseExecutable), as mentioned earlier. For additional errors that you may encounter, take a look at our Knowledge Base article on [Common Errors Using Windows Powershell CLI](https://community.hpcloud.com/article/common-errors-using-windows-powershell-cli).

<!--<img src="media/PromptCred.jpg" width="580" height="228" alt="" />-->


##Navigate to the Command Line## {#NavigatetotheCommandLine}

To issue HP Helion Public Cloud CLI Windows PowerShell commands (also sometimes called *cmdlets*), you need to first navigate to a container or the HP Helion Public Cloud provider, which you can do by issuing the following command:

    cd HPCS:

##Loading the Shell and Module Registration## {#LoadingtheShellandModuleRegistration}

If you have installed the software through the installer package, registration happens automatically through a supplied Powershell Profile. If the profile was not used, you must move to 
the install folder specified while in the setup wizard. From there you can register the module with Import-Module .\Climanifest.psd1. Note that this only last for the duration of the Powershell session and it's recommended to add this command to your Profile for best results.

##Upgrading to a New Version## {#Upgrading}

When you upgrade to a new version of the HP Helion Public Cloud environment CLI software for Windows PowerShell, you must first de-install the previous version of the software.  You can do this using the Windows `Add/Remove Programs` or `Programs and Features` utility (depending on the version of Windows you're using).  Search through the listing of programs for "HPCS-Powershell" and uninstall it.  

Once you have uninstalled the previous revision, simply follow the instructions above to install the latest version, and you're be good to go!
