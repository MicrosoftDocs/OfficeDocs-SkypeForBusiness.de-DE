---
title: Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Senden Sie E-Mails mit Audiokonferenzinformationen an Ihre Benutzer in Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892092"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer in Microsoft Teams

Manchmal müssen Sie Microsoft Teams-Benutzern ihre Audiokonferenzinformationen senden. Dazu können Sie unter den Eigenschaften für einen Benutzer auf **Konferenzinformationen per E-Mail senden** klicken. Wenn Sie diese E-Mail senden, enthält sie alle Audiokonferenzinformationen, wie zum Beispiel:
  
- Die Konferenztelefonnummer oder Dial-in-Telefonnummer für den Benutzer
    
- Die Konferenzkennung des Benutzers
    
   
Hier ist ein Beispiel für die gesendete E-Mail:
  
![E-Mail zu einer Dial-in-Konferenz](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **Send conference info in email** (Konferenzinformationen per E-Mail senden).


## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mail wissen?

- Es gibt mehrere Situationen, in denen E-Mails an Benutzer in Ihrer Organisation gesendet werden, nachdem sie für Audiokonferenzen aktiviert wurden:
    
  - Wenn ihnen eine Lizenz für **Audiokonferenzen** zugewiesen wird
    
  - Wenn Sie die Audiokonferenz-PIN von Benutzern manuell zurücksetzen
    
  - Wenn Sie die Konferenzkennung von Benutzern manuell zurücksetzen
    
  - Wenn ihre Lizenz für **Audiokonferenzen** entfernt wird
    
  - Wenn der Audiokonferenzanbieter für Benutzer von Microsoft in einen anderen Anbieter oder in **Keiner** geändert wird
    
  - Wenn der Audiokonferenzanbieter für Benutzer in Microsoft geändert wird
    
- Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern. Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
