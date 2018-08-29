---
title: Erstellen von benutzerdefinierten externen Zugriffsrichtlinien
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype ermöglicht Ihnen die Erstellung von externen Zugriffs-Richtlinien. Nicht so wie bei Conferencing-Richtlinien, bei denen Sie mehrere Kombinationen haben können, gibt es hier drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken.
ms.openlocfilehash: e166aa9af162fd6432c8932d5842ea0fd00a36b3
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568312"
---
# <a name="create-custom-external-access-policies"></a>Erstellen von benutzerdefinierten externen Zugriffsrichtlinien

Skype ermöglicht Ihnen die Erstellung von externen Zugriffs-Richtlinien. Nicht so wie bei Conferencing-Richtlinien, bei denen Sie mehrere Kombinationen haben können, gibt es hier drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken. Diese sind:
  
- No Federated oder Skype Consumer Zugriff (_Tag: NoFederationAndPIC_)
    
- Nur Federated Zugriff (_Tag: FederationOnly_)
    
- Federated und Consumer Zugriff (_FederationAndPICDefault_)
    
Richtlinien für den benutzerdefinierten externen Zugriff ermöglichen Ihnen, zusätzliche Richtlinien zu schaffen, die von den oben genannten Einstellungen nicht abgedeckt sind. Wenn die Richtlinie erstellt wurde, werden Sie aufgefortert, alle erforderlichen Parameter einzustellen, die Sie später jedoch nicht mehr ändern können. Die Erstellung neuer benutzerdefinierter Richtlinien ermöglicht Ihnen, Funktionen wie Skype Consumer Zugriff zu steuern oder eine Richtlinie zum Deaktivieren von Audio/Video aus der öffentlichen Cloud - dies war nicht von den Voreinstellungen abgedeckt. Benutzerdefinierte externe Zugriffsrichtlinien führen derselben Syntax wie die Client-, Mobilitäts- und Conferencing-Richtlinien. Weitere Informationen zu diesen Einsellungen finden Sie [hier](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version von 2016 der App Click-to-Run für Skype for Business verwenden. Die folgende Minimalversion von Skype for Business 2016 Click-to-Run ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|Erste Freigabe für den aktuellen Kanal  <br/> |17.11.2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Aktueller Kanal  <br/> |06.12.2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Verzögerter Kanal  <br/> |22.02.2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Windows-Apps für Skype for Business verwenden oder Mac-Kunden können weiterhin Dateien übertragen. 
  
## <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. Vom **Start Menu** > **Windows PowerShell**.
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Erstellen einer benutzerdefinierten Richtlinie für den externen Zugriff eines Benutzers

Zu diesem Zweck führen Sie Folgendes aus:
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie viele Dinge zu tun haben. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also
[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Conferencing-Richtlinien für Ihre Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 