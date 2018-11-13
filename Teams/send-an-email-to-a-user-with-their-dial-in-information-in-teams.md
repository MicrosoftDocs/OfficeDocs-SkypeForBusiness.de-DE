---
title: Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
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
ms.openlocfilehash: 3b1cb1eb4fcf654a4ab3d3cb227416b0cf700817
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294921"
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

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**auf **Konferenz Informationen in e-Mail-Nachricht senden**.


## <a name="what-else-should-you-know-about-this-email"></a>Was sollten Sie sonst über diese E-Mails wissen?

- Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:
    
  - Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.
    
  - Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.
    
  - Wenn Sie die Konferenz-ID des Benutzers manuell zurücksetzen.
    
  - Wenn eine **Audiokonferenz** Lizenz daraus entfernt wird.
    
  - Wenn der Anbieter von Audiokonferenzen für einen Benutzer von Microsoft auf einen anderen Anbieter oder **None**geändert wird.
    
  - Wenn der Anbieter von Audiokonferenzen für einen Benutzer an Microsoft geändert wird.
    
- In der Standardeinstellung der Absender der e-Mail-Nachrichten werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen mithilfe von Windows PowerShell. Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
