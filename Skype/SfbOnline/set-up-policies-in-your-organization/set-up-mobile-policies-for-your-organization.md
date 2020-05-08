---
title: Einrichten von Richtlinien für mobile Geräte für Ihre Organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können.
ms.openlocfilehash: cfd9232943aebc9e4565b0ebfe1b46872c4bad65
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164844"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Einrichten von Richtlinien für mobile Geräte für Ihre Organisation

Sie können einrichten, wie Benutzer über die Skype for Business-App auf mobilen Geräten Verbindungen mit Skype for Business Online herstellen. Ein Beispiel hierfür wäre eine Funktion, mit der Benutzer auf ihrem Mobiltelefon Telefonanrufe tätigen und empfangen können und dazu ihre geschäftliche Rufnummer anstelle ihrer Mobiltelefonnummer verwenden können. Mit Mobilitätsrichtlinien können Sie auch festlegen, dass Anrufe nur über WLAN-Verbindungen getätigt oder empfangen werden können.
  
Richtlinieneinstellungen für mobile Geräte können Sie bei der Erstellung einer Richtlinie konfigurieren. Alternativ können Sie das **Set-CsMobilityPolicy** -Cmdlet verwenden, um die Einstellungen einer vorhandenen Richtlinie zu ändern.
  
## <a name="set-your-mobile-policies"></a>Festlegen Ihrer Richtlinien für mobile Geräte

> [!NOTE]
> Für alle Richtlinieneinstellungen für mobile Geräte in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**. 
  
### <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
        
    3. Wenn Sie nicht über Version 3,0 oder höher verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
        
    4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Wenn Sie weitere Informationen benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:
        
        > [!NOTE]
        > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Festlegen einer WLAN-Verbindung als erforderlich für Video für einen Benutzer

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Weitere Informationen finden Sie unter dem Cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Weitere Informationen finden Sie im Cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Verhindern, dass ein Benutzer die Skype for Business-App verwendet

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Weitere Informationen finden Sie unter dem Cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Weitere Informationen finden Sie im Cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) , um die Einstellung auf Ihre Benutzer anzuwenden.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Verhindern, dass ein Benutzer Voice over IP-Anrufe über ein mobiles Gerät tätigt

- Um eine neue Richtlinie für diese Einstellungen zu erstellen, führen Sie Folgendes aus:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Weitere Informationen finden Sie unter dem Cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Um die erstellte neue Richtlinie allen Benutzern in der Organisation zuzuweisen, führen Sie Folgendes aus:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Weitere Informationen finden Sie im Cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx)-Cmdlet die Einstellung auf die Benutzer anwenden.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
