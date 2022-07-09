---
title: Verwalten der Bookings-App in Microsoft Teams
author: mkbond007
ms.author: mabond
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
description: Erfahren Sie, wie Sie die Bookings-App in Teams für Benutzer in Ihrer Organisation verwalten.
ms.openlocfilehash: 45ce6c29cd7bfbaedf53c1b75178142a925157cb
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695038"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Verwalten der Bookings-App in Microsoft Teams

Die Bookings-App in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlich und virtuellen Terminen. Beispiele: Besuche im Gesundheitswesen, Finanzberatungen, Interviews, Kundensupport und Bürozeiten für Bildungseinrichtungen. Weitere Informationen finden Sie unter [Virtuelle Termine mit Teams und der Bookings-App](expand-teams-across-your-org/bookings-virtual-visits.md).

Planer können mehrere Abteilungs- und Mitarbeiterkalender und die Kommunikation mit internen und externen Teilnehmern über eine einzige Oberfläche verwalten. Virtuelle Termine werden über Microsoft Teams-Besprechungen abgehalten, die robuste Videokonferenzfunktionen bieten.

> [!NOTE]
> Nur planende Personen müssen die Bookings-App in Microsoft Teams installiert haben. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie können einfach über ihren Outlook- oder Teams-Kalender oder über den Teams-Besprechungslink in ihrer Buchungsbestätigungs-E-Mail an Terminen teilnehmen.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der Bookings-App in Teams

* Das Exchange-Postfach befindet sich in Exchange Online. Lokale Exchange Server Postfächer werden nicht unterstützt.
* Microsoft Bookings ist für die Organisation verfügbar.
* Benutzer verfügen über eine entsprechende Lizenz. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 und Business Standard werden unterstützt.
* Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter verfügen über eine Lizenz, die die Planung von Teams-Besprechungen unterstützt.
* [Voraussetzungen für Software und Browser](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Bookings in Microsoft Teams

Microsoft Bookings App für Teams ist auf dem Desktop und im Web verfügbar. Sie finden sie unter ["Apps in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) " und unter **"Apps verwalten** " im Teams Admin Center.

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf die Bookings-App innerhalb Ihrer Organisation

Es gibt mehrere Möglichkeiten, um zu steuern, wer Zugriff auf die Bookings-App und auf bestimmte Features der App hat. Sie können Microsoft Bookings App verfügbar machen oder in Microsoft 365 Admin Center deaktivieren. Alternativ können Sie eine Bookings-App-Richtlinie erstellen, damit ausgewählte Benutzer Bookings-Kalender erstellen können. Siehe ["Zugriff auf Microsoft Bookings](/microsoft-365/bookings/get-access) erhalten".

Sie können auch [eine Teams-App-Setuprichtlinie erstellen, um die Bookings-App für ausgewählte Benutzer anzuheften](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Besprechungsrichtlinieneinstellungen

Um die beste Erfahrung für Bookings zu ermöglichen, erstellen Sie eine Teams-Besprechungsrichtlinie, um **jeden in Ihrer Organisation** automatisch zuzulassen und die Richtlinie Ihren Mitarbeitern zuzuweisen. Die Richtlinie ermöglicht es Mitarbeitern, automatisch am Termin teilzunehmen und die Wartebereichsumgebung für externe Teilnehmer zu aktivieren. Erfahren Sie [, wie Sie Personen automatisch zu Besprechungen zulassen](meeting-policies-participants-and-guests.md#automatically-admit-people).

Weitere Informationen zu Besprechungsrichtlinien finden [Sie unter Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md) und [Besprechungsrichtlinien und Besprechungsablauf in Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Optionale Einstellung für Genehmigungen durch Mitarbeiter

Sie können verlangen, dass mitarbeiter sich anmelden, bevor Bookings ihre Zeitplanverfügbarkeitsinformationen freigibt und bevor andere Personen einen Termin mit ihnen planen können.

Um diese Einstellung zu aktivieren, wechseln Sie zu **Microsoft 365 Admin Center** \> **Einstellungen** \> **, und** wählen Sie dann **Bookings** aus.

Wenn diese Einstellung aktiviert ist, erhalten Mitarbeiter eine E-Mail, in der sie aufgefordert werden, die Mitgliedschaft in einem Buchungskalender zu genehmigen.  

Dieses Feature wird weltweit schrittweise für Microsoft 365- und Office 365-Kunden eingeführt. Wenn in Ihrer Umgebung noch nicht alle Optionen verfügbar sind, schauen Sie bald wieder vorbei.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Ändern Ihrer Standarddomäne beim Einrichten des Bookings-Postfachs

Beim Einrichten eines Bookings-Postfachs wird die standardmäßige E-Mail-Domäne Ihrer Microsoft 365- oder Office 365-Organisation verwendet. Die Standarddomäne kann jedoch Probleme verursachen, wenn Besprechungseinladungen an externe Empfänger gesendet werden. Beispielsweise wird Ihre Einladung möglicherweise als Spam gekennzeichnet und in den Junk-Ordner des Empfängers verschoben, sodass die Einladung dem Empfänger möglicherweise nie angezeigt wird.

Es wird empfohlen, die Standarddomäne zu ändern, bevor Sie Ihr Bookings-Postfach erstellen. Weitere Informationen finden Sie in den [häufig gestellten Fragen zu Domänen](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Wenn Sie die Standarddomäne nach dem Erstellen Ihres Bookings-Postfachs ändern müssen, verwenden Sie PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation zum [Festlegen des Postfach-Cmdlets](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Wenn Sie eine Exchange-Hybridkonfiguration verwenden, empfehlen wir, den Nachrichtenfluss zwischen lokalem Exchange und Exchange Online beim Ändern der Standarddomäne gründlich zu testen.

## <a name="send-feedback"></a>Feedback senden

Wir freuen uns über Ihr Feedback zu:

* Benutzererfahrung oder Anwenderfreundlichkeit
* Lücken bei Features oder fehlende Funktionen
* Fehler oder Probleme
  
Um Feedback zu senden, wählen Sie unten in der linken Navigationsleiste von Teams die **Option "Hilfe**" und dann "Problem für **ALLE** Probleme **melden"** aus. Geben Sie am Anfang Ihres Feedbackberichts an, dass Sie Feedback zu "Bookings" senden, damit wir Bookings-Probleme leicht erkennen können.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten der Teilnahmeerfahrung für virtuelle Teams-Termine in Browsern](expand-teams-across-your-org/browser-join.md)


  [Bookings-Dokumentation für Endbenutzer](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
