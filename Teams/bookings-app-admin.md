---
title: Buchungen-APP und virtuelle Besuche in Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft Teams und virtuelle Besuche mit der App "Buchungen"
ms.openlocfilehash: c60993b57233c0c526e1770c1d3d414a73fcc42a
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427680"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a>Buchungen-APP und virtuelle Besuche in Microsoft Teams

Die app "Buchungen" in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlichen und virtuellen Terminen wie Gesundheits Besuche, Finanzberatungen, Interviews, Kundendienst, Unterrichtsstunden und vieles mehr.

Planer können mehrere Abteilungs-und Personal Kalender sowie die Kommunikation mit internen und externen Teilnehmern aus einer einzigen Erfahrung verwalten. Die virtuellen Termine selbst werden über Microsoft Teams-Besprechungen abgehalten, die robuste Videokonferenzfunktionen bieten.

> [!NOTE]
> Nur Planer müssen die app "Buchungen" in Teams installieren. Mitarbeiter, die an virtuellen Terminen teilnehmen, benötigen die APP nicht. Sie können einfach an Terminen aus Ihrem Outlook-oder Teams-Kalender oder über einen Link in ihrer Buchungs Bestätigungs-e-Mail teilnehmen.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der App "Buchungen" in Teams

- Das Exchange-Postfach muss sich in Exchange Online befinden. Lokale Exchange Server-Postfächer werden nicht unterstützt.

- Microsoft-Buchungen müssen für die Organisation aktiviert sein.

- Benutzer müssen über eine entsprechende Lizenz verfügen. Office 365 a3, A5, E3 und E5 sowie Microsoft 365 Business Standard, a3, A5, E3 und E5 werden unterstützt.

- Alle Benutzer der App "Buchungen" und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Terminplanung für Teams unterstützt.

- Ihre Systeme müssen alle [Voraussetzungen für Software und Browser](hardware-requirements-for-the-teams-app.md)erfüllen.

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Buchungen in Teams

Die Microsoft-Buchungs-App für Teams steht auf dem Desktop und im Web zur Verfügung. Sie finden Sie unter [apps in Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **Verwalten von apps** innerhalb des Admin Centers von Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf Buchungen in Ihrer Organisation

Es gibt mehrere Möglichkeiten, zu steuern, wer Zugriff auf die app "Buchungen" hat und welche Features für die app verfügbar sind. Informationen zum Aktivieren oder Deaktivieren von Microsoft-Buchungen im Microsoft 365 Admin Center sowie zum Erstellen einer APP-Richtlinie für Buchungen, mit der ausgewählte Benutzer Buchungen für Kalender erstellen können, finden Sie unter [Abrufen des Zugriffs auf Microsoft-Buchungen](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Sie können auch erfahren, wie Sie [eine Teams-App-Richtlinie erstellen, um die Buchungen-App für ausgewählte Benutzer zu anheften](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Einstellungen für Besprechungsrichtlinien

Erstellen Sie eine Personal Besprechungsrichtlinie, damit **alle Personen in Ihrer Organisation**automatisch zugelassen werden, um die beste Benutzerfreundlichkeit für Buchungen zu ermöglichen. Auf diese Weise können die Mitarbeiter automatisch an dem Termin teilnehmen und die Lobby-Erfahrung für externe Teilnehmer aktivieren. Weitere Informationen finden Sie [unter Automatisches zulassen von Personen für Besprechungen](meeting-policies-in-teams.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Optionale Einstellung für Mitarbeiter Genehmigungen

Als zusätzliche Privatsphäre-Einstellung können Sie festlegen, dass die Mitarbeiter sich anmelden müssen, bevor Ihre Terminplan Verfügbarkeitsinformationen durch Buchungen freigegeben werden und bevor Sie für einen Termin gebucht werden können.  

Wenn Sie diese Einstellung aktivieren möchten, wechseln Sie zu den Einstellungen für **Microsoft 365 Admin Center** \> **Settings** \> **Settings**, und wählen Sie dann **Buchungen**aus.

Wenn diese Einstellung aktiviert ist, erhält das Personal eine e-Mail, in der Sie aufgefordert werden, die Mitgliedschaft in einem Buchungskalender zu genehmigen.  

Dieses Feature wird nach und nach weltweit für Microsoft 365-und Office 365-Kunden eingeführt. Wenn in Ihrer Umgebung noch keine Optionen zur Verfügung stehen, schauen Sie bald wieder vorbei.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Ändern ihrer Standarddomäne beim Einrichten von Buchungs Postfächern

Beim Einrichten eines Postfachs für Buchungen wird die standardmäßige e-Mail-Domäne Ihrer Microsoft 365-oder Office 365-Organisation verwendet. Dies kann jedoch zu Problemen beim Senden von Besprechungseinladungen an externe Empfänger führen. Ihre Einladung wird möglicherweise als "Spam" gekennzeichnet und in den Junk-Ordner des Empfängers verschoben, sodass der Empfänger Ihre Einladung möglicherweise nie sehen kann.

Wir empfehlen, dass Sie vor dem Erstellen des Postfachs für Buchungen die Standarddomäne ändern. Informationen dazu finden Sie in den [FAQ zu Domains](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Wenn Sie die Standarddomäne ändern müssen, nachdem das Postfach für Buchungen bereits erstellt wurde, können Sie dies mit PowerShell tun:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation für das Cmdlet " [Satz-Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) ".

> [!NOTE]
> Wenn Sie eine Exchange-Hybrid Konfiguration verwenden, empfiehlt es sich, den Nachrichtenfluss zwischen lokalen Exchange und Exchange Online beim Ändern der Standarddomäne gründlich zu testen.

## <a name="sending-feedback"></a>Senden von Feedback

Wir freuen uns über Ihr Feedback zu:

  - Benutzererfahrung oder einfache Bedienung
  - Funktionslücken oder fehlende Funktionalität
  - Bugs oder Probleme
  
Um Feedback zu senden, klicken Sie auf die Schaltfläche " **Hilfe** " am unteren Rand der linken Navigationsleiste von Teams, und klicken Sie dann auf **Problem melden** für **alle** Probleme. Bitte beachten Sie zu Beginn Ihres Feedback-Berichts, dass Sie Feedback zu "Buchungen" senden, damit wir Buchungs Probleme einfach erkennen können.

## <a name="related-topics"></a>Verwandte Themen

[Buchungsdokumentation für Endbenutzer](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
