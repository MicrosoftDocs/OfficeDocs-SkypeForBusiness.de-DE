---
title: Email Optionen, wenn sich audiokonferenzeinstellungen ändern
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie Microsoft Teams daran hindern, E-Mails an Benutzer zu senden, wenn sich Einstellungen wie Pins oder die Standardkonferenznummer in Teams ändern. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642106"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams

Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Es kann jedoch vorkommen, dass Sie die Anzahl der E-Mails reduzieren möchten, die an Microsoft Teams-Benutzer gesendet werden. In solchen Fällen können Sie das Senden von E-Mails deaktivieren.
  
Wenn Sie das Senden von E-Mails deaktivieren, werden Audiokonferenz-E-Mails nicht an Ihre Benutzer gesendet, einschließlich E-Mails, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert sind, wenn ihre PIN zurückgesetzt wird und wenn sich die Konferenz-ID und die Standardtelefonnummer für Konferenzen ändern.
  
Hier ist ein Beispiel für die E-Mail, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:
  
![Beispiel für eine E-Mail-Nachricht für Audiokonferenzen.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere E-Mails, die an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:

  - Wenn ihnen eine **Audiokonferenzlizenz** zugewiesen ist.

  - Wenn Sie die Audiokonferenz-PIN des Benutzers manuell zurücksetzen.

  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.

  - Wenn die **Audiokonferenzlizenz** daraus entfernt wird.

  - Wenn der Audiokonferenzanbieter eines Benutzers von Microsoft zu einem anderen Anbieter oder **Keiner** geändert wird.

  - Wenn der Audiokonferenzanbieter eines Benutzers in Microsoft geändert wird.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails an Benutzer

Sie können Microsoft Teams oder Windows PowerShell verwenden, um an Benutzer gesendete E-Mails zu aktivieren oder zu deaktivieren.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Klicken Sie oben auf der Seite " **Konferenzbrücken** " auf " **Brückeneinstellungen"**.

3. Aktivieren oder deaktivieren Sie im **Einstellungsbereich "Brücke** " das **automatische Senden von E-Mails an Benutzer, wenn sich ihre Einwahleinstellungen ändern**.

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Verwenden von Windows PowerShell

Sie können auch das Microsoft Teams PowerShell-Modul verwenden und Folgendes ausführen:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
