---
title: Virtuelle Besuche mit Microsoft Teams und der App Bookings
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams und virtuelle Besuche mit der Bookings-App
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125748"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Virtuelle Besuche mit Microsoft Teams und der App Bookings

Die App Bookings in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlichen und virtuellen Terminen, z. B. Arztbesuche, Finanzberatungen, Vorstellungsgespräche, Kundensupport, Sprechstunden für Bildungseinrichtungen und vieles mehr.

Planer können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Benutzererfahrung verwalten. Die virtuellen Termine selbst werden über Microsoft Teams-Besprechungen abgehalten, die stabile Videokonferenzfunktionen bieten.

> [!NOTE]
> Nur Planer müssen die App Bookings in Teams installiert haben. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie können einfach über ihren Outlook- oder Teams-Kalender oder über einen Link in der Buchungsbestätigungs-E-Mail an Termine teilnehmen.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der App "Bookings" in Teams

- Das Exchange-Postfach muss in Exchange Online gespeichert sein. Lokale Exchange Server werden nicht unterstützt.

- Microsoft Bookings muss für die Organisation aktiviert sein.

- Benutzer müssen über eine entsprechende Lizenz verfügen. Office 365 A3, A5, E3 und E5 sowie Microsoft 365 Business Standard, A3, A5, E3 und E5 werden unterstützt.

- Alle Benutzer der App Bookings und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Planung von Besprechungen in Teams unterstützt.

- Ihre Systeme müssen alle Voraussetzungen [für Software und Browser erfüllen.](hardware-requirements-for-the-teams-app.md)

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Bookings in Teams

Die Microsoft Bookings-App für Teams ist auf dem Desktop und im Web verfügbar. Sie finden sie unter ["Apps" in Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **"Apps im** Teams Admin Center verwalten".

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf Bookings innerhalb Ihrer Organisation

Es gibt mehrere Möglichkeiten zu steuern, wer Zugriff auf die Bookings-App und auf bestimmte Features der App hat. Informationen zum Aktivieren oder Deaktivieren von Microsoft Bookings im Microsoft 365 Admin Center sowie zum Erstellen einer Bookings-App-Richtlinie, die es ausgewählten Benutzern ermöglicht, Bookings-Kalender zu erstellen, finden Sie unter "Zugriff auf [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)erhalten". Sie erfahren auch, wie Sie eine Teams-App-Richtlinie erstellen, um die [App Bookings für ausgewählte Benutzer zu anheften.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Besprechungsrichtlinieneinstellungen

Um eine optimale Benutzererfahrung für Bookings zu ermöglichen, erstellen Sie eine Besprechungsrichtlinie für Mitarbeiter, um automatisch alle **Benutzer in Ihrer Organisation zu lassen.** Auf diese Weise können die Mitarbeiter dem Termin automatisch beitreten und die Lobby für externe Teilnehmer aktivieren. Erfahren Sie mehr darüber, [wie Sie Personen automatisch zu Besprechungen zu lassen.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Einstellung für die optionale Genehmigung von Mitarbeitern

Als zusätzliche Datenschutzeinstellung können Sie festlegen, dass mitarbeiter müssen, die sich für den Terminplan entscheiden müssen, bevor die Verfügbarkeitsinformationen für den Zeitplan über Bookings freigegeben werden und bevor sie für einen Termin gebucht werden können.  

Um diese Einstellung zu aktivieren, wechseln Sie zu **"Einstellungen" im Microsoft 365 Admin** \>  \> **Center,** und wählen Sie dann **Bookings aus.**

Wenn diese Einstellung aktiviert ist, erhalten die Mitarbeiter eine E-Mail, in der sie aufgefordert werden, die Mitgliedschaft in einem Buchungskalender zu genehmigen.  

Dieses Feature wird schrittweise weltweit für Microsoft 365- und Office 365-Kunden eingeführt. Wenn in Ihrer Umgebung noch nicht alle Optionen verfügbar sind, schauen Sie bald wieder nach.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Ändern Ihrer Standarddomäne beim Einrichten von Bookings-Postfächern

Beim Einrichten eines Bookings-Postfachs wird die standardmäßige E-Mail-Domäne Ihrer Microsoft 365- oder Office 365-Organisation verwendet. Dies kann jedoch zu Problemen führen, wenn Besprechungsbesprechungen an externe Empfänger gesendet werden. Ihre Einladung wird möglicherweise als Spam gekennzeichnet und in den Junk-E-Mail-Ordner des Empfängers verschoben, sodass die Einladung dem Empfänger möglicherweise nie angezeigt wird.

Wir empfehlen, die Standarddomäne vor dem Erstellen Ihres Bookings-Postfachs zu ändern. Informationen dazu finden Sie in den häufig gestellten Fragen [zu Domänen.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Wenn Sie die Standarddomäne ändern müssen, nachdem Ihr Postfach in Bookings bereits erstellt wurde, können Sie dies mit PowerShell tun:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation für das [Cmdlet "Set-Mailbox".](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Wenn Sie eine Exchange-Hybridkonfiguration verwenden, empfiehlt es sich, den E-Mail-Fluss zwischen dem lokalen Exchange und Exchange Online gründlich zu testen, wenn Sie die Standarddomäne ändern.

## <a name="sending-feedback"></a>Senden von Feedback

Wir freuen uns über Ihr Feedback zu:

  - Benutzerfreundlichkeit oder Benutzerfreundlichkeit
  - Featurelücken oder fehlende Funktionalität
  - Fehler oder Probleme
  
Um Feedback zu  senden, klicken Sie unten in der linken Navigationsleiste von Teams auf die Schaltfläche "Hilfe" und dann auf "Problem **für** **ALLE Probleme** melden". Bitte beachten Sie am Anfang Ihres Feedbackberichts, dass Sie Feedback zu "Bookings" senden, damit wir Probleme bei Bookings problemlos erkennen können.

## <a name="related-topics"></a>Verwandte Themen

[Dokumentation zu Bookings für Endbenutzer](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
