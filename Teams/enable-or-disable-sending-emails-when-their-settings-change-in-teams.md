---
title: E-Mail-Optionen, wenn sich die Einstellungen für Audiokonferenzen ändern
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Erfahren Sie, wie Sie Skype beim Senden von E-Mails an Benutzer aktivieren oder deaktivieren, wenn sich Einstellungen wie Anheften oder die Standardkonferenznummer in Microsoft Teams ändern. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092703"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails in Microsoft Teams

Benutzer werden automatisch per E-Mail benachrichtigt, wenn sie für Audiokonferenzen aktiviert sind. Es kann jedoch zu Zeiten kommen, in denen Sie die Anzahl der E-Mails verringern möchten, die an Microsoft Teams-Benutzer gesendet werden. In solchen Fällen können Sie das Senden von E-Mails deaktivieren.
  
Wenn Sie das Senden von E-Mails deaktivieren, werden Audiokonferenz-E-Mails nicht an Ihre Benutzer gesendet, einschließlich E-Mails, wenn Benutzer für Audiokonferenzen aktiviert oder deaktiviert sind, wenn ihre PIN zurückgesetzt wird und wenn sich die Konferenz-ID und die Standardtelefonnummer für Konferenzen ändern.
  
Hier ist ein Beispiel für die E-Mail, die an Benutzer gesendet wird, wenn sie für Audiokonferenzen aktiviert sind:
  
![Beispiel für eine E-Mail-Nachricht für Audiokonferenzen](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Wann werden E-Mails an Benutzer gesendet?

- Es gibt mehrere E-Mails, die an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn ihnen **eine** Lizenz für Audiokonferenzen zugewiesen ist.
    
  - Wenn Sie die PIN für Audiokonferenzen des Benutzers manuell zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn die **Lizenz für Audiokonferenzen** entfernt wird.
    
  - Wenn der Audiokonferenzanbieter eines Benutzers von Microsoft zu einem anderen Anbieter oder None **geändert wird.**
    
  - Wenn der Audiokonferenzanbieter eines Benutzers in Microsoft geändert wird.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Aktivieren oder Deaktivieren des Sendens von E-Mails an Benutzer

Sie können Microsoft Teams oder Windows PowerShell verwenden, um an Benutzer gesendete E-Mails zu aktivieren oder zu deaktivieren.

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Brückeneinstellungen.** 

3. Aktivieren oder **deaktivieren Sie im** Bereich Bridge-Einstellungen automatisch E-Mails an Benutzer senden, wenn sich deren **Einwahleinstellungen ändern.**

4. Klicken Sie auf **Speichern**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)

    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen für Audiokonferenzen ändern](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)