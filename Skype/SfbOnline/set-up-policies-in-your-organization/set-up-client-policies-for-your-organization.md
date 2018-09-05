---
title: Einrichten von Clientrichtlinien für Ihre Organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
ms.openlocfilehash: 93dcef25119527bce25c1155dc7c8c05ac6fe78d
ms.sourcegitcommit: dbef8028cb7f8c6366e0fdb34f5f2e2a30d8c32a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "19500635"
---
# <a name="set-up-client-policies-for-your-organization"></a>Einrichten von Clientrichtlinien für Ihre Organisation

Mit Clientrichtlinien können Sie festlegen, welche Funktionen von Skype for Business Online Benutzern zur Verfügung gestellt werden. So können Sie beispielsweise einigen Benutzern das Recht zum Übertragen von Dateien erteilen, während Sie anderen Benutzern dieses Recht verweigern.
  
Sie können Clientrichtlinieneinstellungen bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsClientPolicy**-Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-client-policies"></a>Festlegen Ihrer Clientrichtlinien

> [!NOTE]
> Für alle Clientrichtlinieneinstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Startmenü** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. Vom **Startmenü** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deaktivieren von Emoticons und Anwesenheitsbenachrichtigungen und Verhindern der Speicherung von Chatnachrichten

- Führen Sie zum Erstellen einer neuen Richtlinie Folgendes aus:
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)-Cmdlet.
    
- Führen Sie für eine Zuweisung der erstellten neuen Richtlinie zu allen Benutzern in der Organisation Folgendes aus:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Aktivieren von klickbaren URLs oder Hyperlinks in Chatnachrichten

- Führen Sie zum Erstellen einer neuen Richtlinie Folgendes aus:
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)-Cmdlet.
    
- Führen Sie für eine Zuweisung der erstellten neuen Richtlinie zu allen Benutzern in der Organisation Folgendes aus:
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet.
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.
  
### <a name="prevent-showing-recent-contacts"></a>Verhindern der Anzeige der letzten Kontakte

- Führen Sie zum Erstellen einer neuen Richtlinie Folgendes aus:
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  Weitere Informationen finden Sie im [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx)-Cmdlet.
    
- Führen Sie für die Zuweisung der erstellten neuen Richtlinie zu Amos Marble Folgendes aus:
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  Weitere Informationen finden Sie im [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet.
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Dinge zu tun haben. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Konferenzrichtlinien für Ihre Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 