---
title: E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Hier erfahren Sie, welche Informationen automatisch per E-Mail an Benutzer gesendet werden, wenn sich ihre Dial-in-Konferenzeinstellungen in Microsoft Teams ändern. '
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016165"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails, die an Benutzer gesendet werden, wenn sich ihre Einstellungen in Microsoft Teams ändern

E-Mails werden automatisch an Benutzer gesendet, die [für Audiokonferenzen aktiviert](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) sind und Microsoft als Audiokonferenzanbieter verwenden.
  
Es gibt vier Typen von e-Mails, die an die Benutzer gesendet wird, die für Audiokonferenzen aktiviert sind, werden standardmäßig. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Office 365 sendet in den folgenden Fällen E-Mails an Benutzer:
  
- **Den Benutzern wird eine Lizenz für Audiokonferenzen zugewiesen, oder Sie ändern den Audiokonferenzanbieter in Microsoft.**
    
     Diese e-Mail enthält die Konferenz-ID, die Konferenz Standardrufnummer für Besprechungen, die Audiokonferenz PIN für den Benutzer und die die Skype für Business Online Besprechung Update Tool verwenden, mit dem Aktualisieren vorhandener Besprechungen für, Anweisungen und Link der Benutzer. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Microsoft als Anbieter von Audiokonferenzen zuweisen](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)einrichten. 
  
    Hier ist ein Beispiel für diese E-Mail:
    
     ![Bestätigung der Skype for Business-Lizenz](media/audio-conferencing-user-enabled.png)
  
    Weitere Informationen zur Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **Die Konferenzkennung oder die standardmäßige Konferenztelefonnummer eines Benutzers wird geändert.**
    
    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Aber diese e-Mails nicht des Benutzers Audiokonferenzen PIN enthalten. Weitere Informationen finden Sie unter [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).
  
    Hier ist ein Beispiel für diese E-Mail:
    
     ![Die Dial-in-Konferenzinformationen wurden geändert.](media/audio-conferencing-info-change.png)
  
- **Die Audiokonferenz-PIN eines Benutzers wird zurückgesetzt.**
    
    Diese e-Mail enthält der Organisator Audiokonferenzen PIN, die vorhandene Konferenz-ID und die Standardrufnummer Konferenz für den Benutzer. Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    Hier ist ein Beispiel für diese E-Mail:
    
     ![Die PIN für Dial-in-Konferenzen wurde geändert.](media/audio-conferencing-pin-has-changed.png)
  
- **Die Lizenz eines Benutzers wird entfernt, oder der Audiokonferenzanbieter wird von Microsoft in einen anderen Anbieter oder in „Keiner“ geändert.**
    
    Dies geschieht, wenn die **Audiokonferenz** -Lizenz eines Benutzers oder beim Ändern des Anbieters von Audiokonferenzen eines Benutzers von Microsoft an einen Drittanbieter-Audiokonferenzen oder entfernt wird, wenn den Anbieter auf **keine**festlegen. Diese e-Mail enthält die Informationen für den Benutzer mit der Skype für Business Online Besprechung Update Tool Audiokonferenzen bestimmte Informationen wie die Standard Konferenz Telefon Nummer oder Konferenz-ID entfernt und Anweisungen
    
    Siehe [Zuweisen von Lizenzen zu Benutzern in Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Hier ist ein Beispiel für diese E-Mail:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Vornehmen von Änderungen an den gesendeten E-Mails

Sie können die E-Mail-Nachricht ändern, die automatisch an Benutzer gesendet wird. Zu den zu ändernden Optionen gehören die E-Mail-Adresse und der Anzeigename, der in der Kontaktinformation *From* enthalten ist. In der Standardeinstellung der Absender der e-Mail werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell. Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn keine E-Mails an die Benutzer gesendet werden sollen?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall die Konferenz-ID default Conferencing Telefonnummer und wichtiger, ihre PIN-Audiokonferenzen wird nicht an den Benutzer gesendet werden. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.
  
Standardmäßig werden E-Mails an die Benutzer gesendet. Wenn Sie nicht möchten, dass die Benutzer E-Mails für Audiokonferenzen erhalten, können Sie Microsoft Teams oder Windows PowerShell verwenden. 

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Senden Sie automatisch E-Mails an Benutzer, wenn sich die Einwahlkonfiguration ändert**.

4. Klicken Sie auf **Speichern**.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Standardmäßig ist Office 365 als Absender der E-Mails angegeben. Sie können jedoch die E-Mail-Adresse und den Anzeigenamen mit Windows PowerShell ändern. 

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren und Deaktivieren der bei geänderten Audiokonferenzeinstellungen gesendeten E-Mails](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
