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
ms.openlocfilehash: a6aa59a798e06c407c1bbde6734ec9ab3ecedcd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58637020"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrieren eines Geräts beim verwalteten Microsoft Teams-Räume Premium Dienst

Um ein Microsoft Teams-Räume-Gerät beim verwalteten Dienst von Teams-Räume Premium zu registrieren, müssen Sie dem Administrator für verwaltete Dienste einen weiteren Benutzer zuweisen und dann die Registrierungsschritte mit diesem Benutzer ausführen.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Zuweisen von Benutzern zur Administratorrolle "Verwalteter Dienst"

Führen Sie die folgenden Schritte aus, um Benutzer der Administratorrolle "Verwalteter Dienst" zuzuordnen:

1. Melden Sie sich beim [Teams-Räume Premium-Portal](https://portal.rooms.microsoft.com/) mit den gleichen Administratorrechten wie bei der Anmeldung beim Microsoft 365 Admin Center.
2. Navigieren Sie **zu Einstellungen**  >    >  **Einstellungen,** und wählen Sie dann **Administrator für verwaltete Dienste aus.**
3. Wählen **Sie unter Administrator für verwaltete** Dienste die **Registerkarte** Aufgaben und dann Hinzufügen **aus.**
4. Folgen Sie dem Assistenten, um die Aufgabe zu benennen und die Benutzer auszuwählen, die der Aufgabe hinzugefügt werden sollen. Die Zuweisung gilt für alle Räume und Raumgruppen.
5. Wählen Sie am Ende des Aufgaben-Assistenten Aufgabe **hinzufügen aus.**

Benutzer, denen die Rolle "Administrator für verwaltete Dienste" zugewiesen ist, sind für die täglichen Verwaltung und Überwachung des Teams-Räume Premium Dienstportals verantwortlich.

Nachdem Sie Benutzer der Administratorrolle für verwaltete [](#enroll-a-teams-rooms-device) Dienste zugewiesen haben, fahren Sie mit dem Abschnitt Registrieren eines Geräts fort, um dem Portal für verwaltete Dienste ein Teams-Räume-Gerät hinzuzufügen.

## <a name="enroll-a-teams-rooms-device"></a>Registrieren eines Teams-Räume Geräts

Führen Sie die folgenden Schritte aus, um ein Gerät bei dem verwalteten Teams-Räume Premium zu registrieren:

1. Melden Sie sich beim [Teams-Räume Premium-Portal](https://portal.rooms.microsoft.com/) mit einem Benutzer an, dem die Rolle "Administrator für verwaltete Dienste" zugewiesen wurde.
2. Wählen Sie auf dem **?** in der oberen rechten Ecke des Portals, um das Hilfemenü zu öffnen. Das Hilfemenü enthält einen [Installationsleitfaden mit](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) detaillierten Registrierungsanweisungen:

    1. Lesen Sie **den Abschnitt Voraussetzungen** im Installationshandbuch. Vergewissern Sie sich, dass die **URLs,** die in der Liste Für Kommunikation erforderliche URLs aufgeführt sind, der Liste zulassen von Datenverkehr ihrer Firewall hinzugefügt werden.
    2. Folgen Sie den Anweisungen im Abschnitt **Aktivieren von TPM Einstellungen,** um die TPM-Funktionalität (Trusted Platform Module) auf Ihrem Gerät zu aktivieren.
    3. Folgen Sie den Anweisungen im Abschnitt Hinzufügen von **Proxy Einstellungen,** um Ihr Gerät für die Verwendung Ihres Proxygateways zu konfigurieren, sofern Sie über eines verfügen.
    4. Folgen Sie den Anweisungen im Abschnitt **Prozess,** um die Überwachungs-Agent-Software zu installieren und den Selbstregistrierungsschlüssel auf Ihrem Gerät zu konfigurieren.

3. Nachdem der Überwachungs-Agent und der eindeutige XML-Schlüssel auf Ihrem Gerät konfiguriert wurden, navigieren Sie zu Räume **>** Raumname > **Status**, und wählen Sie dann Registrieren **aus.**

    > [!NOTE]
    > Das Teams-Räume Gerät verbleiben im **Onboarding-Zustand,** bis ein Administrator für verwaltete Dienste das Gerät über das Portal registriert.

## <a name="link-to-installation-guide"></a>Link zum Installationshandbuch

Das **Menü Hilfe** enthält einen Link zum [Installationshandbuch,](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) das wiederum die folgenden Informationen enthält:

- Anweisungen zu URLs, die aufgelistet werden müssen, damit Raum-Telemetrie an den verwalteten Dienst gesendet werden kann.
- Anweisungen zum Anwenden Microsoft Teams-Räume Premium Überwachungs-Agents und des eindeutigen XML-Schlüssels als Teil der Registrierung eines Geräts im verwalteten Dienst.
- Anleitungen zur Problembehandlung.
