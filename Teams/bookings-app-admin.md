---
title: Virtuelle Visiten und Termine mit Microsoft Teams und der Bookings-App
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
description: Microsoft Teams und virtuelle Visiten und Termine mit der Bookings-App
ms.openlocfilehash: 9d2c2fe9fd1852d030d512d95bf5c944b8b1e1ed119b97a2bac23569cbb83f69
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295202"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Virtuelle Visiten und Termine mit Microsoft Teams und der Bookings-App

Die Bookings-App in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlichen und virtuellen Terminen, z. B. Arzttermine, Finanzberatungsgespräche, Bewerbungsgespräche, Kundensupport, Dienststunden für Bildungseinrichtungen und vieles mehr.

Die planenden Personen können mehrere Abteilungs- und Mitarbeiterkalender sowie die Kommunikation mit internen und externen Teilnehmern über eine einzige Lösung verwalten. Die virtuellen Treffen selbst werden über Microsoft Teams-Besprechungen durchgeführt, die stabile Videokonferenzfunktionen bieten.

> [!NOTE]
> Nur planende Personen müssen die Bookings-App in Microsoft Teams installiert haben. Mitarbeiter, die virtuelle Treffen durchführen oder daran teilnehmen, benötigen die App nicht. Sie können einfach über ihren Outlook- oder Microsoft Teams-Kalender oder über einen Link in der Buchungsbestätigungs-E-Mail an geplanten Treffen teilnehmen.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Voraussetzungen für die Verwendung der Bookings-App in Microsoft Teams

- Das Exchange-Postfach muss sich in Exchange Online befinden. Lokale Exchange Server-Postfächer werden nicht unterstützt.

- Microsoft Bookings muss für die Organisation aktiviert sein.

- Die Benutzer müssen über eine entsprechende Lizenz verfügen. Office 365 A3, A5, E3 und E5 sowie Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3 und E5 werden unterstützt.

- Alle Benutzer der Bookings-App und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Planung von Microsoft Teams-Besprechungen unterstützt.

- Ihre Systeme müssen alle [Software- und Browservoraussetzungen](hardware-requirements-for-the-teams-app.md) erfüllen.

## <a name="availability-of-bookings-in-teams"></a>Verfügbarkeit von Bookings in Microsoft Teams

Die Microsoft Bookings-App für Microsoft Teams steht auf Desktops und im Web zur Verfügung. Sie finden sie unter [Apps in Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **Apps verwalten** im Microsoft Teams Admin Center.

### <a name="control-access-to-bookings-within-your-organization"></a>Steuern des Zugriffs auf die Bookings-App innerhalb Ihrer Organisation

Es gibt mehrere Möglichkeiten, um zu steuern, wer Zugriff auf die Bookings-App und auf bestimmte Features der App hat. Informationen zum Aktivieren oder Deaktivieren von Microsoft Bookings im Microsoft 365 Admin Center sowie zum Erstellen einer Bookings-App-Richtlinie, die es ausgewählten Benutzern ermöglicht, Bookings-Kalender zu erstellen, finden Sie unter [Zugreifen auf Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Erfahren Sie außerdem, wie Sie eine [Microsoft Teams-App-Richtlinie erstellen können, um die Bookings-App für bestimmte Benutzer anzuheften](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Empfohlene Einstellungen für Besprechungsrichtlinien

Um eine optimale Nutzung der Bookings-App zu ermöglichen, erstellen Sie eine Mitarbeiter-Besprechungsrichtlinie für die automatische Zulassung von **Jedem in Ihrer Organisation**. Dadurch können Mitarbeiter automatisch am Termin teilnehmen, und für externe Teilnehmer wird der Wartebereich aktiviert. Erfahren Sie mehr darüber, wie [Personen automatisch zu Besprechungen zugelassen werden können](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Optionale Einstellung für Genehmigungen durch Mitarbeiter

Zum zusätzlichen Schutz der Privatsphäre können Sie festlegen, dass sich Mitarbeiter damit einverstanden erklären müssen, bevor Informationen zu ihrer Verfügbarkeit über die Bookings-App freigegeben werden und bevor sie für einen Termin gebucht werden können.  

Um diese Einstellung zu aktivieren, wechseln Sie zu **Microsoft 365 Admin Center** \> **Einstellungen** \> **Einstellungen**, und klicken Sie dann auf **Bookings**.

Wenn diese Einstellung aktiviert ist, erhalten die Mitarbeiter eine E-Mail, in der sie aufgefordert werden, ihre Einbindung in einen Booking-Kalender zu gestatten.  

Dieses Feature wird weltweit schrittweise für Microsoft 365- und Office 365-Kunden eingeführt. Falls noch nicht alle Optionen in Ihrer Umgebung verfügbar sind, werden sie das in Kürze sein.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Ändern der Standarddomäne beim Einrichten von Bookings-Postfächern

Beim Einrichten eines Bookings-Postfachs wird die standardmäßige E-Mail-Domäne Ihrer Microsoft 365- oder Office 365-Organisation verwendet. Dies kann jedoch zu Problemen beim Senden von Besprechungseinladungen an externe Empfänger führen. Ihre Einladung könnte als Spam gekennzeichnet und in den Junk-E-Mail-Ordner des Empfängers verschoben werden, sodass dieser Ihre Einladung möglicherweise nie sehen wird.

Es wird empfohlen, die Standarddomäne vor dem Erstellen Ihres Bookings-Postfachs zu ändern. Informationen dazu finden Sie unter [Häufig gestellte Fragen zu Domänen](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Wenn Sie die Standarddomäne ändern müssen, nachdem Ihr Bookings-Postfach erstellt wurde, können Sie dies mit PowerShell tun:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Weitere Informationen finden Sie in der PowerShell-Dokumentation zum Cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Falls Sie eine Exchange-Hybridkonfiguration verwenden, empfiehlt es sich, den E-Mail-Fluss zwischen dem lokalen Exchange und Exchange Online sorgfältig zu testen, wenn Sie die Standarddomäne ändern.

## <a name="sending-feedback"></a>Senden von Feedback

Wir freuen uns über Ihr Feedback zu:

  - Benutzererfahrung oder Anwenderfreundlichkeit
  - Lücken bei Features oder fehlende Funktionen
  - Fehler oder Probleme
  
Klicken Sie zum Senden von Feedback unten auf der linken Navigationsleiste von Microsoft Teams auf die Schaltfläche **Hilfe** und dann auf **Problem melden** für **ALLE** Probleme. Geben Sie bitte am Anfang Ihrer Feedbacknachricht an, dass Sie Feedback zu "Bookings" senden, damit wir Bookings-Probleme einfach ermitteln können.

## <a name="related-topics"></a>Verwandte Themen


  [Bookings-Dokumentation für Endbenutzer](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)