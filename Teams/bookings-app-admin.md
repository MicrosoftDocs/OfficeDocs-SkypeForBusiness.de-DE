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
ms.openlocfilehash: 2bbc671b1054cfa4340abf7656e17939d147dea2
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288343"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Verwalten der Bookings-App in Microsoft Teams

Die Bookings-App in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlichen und virtuellen Terminen, z. B. Arzttermine, Finanzberatungsgespräche, Bewerbungsgespräche, Kundensupport, Dienststunden für Bildungseinrichtungen und vieles mehr. Weitere Informationen finden Sie unter [Virtuelle Besuche mit Teams und der Bookings-App](expand-teams-across-your-org/bookings-virtual-visits.md).

Die planenden Personen können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Lösung verwalten. Die virtuellen Termine selbst werden über Microsoft Teams-Besprechungen abgehalten, die stabile Videokonferenzfunktionen bieten.

> [!NOTE]
> Nur planende Personen müssen die Bookings-App in Microsoft Teams installiert haben. Mitarbeiter, die virtuelle Termine durchführen oder daran teilnehmen, benötigen die App nicht. Sie können einfach über ihren eigenen Kalender oder Outlook über Teams Oder über den Link Teams Besprechung in der Buchungsbestätigungs-E-Mail teilnehmen.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der Bookings-App in Microsoft Teams

- Das Exchange-Postfach muss sich in Exchange Online befinden. Lokale Exchange Server Postfächer werden nicht unterstützt.

- Microsoft Bookings muss für die Organisation aktiviert sein.

- Die Benutzer müssen über eine entsprechende Lizenz verfügen. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 und Business Standard werden unterstützt.

- Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die Teams unterstützt.

- Ihre Systeme müssen alle [Software- und Browservoraussetzungen](hardware-requirements-for-the-teams-app.md) erfüllen.

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Bookings in Microsoft Teams

Die Microsoft Bookings-Teams ist auf dem Desktop und im Web verfügbar. Sie finden sie unter [Apps in Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **Apps verwalten** im Teams Admin Center.

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf die Bookings-App innerhalb Ihrer Organisation

Es gibt mehrere Möglichkeiten, um zu steuern, wer Zugriff auf die Bookings-App und auf bestimmte Features der App hat.

Informationen zum Aktivieren oder Deaktivieren von Microsoft Bookings im Microsoft 365 Admin Center und zum Erstellen einer Bookings-App-Richtlinie, die ausgewählten Benutzern das Erstellen von Bookings-Kalendern erlaubt, finden Sie unter Zugriff auf [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) erhalten.

Sie können auch [eine Richtlinie für die Teams Ihrer App erstellen, um die Bookings-App für ausgewählte Benutzer anheften](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Besprechungsrichtlinieneinstellungen

Um eine optimale Benutzererfahrung für Bookings zu ermöglichen, erstellen Sie eine Teams-Besprechungsrichtlinie, damit jeder **in** Ihrer Organisation automatisch zugibt, und weisen Sie die Richtlinie Ihren Mitarbeitern zu. Auf diese Weise können Mitarbeiter dem Termin automatisch beitreten und die Lobbyerfahrung für externe Teilnehmer aktivieren. Erfahren Sie mehr darüber, wie [Sie Personen automatisch zu Besprechungen einräumen](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Optionale Einstellung für Genehmigungen durch Mitarbeiter

Zum zusätzlichen Schutz der Privatsphäre können Sie festlegen, dass sich Mitarbeiter damit einverstanden erklären müssen, bevor Informationen zu ihrer Verfügbarkeit über die Bookings-App freigegeben werden und bevor sie für einen Termin gebucht werden können.  

Um diese Einstellung zu aktivieren, wechseln Sie **zu Microsoft 365 Admin Center** \> **Einstellungen** \> **Einstellungen**, und wählen Sie dann **Bookings aus**.

Wenn diese Einstellung aktiviert ist, erhalten die Mitarbeiter eine E-Mail, in der sie aufgefordert werden, die Mitgliedschaft in einem Buchungskalender zu genehmigen.  

Dieses Feature wird weltweit schrittweise für Microsoft 365- und Office 365-Kunden eingeführt. Wenn in Ihrer Umgebung noch nicht alle Optionen verfügbar sind, schauen Sie bald wieder nach.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Ändern der Standarddomäne beim Einrichten von Bookings-Postfächern

Beim Einrichten eines Bookings-Postfachs wird die standardmäßige E-Mail-Domäne Ihrer Microsoft 365- oder Office 365-Organisation verwendet. Dies kann jedoch zu Problemen beim Senden von Besprechungseinladungen an externe Empfänger führen. Ihre Einladung könnte als Spam gekennzeichnet und in den Junk-E-Mail-Ordner des Empfängers verschoben werden, sodass dieser Ihre Einladung möglicherweise nie sehen wird.

Es wird empfohlen, die Standarddomäne zu ändern, bevor Sie Ihr Bookings-Postfach erstellen. Informationen dazu finden Sie unter [Häufig gestellte Fragen zu Domänen](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Wenn Sie die Standarddomäne ändern müssen, nachdem Ihr Bookings-Postfach erstellt wurde, können Sie dies mit PowerShell tun:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation zum Cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Wenn Sie eine Exchange-Hybridkonfiguration verwenden, empfehlen wir, den E-Mail-Fluss zwischen lokalen Exchange und Exchange Online beim Ändern der Standarddomäne gründlich zu testen.

## <a name="sending-feedback"></a>Senden von Feedback

Wir freuen uns über Ihr Feedback zu:

  - Benutzererfahrung oder Anwenderfreundlichkeit
  - Lücken bei Features oder fehlende Funktionen
  - Fehler oder Probleme
  
Um Feedback zu senden, wählen  Sie die Schaltfläche Hilfe am unteren Rand der linken Teams und dann Problem **für** **ALLE Probleme** melden aus. Geben Sie am Anfang Ihres Feedbackberichts an, dass Sie Feedback zu "Bookings" senden, damit wir Bookings-Probleme problemlos erkennen können.

## <a name="related-articles"></a>Verwandte Artikel

[Verwalten der Teilnahmeerfahrung für virtuelle Teams in mobilen Browsern](expand-teams-across-your-org/mobile-browser-join.md)


  [Bookings-Dokumentation für Endbenutzer](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
