---
title: Registrieren eines Teams-Räume-Geräts im verwalteten Microsoft Teams-Räume Premium Dienst
author: v-smandalika
ms.author: v-smandalika
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
description: Erfahren Sie, wie Sie Microsoft Teams-Räume Konten in einem verwalteten Microsoft Teams-Räume Premium registrieren.
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766968"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrieren eines Geräts beim verwalteten Microsoft Teams-Räume Premium Dienst

Um ein Microsoft Teams-Räume-Gerät beim verwalteten Dienst Teams-Räume Premium zu registrieren, müssen Sie dem Administrator für verwaltete Dienste einen weiteren Benutzer zuweisen und dann die Registrierungsschritte mit diesem Benutzer ausführen.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Zuweisen von Benutzern zur Administratorrolle "Verwalteter Dienst"

Führen Sie die folgenden Schritte aus, um Benutzer der Administratorrolle "Verwalteter Dienst" zuzuordnen:

1. Melden Sie sich beim [Teams-Räume Premium-Portal](https://portal.rooms.microsoft.com/) mit den gleichen Administratorrechten wie bei der Anmeldung beim Microsoft 365 Admin Center.
2. Navigieren Sie **zu Einstellungen**  >    >  **Einstellungen,** und wählen Sie dann **Administrator für verwaltete Dienste aus.**
3. Wählen **Sie unter Administrator für verwaltete** Dienste die **Registerkarte** Aufgaben und dann Hinzufügen **aus.**
4. Folgen Sie dem Assistenten, um die Aufgabe zu benennen und die Benutzer auszuwählen, die der Aufgabe hinzugefügt werden sollen. Die Zuweisung gilt für alle Räume und Raumgruppen.
5. Wählen Sie am Ende des Aufgaben-Assistenten Aufgabe **hinzufügen aus.**

Benutzer, denen die Rolle "Administrator für verwaltete Dienste" zugewiesen ist, sind für die Täglichen Verwaltung und Überwachung des Portals Teams-Räume Premium Dienstverwaltung verantwortlich.

Nachdem Sie Benutzer der Administratorrolle für verwaltete [](#enroll-a-teams-rooms-device) Dienste zugewiesen haben, fahren Sie mit dem Abschnitt Registrieren eines Geräts fort, um dem Portal für verwaltete Dienste ein Teams-Räume-Gerät hinzuzufügen.

## <a name="enroll-a-teams-rooms-device"></a>Registrieren eines Teams-Räume Geräts

 Informationen zum Registrieren eines Geräts bei Teams-Räume Premium Dienst finden Sie unter [Überwachen der Gerätesoftwareinstallation.](monitor-software-installation-guide.md)

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
