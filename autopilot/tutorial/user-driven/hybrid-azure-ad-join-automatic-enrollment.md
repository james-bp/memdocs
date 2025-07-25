---
title: Windows Autopilot user-driven Microsoft Entra hybrid join - Step 1 of 10 - Set up Windows automatic Intune enrollment
description: How to - Windows Autopilot user-driven Microsoft Entra hybrid join - Step 1 of 10 - Set up Windows automatic Intune enrollment.
ms.service: windows-client
ms.localizationpriority: medium
author: frankroj
ms.author: frankroj
ms.reviewer: madakeva
manager: bpardi
ms.date: 06/13/2025
ms.topic: tutorial
ms.collection:
  - tier1
  - highpri
ms.subservice: autopilot
appliesto:
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 11</a>
  - ✅ <a href="https://learn.microsoft.com/windows/release-health/supported-versions-windows-client" target="_blank">Windows 10</a>
---

# User-driven Microsoft Entra hybrid join: Set up Windows automatic Intune enrollment

Windows Autopilot user-driven Microsoft Entra hybrid join steps:
> [!div class="checklist"]
>
> - **Step 1: Set up Windows automatic Intune enrollment**

- Step 2: [Install the Intune Connector for Active Directory](hybrid-azure-ad-join-intune-connector.md)
- Step 3: [Increase the computer account limit in the Organizational Unit (OU)](hybrid-azure-ad-join-computer-account-limit.md)
- Step 4: [Register devices as Windows Autopilot devices](hybrid-azure-ad-join-register-device.md)
- Step 5: [Create a device group](hybrid-azure-ad-join-device-group.md)
- Step 6: [Configure and assign Windows Autopilot Enrollment Status Page (ESP)](hybrid-azure-ad-join-esp.md)
- Step 7: [Create and assign Microsoft Entra hybrid join Windows Autopilot profile](hybrid-azure-ad-join-autopilot-profile.md)
- Step 8: [Configure and assign domain join profile](hybrid-azure-ad-join-domain-join-profile.md)
- Step 9: [Assign Windows Autopilot device to a user (optional)](hybrid-azure-ad-join-assign-device-to-user.md)
- Step 10: [Deploy the device](hybrid-azure-ad-join-deploy-device.md)

For an overview of the Windows Autopilot user-driven Microsoft Entra hybrid join workflow, see [Windows Autopilot user-driven Microsoft Entra hybrid join overview](hybrid-azure-ad-join-workflow.md#workflow).

> [!NOTE]
>
> If automatic Intune enrollment is already set up, skip this step and move on to [Step 2: Install the Intune Connector for Active Directory](hybrid-azure-ad-join-intune-connector.md).

## Set up Windows automatic Intune enrollment

In order for Windows Autopilot to work, devices need to be able to enroll in Intune automatically. Enrolling devices in Intune automatically can be configured in the [Azure portal](https://portal.azure.com):

[!INCLUDE [Set up Windows automatic enrollment](../../includes/automatic-intune-enrollment.md)]

## Next step: Install the Intune Connector for Active Directory

> [!div class="nextstepaction"]
> [Step 2: Install the Intune Connector for Active Directory](hybrid-azure-ad-join-intune-connector.md)

## Related content

[!INCLUDE [More information automatic enrollment](../../includes/more-info-automatic-enrollment.md)]
