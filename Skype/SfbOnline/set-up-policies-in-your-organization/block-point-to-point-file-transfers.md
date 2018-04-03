---
title: Point-Block dateiübertragungen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: In Skype für Business Online haben Sie die Kontrolle über dateiübertragungen Point (P2P) als Teil des vorhandenen konferenzrichtlinieneinstellungen aufgeführt. Jedoch auf diese Weise können oder Blöcke Datei überträgt für Benutzer, unabhängig davon, ob sie Dateien an Benutzer, die innerhalb derselben Organisation sind oder an ein Verbundbenutzer aus einer anderen Organisation übertragen werden. Die folgenden Schritte ausführen, können Sie P2P dateiübertragungen mit verbundorganisationen oder Partnern blockieren.
ms.openlocfilehash: 8e3fd112d46a88752b0d6d19cf2e1fbb1787df32
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="block-point-to-point-file-transfers"></a>Point-Block dateiübertragungen

In Skype für Business Online haben Sie die Kontrolle über dateiübertragungen Point (P2P) als Teil des vorhandenen konferenzrichtlinieneinstellungen aufgeführt. Jedoch auf diese Weise können oder Blöcke Datei überträgt für Benutzer, unabhängig davon, ob sie Dateien an Benutzer, die innerhalb derselben Organisation sind oder an ein Verbundbenutzer aus einer anderen Organisation übertragen werden. Die folgenden Schritte ausführen, können Sie P2P dateiübertragungen mit verbundorganisationen oder Partnern blockieren.
  
 Ein sehr häufiges Szenario ist, wenn Sie interne Benutzern, Dateiübertragung Verwendung P2P jedoch blockieren Dateiübertragung mit Verbundpartnern zulassen möchten. Für dieses Szenario müssen Sie ausführen:
  
- Zuweisen einer konferenzrichtlinie mit P2P-Dateiübertragung aktiviert (_EnableP2PFileTransfer_ auf _True_festgelegt) für Benutzer in Ihrer Organisation.
    
- Erstellen einer globalen externen Kommunikation Benutzerrichtlinie blockieren externe P2P-dateiübertragungen (_EnableP2PFileTransfer_ Festlegung auf _"false"_), und weisen Sie es zu einem Benutzer in Ihrer Organisation festgelegt. 
    
Sie können erfahren Sie mehr über diese Einstellungen [hier](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Wenn ein Verbundbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer senden, in dem die Richtlinie angewendet wurde, erhalten sie einen **Transfer** -Fehler. Und wenn ein Benutzer versucht, eine Datei senden, erhalten sie eine Fehlermeldung **Dateiübertragung ist deaktiviert** .
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version von einer 2016 Klick-und-Los Skype-Geschäfts-app verwenden, die sie unterstützt. Die folgenden Mindestversion von Skype für Business 2016 Klick-und-Los-Client ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|Erste Version für aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Aktueller Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Zurückgestellte DDE-Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Skype für apps für Windows Business oder Macintosh-Clients verwenden weiterhin werden können Dateien übertragen. 
  
## <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie _Get-Host_ im **Windows PowerShell** -Fenster eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
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

  Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deaktivieren von dateiübertragungen für Ihre Organisation P2P

_EnableP2PFileTransfer_ ist standardmäßig auf globale Richtlinie für die Organisation aktiviert. Wenn es erstellt wurde, wurden die Benutzer die _BposSAllModality_ Richtlinie zugewiesen.
  
Wenn P2P Übertragungen für innerhalb Ihrer Organisation jedoch blockieren externe dateiübertragungen an eine andere Organisation ermöglichen möchten, müssen Sie nur auf globaler Ebene zu ändern. Führen Sie dazu Folgendes aus:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deaktivieren von dateiübertragungen für einen Benutzer P2P

Sie können dies zu einem Benutzer anwenden, indem eine neue Richtlinie erstellen und diesen Benutzer erteilen. Führen Sie dazu Folgendes aus: 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 