---
title: E-Mails an Benutzer gesendet wird, wenn in Microsoft-Teams, deren Einstellungen ändern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, welche Informationen automatisch gesendet, Benutzern per e-Mail beim Ändern ihrer Einstellungen für einwahlkonferenzen im Microsoft-Teams. '
ms.openlocfilehash: f351f7a1107c3f52ddc2c9f60b7cd79feb31388c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890062"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-Mails an Benutzer gesendet wird, wenn in Microsoft-Teams, deren Einstellungen ändern

E-Mails werden automatisch für Benutzer, die [für die Audiokonferenz aktiviert](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) werden gesendet mithilfe von Microsoft als Anbieter von Audiokonferenzen.
  
Es gibt vier Typen von e-Mails, die an die Benutzer gesendet wird, die für Audiokonferenzen aktiviert sind, werden standardmäßig. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Audiokonferenzen in Office 365 sendet in den folgenden Fällen E-Mails an Benutzer:
  
- **Auf diese oder beim Ändern des Anbieters von Audiokonferenzen an Microsoft, wird eine Audiokonferenz-Lizenz zugewiesen.**
    
     Diese e-Mail enthält die Konferenz-ID, die Konferenz Standardrufnummer für Besprechungen, die Audiokonferenz PIN für den Benutzer und die die Skype für Business Online Besprechung Update Tool verwenden, mit dem Aktualisieren vorhandener Besprechungen für, Anweisungen und Link der Benutzer. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Microsoft als Anbieter von Audiokonferenzen zuweisen](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Sie können die [dynamische Audiokonferenzen-IDs in Ihrer Organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)einrichten. 
  
    So kann diese E-Mail aussehen:
    
     ![Skype for Business Verify License](media/audio-conferencing-user-enabled.png)
  
    Finden Sie weitere Informationen über die Lizenzierung von [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)sehen.
    
- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**
    
    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Aber diese e-Mails nicht des Benutzers Audiokonferenzen PIN enthalten. Weitere Informationen finden Sie unter [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).
  
    So kann diese E-Mail aussehen:
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](media/audio-conferencing-info-change.png)
  
- **Die PIN eines Benutzers-Audiokonferenzen wird zurückgesetzt.**
    
    Diese e-Mail enthält der Organisator Audiokonferenzen PIN, die vorhandene Konferenz-ID und die Standardrufnummer Konferenz für den Benutzer. Finden Sie unter [der Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](media/audio-conferencing-pin-has-changed.png)
  
- **Lizenz des Benutzers entfernt wird oder wenn Audiokonferenzen ändert von Microsoft in anderen Anbieter oder keiner.**
    
    Dies geschieht, wenn die **Audiokonferenz** -Lizenz eines Benutzers oder beim Ändern des Anbieters von Audiokonferenzen eines Benutzers von Microsoft an einen Drittanbieter-Audiokonferenzen oder entfernt wird, wenn den Anbieter auf **keine**festlegen. Diese e-Mail enthält die Informationen für den Benutzer mit der Skype für Business Online Besprechung Update Tool Audiokonferenzen bestimmte Informationen wie die Standard Konferenz Telefon Nummer oder Konferenz-ID entfernt und Anweisungen
    
    Weitere Informationen finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    So kann diese E-Mail aussehen:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können die E-Mail-Nachricht ändern, die automatisch an Benutzer gesendet wird. Zu den zu ändernden Optionen gehören die E-Mail-Adresse und der Anzeigename, der in der Kontaktinformation *From* enthalten ist. In der Standardeinstellung der Absender der e-Mail werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell. Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. In diesem Fall die Konferenz-ID default Conferencing Telefonnummer und wichtiger, ihre PIN-Audiokonferenzen wird nicht an den Benutzer gesendet werden. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.
  
In der Standardeinstellung e-Mails an Ihre Benutzer gesendet, aber wenn Sie zu empfangen von e-Mail für Audiokonferenzen verhindern möchten, können Sie Microsoft-Teams oder mit Windows PowerShell. 

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**. 

2. Klicken Sie am oberen Rand der Seite **Konferenz Brücken** **Bridge-Einstellungen**auf. 

3. Klicken Sie im Bereich **Bridge-Einstellungen** aktivieren oder Deaktivieren von **Benutzern Wenn Ändern ihrer Einstellungen für die Zugriffsnummer für Einwahl-e-Mails automatisch gesendet**.

4. Klicken Sie auf **Speichern**.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Verwenden von Windows PowerShell**
  
Finden Sie im [Microsoft-Teams PowerShell Verweis](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

In der Standardeinstellung der Absender der e-Mail werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen von Windows PowerShell. 

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
  
  
## <a name="related-topics"></a>Verwandte Themen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
