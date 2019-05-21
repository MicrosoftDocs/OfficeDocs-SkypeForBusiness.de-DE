---
title: Erstellen von benutzerdefinierten externen Zugriffsrichtlinien
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Mit Skype for Business Online können Sie zusätzliche Richtlinien für den externen Zugriff erstellen. Im Gegensatz zu Client-oder Konferenzrichtlinien, in denen Sie mehrere Kombinationen haben können, gibt es drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken können.
ms.openlocfilehash: 0ffd39559e4bc45a7d70466d48fb9ae838660af9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297806"
---
# <a name="create-custom-external-access-policies"></a>Erstellen von benutzerdefinierten externen Zugriffsrichtlinien

Mit Skype for Business Online können Sie zusätzliche Richtlinien für den externen Zugriff erstellen. Im Gegensatz zu Client-oder Konferenzrichtlinien, in denen Sie mehrere Kombinationen haben können, gibt es drei vordefinierte Richtlinien für den externen Zugriff, die die meisten Szenarien abdecken können. Diese sind:
  
- Kein Verbund-oder Skype-Consumer-Zugriff (_Tag: NoFederationAndPIC_ )
    
- Nur für den Verbundzugriff (_Tag: FederationOnly_ )
    
- Federated-und Consumer-Zugriff (_FederationAndPICDefault_)
    
Mit benutzerdefinierten externen Richtlinien können Sie zusätzliche Policen erstellen, die nicht unter die obigen Einstellungen fallen. Wenn die Richtlinie erstellt wurde, müssen Sie alle erforderlichen Parameter festlegen, die Sie später nicht mehr ändern können. Durch das Erstellen neuer benutzerdefinierter Richtlinien können Sie Features wie den Skype-Consumer-Zugriff oder eine Richtlinie zum Deaktivieren der öffentlichen Cloud-Audio/Video-Funktion steuern, was nicht mit vordefinierten Einstellungen abgedeckt wurde. Benutzerdefinierte Richtlinien für den externen Zugriff Folgen der gleichen Syntax wie Client-, Mobilitäts-und Konferenzrichtlinien. Weitere Informationen zu diesen Einstellungen finden Sie [hier](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version der 2016-Klick-und-Los-Skype for Business-App verwenden, die ihn unterstützt. Die folgende Mindestversion von Skype for Business 2016 Klick-und-Los-Client ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release für aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571,2006)  <br/> |
|Aktueller Kanal  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571,2072)  <br/> |
|Verzögerter Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369,2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die eine ältere Version von Skype for Business-Windows-Apps oder Mac-Clients verwenden, können weiterhin Dateien übertragen. 
  
## <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Erstellen einer benutzerdefinierten Richtlinie für den externen Zugriff für einen Benutzer

Führen Sie dazu die folgenden Aktionen aus:
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
