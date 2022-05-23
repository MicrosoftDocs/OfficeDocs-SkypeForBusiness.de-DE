---
title: Registrieren eines Teams-Räume Geräts im Microsoft Teams-Räume Premium verwalteten Dienst
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Microsoft Teams-Räume Konten in Microsoft Teams-Räume Premium verwalteten Dienst registrieren.
f1keywords: ''
ms.openlocfilehash: c64fcaf6e817eb57be2915f4f7b6d8684f2ae49b
ms.sourcegitcommit: d425748a50964ebc78e5d38fce564a444a449f43
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65635453"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrieren eines Geräts im Microsoft Teams-Räume Premium verwalteten Dienst

Um ein Microsoft Teams-Räume Gerät im Teams-Räume Premium verwalteten Dienst zu registrieren, müssen Sie einen oder mehrere Benutzer dem Administrator für verwaltete Dienste zuweisen und dann die Registrierungsschritte mit diesem Benutzer ausführen.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Zuweisen von Benutzern zur Rolle "Verwalteter Dienstadministrator"

Führen Sie die folgenden Schritte aus, um Benutzer der Rolle "Verwalteter Dienstadministrator" zuzuweisen:

1. Melden Sie sich beim [Teams-Räume Premium-Portal](https://portal.rooms.microsoft.com/) mit den gleichen Administratorberechtigungen an wie bei der Anmeldung beim Microsoft 365 Admin Center.
2. Navigieren Sie zu **Einstellungen** >  **Einstellungen** >  **Roles**, und wählen Sie dann "**Verwalteter Dienstadministrator**" aus.
3. Wählen Sie unter " **Verwalteter Dienstadministrator**" die Registerkarte " **Aufgaben** " und dann " **Hinzufügen"** aus.
4. Folgen Sie dem Assistenten, um die Aufgabe zu benennen und die Benutzer auszuwählen, die ihr hinzugefügt werden sollen. Die Aufgabe gilt für alle Räume und Raumgruppen.
5. Wählen Sie am Ende des Aufgaben-Assistenten " **Aufgabe hinzufügen"** aus.

Benutzer, denen die Rolle "Verwalteter Dienstadministrator" zugewiesen ist, sind für die tägliche Verwaltung und Überwachung des Teams-Räume Premium verwalteten Dienstportals verantwortlich.

Nachdem Sie Benutzern die Rolle "Verwalteter Dienstadministrator" zugewiesen haben, fahren Sie mit der [Registrierung eines Teams-Räume Geräts](enroll-a-device.md) fort, um dem Portal für verwaltete Dienste ein Teams-Räume Gerät hinzuzufügen.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
