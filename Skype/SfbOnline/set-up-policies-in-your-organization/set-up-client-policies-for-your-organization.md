---
title: Einrichten von Clientrichtlinien für Ihre Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
ms.openlocfilehash: 43b51b800b3107410c64bd2605b5a6a7622fe65a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776290"
---
# <a name="set-up-client-policies-for-your-organization"></a>Einrichten von Clientrichtlinien für Ihre Organisation

Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
  
Client Richtlinieneinstellungen können zum Zeitpunkt der Erstellung einer Richtlinie konfiguriert werden, oder Sie können das Cmdlet " **festlegen-CsClientPolicy** " verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-client-policies"></a>Festlegen Ihrer Clientrichtlinien

> [!NOTE]
> Für alle Clientrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
    1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Startmenü** > **Windows PowerShell**.
        
    2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
        
    3. Wenn Sie nicht über Version 3,0 oder höher verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
        
    4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
    1. Vom **Startmenü** > **Windows PowerShell**.
        
    2. Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:
    
        > [!NOTE]
        > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

       ```powershell
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```
Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deaktivieren von Emoticons und Anwesenheitsbenachrichtigungen und Verhindern der Speicherung von Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Weitere Informationen finden Sie unter dem Cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Weitere Informationen finden Sie im Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , um die Einstellungen auf die Benutzer anzuwenden.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Aktivieren von klickbaren URLs oder Hyperlinks in Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Weitere Informationen finden Sie unter dem Cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Weitere Informationen finden Sie im Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , um die Einstellungen auf die Benutzer anzuwenden.
  
### <a name="prevent-showing-recent-contacts"></a>Verhindern der Anzeige der letzten Kontakte

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Weitere Informationen finden Sie unter dem Cmdlet [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Weitere Informationen finden Sie im Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) , um die Einstellungen auf die Benutzer anzuwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
