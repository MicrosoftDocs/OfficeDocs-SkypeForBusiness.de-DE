---
title: Verwalten der Bookings-App in Microsoft Teams
author: dmaguire
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Erfahren Sie, wie Sie die Bookings-App in Teams Benutzern in Ihrer Organisation verwalten.
ms.openlocfilehash: 692cf8500b47d903986542082c328b4a8be2237d
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050911"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Verwalten der Bookings-App in Microsoft Teams

Die Bookings-App in Microsoft Teams bietet eine einfache Möglichkeit, private und virtuelle Termine zu planen. Beispiele hierfür sind Arztbesuche, Finanzberatungen, Vorstellungsgespräche, Kundensupport und Sprechstunden für Bildungseinrichtungen. Weitere Informationen finden Sie unter [Virtuelle Besuche mit ihrem Teams und der Bookings-App](expand-teams-across-your-org/bookings-virtual-visits.md).

Planer können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Besprechung verwalten. Virtuelle Termine werden über Besprechungen Microsoft Teams, die stabile Funktionen für die Videokonferenz bieten.

> [!NOTE]
> Nur planende Personen müssen die Bookings-App in Microsoft Teams installiert haben. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie können einfach über ihren eigenen Kalender oder Outlook über Teams Oder über den Link Teams Besprechung in der Buchungsbestätigungs-E-Mail teilnehmen.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der Bookings-App in Teams

* Das Exchange befindet sich in Exchange Online. Lokale Exchange Server-Postfächer werden nicht unterstützt.
* Microsoft Bookings ist für die Organisation verfügbar.
* Die Benutzer verfügen über eine entsprechende Lizenz. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 und Business Standard werden unterstützt.
* Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter verfügen über eine Lizenz, die Teams unterstützt.
* [Software- und Browservoraussetzungen](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Bookings in Microsoft Teams

Die Microsoft Bookings-App Teams ist auf dem Desktop und im Web verfügbar. Sie finden sie unter [Apps in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **Apps verwalten** im Teams Admin Center.

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf die Bookings-App innerhalb Ihrer Organisation

Es gibt mehrere Möglichkeiten, um zu steuern, wer Zugriff auf die Bookings-App und auf bestimmte Features der App hat. Sie können die Microsoft Bookings-App verfügbar machen oder sie im Microsoft 365 Admin Center. Alternativ können Sie eine Bookings-App-Richtlinie erstellen, damit ausgewählte Benutzer Bookings-Kalender erstellen können. Weitere Informationen [finden Sie unter Zugriff auf Microsoft Bookings](/microsoft-365/bookings/get-access).

Sie können auch [eine Richtlinie zum Teams Ihrer App erstellen, um die Bookings-App für ausgewählte Benutzer anheften](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Besprechungsrichtlinieneinstellungen

Um eine optimale Benutzererfahrung für Bookings zu ermöglichen, erstellen Sie eine Teams-Besprechungsrichtlinie, damit jeder **in** Ihrer Organisation automatisch zugibt, und weisen Sie die Richtlinie Ihren Mitarbeitern zu. Mit der Richtlinie können Mitarbeiter automatisch am Termin teilnehmen und die Wartebereichserfahrung für externe Teilnehmer aktivieren. Erfahren [Sie, wie Sie Personen automatisch zu Besprechungen zugeben.](meeting-policies-participants-and-guests.md#automatically-admit-people)

## <a name="optional-staff-approvals-setting"></a>Optionale Einstellung für Genehmigungen durch Mitarbeiter

Sie können vor dem Teilen der Verfügbarkeitsinformationen für den Zeitplan durch andere Mitarbeiter die Anmeldung erforderlich machen, bevor andere Personen einen Termin mit ihnen planen können.

Um diese Einstellung zu aktivieren, wechseln Sie **zu Microsoft 365 Admin Center** \> **Einstellungen** \> **Einstellungen**, und wählen Sie dann **Bookings aus**.

Wenn diese Einstellung aktiviert ist, erhält der Mitarbeiter eine E-Mail, in der er aufgefordert wird, die Mitgliedschaft in einem Buchungskalender zu genehmigen.  

Dieses Feature wird weltweit schrittweise für Microsoft 365- und Office 365-Kunden eingeführt. Wenn in Ihrer Umgebung noch nicht alle Optionen verfügbar sind, schauen Sie bald wieder nach.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Ändern der Standarddomäne beim Einrichten eines Bookings-Postfachs

Beim Einrichten eines Bookings-Postfachs wird die standardmäßige E-Mail-Domäne Ihrer Microsoft 365- oder Office 365-Organisation verwendet. Die Standarddomäne kann jedoch Probleme verursachen, wenn Besprechungs-Einladungen an externe Empfänger gesendet werden. So wird Ihre Einladung beispielsweise möglicherweise als Spam gekennzeichnet und in den Junk-E-Mail-Ordner des Empfängers verschoben, sodass der Empfänger die Einladung möglicherweise nicht sehen kann.

Es wird empfohlen, die Standarddomäne zu ändern, bevor Sie Ihr Bookings-Postfach erstellen. Weitere Informationen finden [Sie unter Häufig gestellte Fragen (FAQ) zu Domänen](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Wenn Sie die Standarddomäne nach dem Erstellen Ihres Bookings-Postfachs ändern müssen, verwenden Sie PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation [zum Festlegen des](/powershell/module/exchange/mailboxes/set-mailbox) Postfach-Cmdlets.

> [!NOTE]
> Wenn Sie eine Exchange-Hybridkonfiguration verwenden, empfehlen wir, den E-Mail-Fluss zwischen lokalen Exchange und Exchange Online beim Ändern der Standarddomäne gründlich zu testen.

## <a name="send-feedback"></a>Feedback senden

Wir freuen uns über Ihr Feedback zu:

* Benutzererfahrung oder Anwenderfreundlichkeit
* Lücken bei Features oder fehlende Funktionen
* Fehler oder Probleme
  
Um Feedback zu senden, wählen  Sie unten auf der linken Navigationsleiste Teams die Option Hilfe aus, und wählen Sie dann Problem **für** **ALLE Probleme melden** aus. Geben Sie am Anfang Ihres Feedbackberichts an, dass Sie Feedback zu "Bookings" senden, damit wir Bookings-Probleme problemlos erkennen können.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten der Teilnahmeerfahrung für Teams virtuelle Besuche in mobilen Browsern](expand-teams-across-your-org/mobile-browser-join.md)


  [Bookings-Dokumentation für Endbenutzer](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
