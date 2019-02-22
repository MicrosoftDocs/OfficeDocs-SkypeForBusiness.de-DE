---
title: Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie die von Skype an Benutzer gesendeten E-Mails bei Änderungen an Einstellungen wie zum Beispiel PINs oder standardmäßigen Konferenztelefonnummern in Microsoft Teams aktivieren oder deaktivieren. '
ms.openlocfilehash: 7c08f0268c707a545873afe76e850a90a41087b4
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178638"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams

Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert werden. Es kann jedoch Fälle geben, in denen Sie die Anzahl der an Microsoft Teams-Benutzer gesendeten E-Mails reduzieren möchten. In diesen Fällen können Sie das Senden von E-Mails deaktivieren.
  
Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails zu Audiokonferenzen an die Benutzer gesendet. Dazu zählen auch E-Mails, die normalerweise gesendet werden, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert werden, wenn ihre PIN zurückgesetzt wird oder wenn sich die Konferenzkennung und die standardmäßige Konferenztelefonnummer ändern.
  
Hier ist ein Beispiel für eine E-Mail, die beim Aktivieren von Benutzern für Audiokonferenzen an die Benutzer gesendet wird:
  
![E-Mails zu Audiokonferenzen](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere Situationen, in denen E-Mails an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn ihnen eine Lizenz für **Audiokonferenzen** zugewiesen wird
    
  - Wenn Sie die Audiokonferenz-PIN von Benutzern manuell zurücksetzen
    
  - Wenn Sie die Konferenzkennung von Benutzern manuell zurücksetzen
    
  - Wenn ihre Lizenz für **Audiokonferenzen** entfernt wird
    
  - Wenn der Audiokonferenzanbieter für Benutzer von Microsoft in einen anderen Anbieter oder in **Keiner** geändert wird
    
  - Wenn der Audiokonferenzanbieter für Benutzer in Microsoft geändert wird


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren der an Benutzer gesendeten E-Mails

Sie können die an Benutzer gesendeten E-Mails über Microsoft Teams oder über Windows PowerShell aktivieren oder deaktivieren.

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.

4. Klicken Sie auf **Speichern**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich ihre Audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


