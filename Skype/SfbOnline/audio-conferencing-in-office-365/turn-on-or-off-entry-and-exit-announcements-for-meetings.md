---
title: "Aktivieren bzw. Deaktivieren der Ankündigung von Zu- und Abgängen für Besprechungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: ca353400d78a37a4b7cc362df6ed44a7f25fd869
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Aktivieren bzw. Deaktivieren der Ankündigung von Zu- und Abgängen für Besprechungen

Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie eine audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, mit denen Personen einen Skype für Business oder Microsoft-Teams Besprechung anrufen. 
  
Die Konferenzbrücke beantwortet einen Anruf für einen Benutzer, die in einer Besprechung mit einem Telefon einwählt. Bitten Sie die Konferenzbrücke den Anrufer mit Ansagen aus einer Live Meeting-Telefonzentrale beantwortet, und klicken Sie dann je nach Ihrer Einstellungen kann wiedergeben Benachrichtigungen, Anrufer dokumentieren Sie ihren Namen, und richten Sie die PIN-Sicherheit. Eine PIN zu einem Skype für Business oder Microsoft-Teams Besprechungsorganisator angegeben wird, und es ermöglicht es ihnen, eine Besprechung starten, wenn die Besprechung mithilfe einer Skype für Business oder Microsoft-Teams app gestartet werden kann. Sie können, jedoch festlegen, sodass eine PIN erforderlich ist, um eine Besprechung zu starten.
  
## <a name="setting-meeting-join-options"></a>Festlegen von Optionen für die Besprechungsteilnahme

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Unter **Erleben Sie die Teilnahme an einer Besprechung**de- **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**. Diese Option ist standardmäßig aktiviert. Wenn Sie ihn deaktivieren, werden nicht Benutzer, die bereits an der Besprechung benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.
    
5. Wählen Sie unter **Entry/Exit Ankündigung Typ** **Namen oder Rufnummern** oder **Töne**.
    
6. Überprüfen Sie, oder deaktivieren Sie **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen**.
    
7. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) nutzen.
    
-  In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie Einstellungen Änderungen für viele Benutzer gleichzeitig durchführen. Learn about these advantages in the following topics: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)

