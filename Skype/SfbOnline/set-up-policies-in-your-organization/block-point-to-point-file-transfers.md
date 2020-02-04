---
title: Blockieren von Punkt-zu-Punkt-Dateiübertragungen
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: In Skype for Business Online haben Sie die Möglichkeit, Punkt-zu-Punkt-Dateiübertragungen (P2P) als Teil der vorhandenen konferenzrichtlinieneinstellungen zu steuern. Auf diese Weise können jedoch Dateiübertragungen für Benutzer blockiert werden, unabhängig davon, ob Sie Dateien an einen Benutzer übertragen, der sich in derselben Organisation oder einem Verbundbenutzer aus einer anderen Organisation befindet. Führen Sie die folgenden Schritte aus, um P2P-Dateiübertragungen mit Verbundorganisationen oder-Partnern zu blockieren.
ms.openlocfilehash: 8c2cc90af2642a9094076c1569eee8b0ec4b15ff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693040"
---
# <a name="block-point-to-point-file-transfers"></a>Blockieren von Punkt-zu-Punkt-Dateiübertragungen

In Skype for Business Online haben Sie die Möglichkeit, Punkt-zu-Punkt-Dateiübertragungen (P2P) als Teil der vorhandenen konferenzrichtlinieneinstellungen zu steuern. Auf diese Weise können jedoch Dateiübertragungen für Benutzer blockiert werden, unabhängig davon, ob Sie Dateien an einen Benutzer übertragen, der sich in derselben Organisation oder einem Verbundbenutzer aus einer anderen Organisation befindet. Führen Sie die folgenden Schritte aus, um P2P-Dateiübertragungen mit Verbundorganisationen oder-Partnern zu blockieren.
  
 Ein sehr häufiges Szenario ist, wenn Sie internen Benutzern die Verwendung der P2P-Dateiübertragung gestatten, aber die Dateiübertragung mit Verbundpartnern blockieren möchten. Für dieses Szenario müssten Sie Folgendes tun:
  
- Weisen Sie den Benutzern in Ihrer Organisation eine konferenzrichtlinie mit aktivierter P2P-Dateiübertragung (_EnableP2PFileTransfer_ festgelegt auf " _true_") zu.
    
- Erstellen Sie eine globale Richtlinie für externe Benutzerkommunikation, um externe P2P-Dateiübertragungen zu blockieren (_EnableP2PFileTransfer_ auf " _false_" festgelegt), und weisen Sie Sie einem Benutzer in Ihrer Organisation zu. 
    
Weitere Informationen zu diesen Einstellungen finden Sie [hier](https://technet.microsoft.com/library/mt228132.aspx).
  
Wenn ein Verbundbenutzer außerhalb Ihrer Organisation versucht, eine Datei an einen Benutzer zu senden, auf den die Richtlinie angewendet wurde, wird der Fehler " **Übertragung fehlgeschlagen** " angezeigt. Und wenn ein Benutzer versucht, eine Datei zu senden, wird der Fehler " **Dateiübertragung ist deaktiviert** " angezeigt.
  
Damit dies funktioniert, muss der Benutzer eine unterstützte Version einer 2016-Klick-und-Los-Skype for Business-App verwenden, die ihn unterstützt. Die folgende Mindestversion von Skype for Business 2016 Klick-und-Los-Client ist erforderlich:
  
|**Typ**|**Veröffentlichungsdatum**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release für aktuellen Kanal  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571,2006)  <br/> |
|Aktueller Kanal  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571,2072)  <br/> |
|Verzögerter Kanal  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369,2118)  <br/> |
   
> [!CAUTION]
> Benutzer, die ältere Versionen von Skype for Business-Windows-Apps oder Mac-Clients verwenden, können weiterhin Dateien übertragen. 
  
## <a name="verify-and-start-windows-powershell"></a>Überprüfen und Starten von Windows PowerShell

- **Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**
    
1. Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.
    
2. Überprüfen Sie die Version, indem Sie im **Windows PowerShell** _-Fenster Get-Host_ eingeben.
    
3. Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
4. Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.
    
    Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Starten einer Windows PowerShell-Sitzung**
    
1. Vom **Start Menu** > **Windows PowerShell**.
    
2. Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:
    
    > [!NOTE]
    > Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deaktivieren von P2P-Dateiübertragungen für Ihre Organisation

Standardmäßig ist _EnableP2PFileTransfer_ in der globalen Richtlinie der Organisation aktiviert. Bei der Erstellung wurden den Benutzern die _BposSAllModality_ -Richtlinie zugewiesen.
  
Um P2P-Übertragungen innerhalb Ihrer Organisation zu ermöglichen, aber externe Dateiübertragungen an eine andere Organisation zu blockieren, müssen Sie Sie nur auf globaler Ebene ändern. Führen Sie dazu die folgenden Schritte aus:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deaktivieren von P2P-Dateiübertragungen für einen Benutzer

Sie können dies auf einen Benutzer anwenden, indem Sie eine neue Richtlinie erstellen und diesem Benutzer erteilen. Führen Sie dazu die folgenden Schritte aus: 
> 
>   ```PowerShell
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```PowerShell
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
