# Introduction
The Microsoft Teams Data Collector is a PowerShell script useful for easily collecting and packaging various data for troubleshooting Microsoft Teams desktop client issues on Windows.

This tool does not transmit or share the data collected, it simply produces a ZIP file containing the data.

[![Version](https://img.shields.io/github/v/release/microsoft/TeamsDataCollector?label=latest%20version)](https://github.com/microsoft/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip)
[![Downloads](https://img.shields.io/github/downloads/microsoft/TeamsDataCollector/total)](https://github.com/microsoft/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip)

# Getting Started
PowerShell **5.0** (or greater) must be installed on the host machine. Click [here](https://github.com/powershell/powershell) for details
on how to get the latest version for your computer. 

# Usage
1. [Download](https://github.com/microsoft/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip) the script package.

2. Extract it on to the computer experiencing Teams issues.

     ![Extract](https://user-images.githubusercontent.com/79993173/109880924-802db980-7c45-11eb-9897-42921631dd24.png)

3. Run the CollectTeamsClientData.ps1 script, either by double clicking on the file, or by right clicking on it and choosing "Run with PowerShell".

     ![RunWithPowerShell](https://user-images.githubusercontent.com/79993173/109881134-c256fb00-7c45-11eb-929a-ef73a7e3cff4.png)

4. Once the script is complete, it should produce a ZIP file in the same folder as the script.

     ![ZipFile](https://user-images.githubusercontent.com/79993173/109881493-65a81000-7c46-11eb-8f8f-b5d42f678272.png)

# Advanced Usage
```
CollectTeamsClientData.ps1 [-Help]

CollectTeamsClientData.ps1 [[-Destination] <path>] [[-Scenario] <scenario name>]

  -Help       : Displays this help message. This will list available scenarios.

  -Destination: Provides the destination for the ZIP file produced by this script.
                If one is not provided, it will default to the script location.

  -Scenario   : Provides the scenario name to collect.
                If one is not provided, it will default to "All".
```                
# Data Collected
The script collects various files, registry keys, and enumerates various directories.
It will list each file and registry key that it collects, and each directory it enumerates.

It also collects:
- General computer information (Get-ComputerInfo)
- Time, culture, and language information (Get-TimeZone, Get-WinSystemLocale, Get-WinUserLanguageList, Get-Culture)
- Display information (Get-WmiObject win32_videocontroller)
- Drive information (Get-PSDrive, Get-PhysicalDisk, Get-Volume)
- Network information (Get-NetAdapter, Get-NetIPAddress)
- Running processes (Get-Process)
- Application and System event logs

The data collected by the script may contain End-User Identifiable Information (EUII).
This could include, but is not limited to:
- Computer name
- User name
- Email addresses
- SIP addresses
- IP addresses
- MAC addresses
- Telephone numbers (calling or called)
- User IDs (such as AAD Object GUID)

The script does NOT collect passwords or any other credential information.

The ZIP file produced by the script can be opened and its contents reviewed.

# Example
![ExampleRun](https://user-images.githubusercontent.com/79993173/109887130-377afe00-7c4f-11eb-92c4-a04daa9ae23b.png)


# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
