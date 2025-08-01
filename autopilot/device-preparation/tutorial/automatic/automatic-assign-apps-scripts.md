---
title: Windows Autopilot device preparation in automatic mode for Windows 365 (preview) - Step 3 of 6 - Assign applications and PowerShell scripts to device group
description: How to - Windows Autopilot device preparation in automatic mode for Windows 365 (preview) - Step 3 of 6 - Assign applications and PowerShell scripts to device group.
ms.service: windows-client
ms.localizationpriority: medium
author: frankroj
ms.author: frankroj
ms.reviewer: madakeva
manager: aaroncz
ms.date: 06/11/2025
ms.topic: tutorial
ms.collection:
  - tier1
  - highpri
ms.subservice: autopilot
appliesto:
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 11</a>
---

# Windows Autopilot device preparation in automatic mode for Windows 365 (preview): Assign applications and PowerShell scripts to device group

Windows Autopilot device preparation in automatic mode for Windows 365 steps:

- Step 1: [Set up Windows automatic Intune enrollment](automatic-automatic-enrollment.md)
- Step 2: [Create an assigned device group](automatic-device-group.md)

> [!div class="checklist"]
>
> - **Step 3: Assign applications and PowerShell scripts to device group**

- Step 4: [Create Windows Autopilot device preparation policy](automatic-autopilot-policy.md)
- Step 5: [Create a Cloud PC provisioning policy](automatic-cloud-pc-provisioning-policy.md)
- Step 6: [Monitor the deployment](automatic-monitor.md)

For an overview of the Windows Autopilot device preparation in automatic mode for Windows 365 workflow, see [Windows Autopilot device preparation in automatic mode for Windows 365 overview](automatic-workflow.md#workflow).

## Assign applications and PowerShell scripts to device group

During the out-of-box experience (OOBE) experience before the end-user is signed in for the first time, Windows Autopilot device preparation allows deployment of up to:

- 10 managed applications
- 10 PowerShell scripts

The applications and PowerShell scripts specified should be the essential applications to install and the essential PowerShell scripts to run before the end-user can start using the device.

Any applications installed or PowerShell scripts that run during a Windows Autopilot device preparation deployment should be configured to install in the **System** context since the applications are installed and the PowerShell scripts ran during OOBE when no user is signed in.

For applications to install and PowerShell scripts work successfully during a Windows Autopilot device preparation deployment, two steps need to be taken:

1. They must be assigned to the device group created for Windows Autopilot device preparation in [Step 3: Create an assigned device group](automatic-device-group.md). This step is covered in this article.
2. They must be specified as part of the Windows Autopilot device preparation policy. This step is covered in the next step [Step 5: Create Windows Autopilot device preparation policy](automatic-autopilot-policy.md).

> [!NOTE]
>
> The below steps assume that the applications or PowerShell scripts that will be deployed during Windows Autopilot device preparation deployment are already added to Intune. For more information on how to add applications and PowerShell scripts to Intune if they aren't already created, see [Add apps to Microsoft Intune](/mem/intune-service/apps/apps-add) and [Use PowerShell scripts on Windows devices in Intune](/mem/intune-service/apps/intune-management-extension).

### Applications

The following types of applications are supported for use with Windows Autopilot device preparation:

- [Line-of-business (LOB)](/mem/intune-service/apps/lob-apps-windows).
- [Win32](/mem/intune-service/apps/apps-win32-prepare).
- [Microsoft Store](/mem/intune-service/apps/store-apps-microsoft) - only Microsoft Store apps that support WinGet are supported.
- [Microsoft 365](/mem/intune-service/apps/apps-add-office365).
- [Enterprise App Catalog](/intune/intune-service/apps/apps-add-enterprise-app).

In addition, Windows Autopilot device preparation supports deploying both Win32 and line-of-business (LOB) applications in the same deployment.

To assign the desired applications to the device group created for Windows Autopilot device preparation:

1. Sign into the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. In the **Home** screen, select **Apps** in the left hand pane.

1. In the **Apps | Overview** screen, under **By platform**, select **Windows**.

1. In the **Windows | Windows apps** screen, scroll through the list of applications and then select the desired application that should be installed during the Windows Autopilot device preparation deployment. Alternatively, use the **Search by name or publisher** box to search for the application, and then select it.

1. Once the application is selected, a new screen opens showing the application. Under **Manage**, select **Properties**.

1. In the **Properties** screen, next to **Assignments**, select **Edit**.

1. In the **Edit application** screen:

   1. Under the **Required** section, select **Add group**. The **Select groups** pane opens.

   1. In the **Select groups** pane:

      1. Scroll through the list of groups. Once the Windows Autopilot device preparation device security group is located, select it. Alternatively, use the **Search** box to locate the Windows Autopilot device preparation device security group and then select it.

      1. Once the Windows Autopilot device preparation device security group is selected, select **Select**.

   1. Verify that the Windows Autopilot device preparation device security group is listed under the **Required** section. Additionally, verify that **Group mode** is set to **Included**. When applicable, also verify that **Install Context** is set to **Device context**.

   1. Once everything is verified, select **Review + save**.

   1. In the **Review + save** screen, select **Save**.

1. Repeat the steps for any additional applications that need to be installed during the Windows Autopilot device preparation deployment.

### PowerShell scripts

To assign the desired PowerShell scripts to the device group created for Windows Autopilot device preparation:

1. Sign into the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431).

1. In the **Home** screen, select **Devices** in the left hand pane.

1. In the **Devices | Overview** screen, expand **Manage devices**, and then select **Scripts and remediations**.

1. In the **Devices | Scripts and remediations** screen:

   1. Select **Platform scripts**.

   1. Scroll through the list of PowerShell scripts and then select the desired PowerShell script that should run during the Windows Autopilot device preparation deployment. Alternatively, use the **Search** box to search for the PowerShell script, and then select it.

1. Once the PowerShell script is selected, a new screen opens showing the PowerShell script. Under **Manage**, select **Properties**.

1. In the **Properties** screen, next to **Assignments**, select **Edit**.

1. In the **Edit PowerShell script** screen:

   1. Under the **Included groups** section, select **Add groups**. The **Select groups to include** pane opens.

   1. In the **Select groups to include** pane:

      1. Scroll through the list of groups. Once the Windows Autopilot device preparation device security group is located, select it. Alternatively, use the **Search** box to locate the Windows Autopilot device preparation device security group and then select it.

      1. Once the Windows Autopilot device preparation device security group is selected, select **Select**.

   1. Verify that the Windows Autopilot device preparation device security group is listed under the **Included groups** section. Make sure that the Windows Autopilot device preparation device security group wasn't accidentally added under the **Excluded groups** section.

   1. Once everything is verified, select **Review + save**.

   1. In the **Review + save** screen, select **Save**.

## Next step: Create Windows Autopilot device preparation policy

> [!div class="nextstepaction"]
> [Step 4: Create Windows Autopilot device preparation policy](automatic-autopilot-policy.md)

## Related content

- [Add apps to Microsoft Intune](/mem/intune-service/apps/apps-add).
- [Use PowerShell scripts on Windows devices in Intune](/mem/intune-service/apps/intune-management-extension).
- [Assign apps to groups with Microsoft Intune](/mem/intune-service/apps/apps-deploy).
- [Win32 app management in Microsoft Intune](/mem/intune-service/apps/apps-win32-app-management).
- [Add a Windows line-of-business app to Microsoft Intune](/mem/intune-service/apps/lob-apps-windows).
