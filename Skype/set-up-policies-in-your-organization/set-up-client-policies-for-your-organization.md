---
title: "Einrichten von Clientrichtlinien für Ihre Organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern."
ms.openlocfilehash: 2d76f1037e595419caf5059a563e441c521abd81
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-client-policies-for-your-organization"></a>Einrichten von Clientrichtlinien für Ihre Organisation

Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
  
Richtlinie Clienteinstellungen auf die Uhrzeit der Erstellung eine Richtlinie konfiguriert werden können, oder kann, verwenden Sie das Cmdlet **Set-CsClientPolicy** zum Ändern der Einstellungen einer vorhandenen Richtlinie.
  
## <a name="set-your-client-policies"></a>Festlegen Ihrer Clientrichtlinien

> [!NOTE]
> Für alle Clientrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Um sicherzustellen, dass Sie Version 3.0 oder höher ausgeführt werden: **Im Menü Start** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster **Windows PowerShell** die Zeichenfolge _Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. Über das **Startmenü** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deaktivieren von Emoticons und Anwesenheitsbenachrichtigungen und Verhindern der Speicherung von Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Aktivieren von klickbaren URLs oder Hyperlinks in Chatnachrichten

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.
  
### <a name="prevent-showing-recent-contacts"></a>Verhindern der Anzeige der letzten Kontakte

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) -Cmdlet.
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) -Cmdlet.
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externe Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Datenblöcke Point-Datei übertragen](block-point-to-point-file-transfers.md)

[Einrichten von konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
