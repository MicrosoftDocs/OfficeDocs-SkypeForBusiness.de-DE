---
title: E-Mail-Optionen, wenn sich die Audiokonferenzeinstellungen ändern
ms.author: tonysmit
author: tonysmit
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
description: 'Erfahren Sie, wie Sie das Senden Skype E-Mails an Benutzer aktivieren oder deaktivieren, wenn sich Einstellungen wie Änderungen an der Pin oder die Standardkonferenznummer in ihrer Microsoft Teams. '
ms.openlocfilehash: f81572feb976ab68a6a65631ec772ec4421f2b1e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727444"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams

Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Es kann jedoch zeitenweise kommen, in denen Sie die Anzahl der E-Mails verringern möchten, die an Benutzer Microsoft Teams werden. In diesen Fällen können Sie das Senden von E-Mails deaktivieren.
  
Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails für Audiokonferenzen an die Benutzer gesendet, z. B. E-Mails dazu, wann Benutzer für Audiokonferenzen aktiviert oder deaktiviert sind, wann die PIN zurückgesetzt wird und wenn sich die Konferenz-ID und die Standardtelefonnummer für Konferenzen ändern.
  
Hier ist ein Beispiel für eine E-Mail, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:
  
![Beispiel für eine E-Mail-Nachricht für Audiokonferenzen](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere E-Mails, die nach der Aktivierung für Audiokonferenzen an Benutzer in Ihrer Organisation gesendet werden:
    
  - Wenn ihnen **eine Lizenz für Audiokonferenzen** zugewiesen wird.
    
  - Wenn Sie die PIN für Audiokonferenzen des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn die **Lizenz für Audiokonferenzen** entfernt wird.
    
  - Wenn sich der Audiokonferenzanbieter eines Benutzers von Microsoft auf einen anderen Anbieter oder Kein **ändert.**
    
  - Wenn sich der Audiokonferenzanbieter eines Benutzers in Microsoft ändert.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails an Benutzer

Sie können E-Microsoft Teams oder Windows PowerShell, um an Benutzer gesendete E-Mails zu aktivieren oder zu deaktivieren.

![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Aktivieren oder **deaktivieren Sie im Bereich** Einstellungen der Brücke die Option Automatisches Senden von E-Mails an Benutzer, wenn sich **deren Einwahleinstellungen ändern.**

4. Klicken Sie auf **Speichern**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
Sie können auch das Microsoft Teams PowerShell-Modul verwenden und ausführen:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Mit dem Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) können Sie weitere Einstellungen für Ihre Organisation (unter anderem E-Mail) verwalten.

Weitere Informationen Microsoft Teams Sie in der [PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)

    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
