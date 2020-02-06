---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype for Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für die Serververwaltung und-Verwaltung. Es basiert auf Windows PowerShell und enthält eine umfassende Sammlung von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817554"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype for Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für die Serververwaltung und-Verwaltung. Es basiert auf Windows PowerShell und enthält eine umfassende Sammlung von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.
  
Mit Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Enthalten sind eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft-Serverprodukte integriert, darunter lync-und Skype-Server, die mit lync Server 2010 beginnen. In der Skype for Business Server-Verwaltungsshell sind über 700 lync-und Skype-spezifische Cmdlets verfügbar.
  
> [!NOTE]
> Die Skype for Business-Cmdlet-Referenz wurde in docs.Microsoft.com verschoben. Wenn Sie auf die Links unten klicken, gelangen Sie zur neuen docs.Microsoft.com-Seite. Der Inhalt wird nun über GitHub freigegeben und steht für Community-Beiträge zur Verfügung. Möchten Sie einen Beitrag leisten? Schauen Sie sich die Readme-Datei im Repo hier an:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server ist mit mehr als 700-Cmdlets ausgeliefert, die es Administratoren ermöglichen, Skype for Business Server über die Skype for Business Server-Verwaltungsshell zu verwalten. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, wenn Sie einen Befehl wie den folgenden eingeben:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab. Wenn Sie Hilfeinformationen zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.
  
Geben Sie den folgenden Befehl an der Eingabeaufforderung ein, um eine vollständige Liste der verfügbaren Cmdlets für Skype for Business Server anzuzeigen: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Wissenswertes zu Windows PowerShell in Skype for Business Server:
  
- Wenn Sie die Skype for Business Server-Cmdlets ausführen möchten, öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie ein Windows PowerShell-Fenster anstelle der Skype for Business Server-Verwaltungsshell öffnen, sind Sie möglicherweise nicht in der Lage, die Skype-Cmdlets auszuführen. Wenn Sie die Skype for Business Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie zuerst Folgendes an der Windows PowerShell-Eingabeaufforderung ein: #a0`Import-Module SkypeforBusiness`
  
- Die Skype for Business Server-Verwaltungsshell wird automatisch auf jedem Skype for Business Server Enterprise Edition-Front-End-Server oder Standard Edition-Server installiert.
    
- Sie können die Hilfeinhalte der Skype for Business Server-Verwaltungsshell aktualisieren, indem Sie das Cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) ausführen. Mit dem Cmdlet Update-Help werden die neuesten Hilfedateien heruntergeladen und installiert, die für alle auf dem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business-Cmdlets.
    
    Standardmäßig aktualisiert das Cmdlet **Update-Help** alle Module, die auf Ihrem Skype for Business-Server installiert sind. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Umfang des Cmdlets anhand des Parameters _Module_ einschränken. Im folgenden Beispiel wird nur das Skype for Business-Modul aktualisiert.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das Cmdlet [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) verwenden, um die neueste Version der Hilfe abzurufen und an einem von Ihnen angegebenen Speicherort zu speichern. Sie können dann das **Update-Help-** Cmdlet mit dem _-SourcePath-_ Parameter auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe von dem von Ihnen ausgewählten Speicherort abzurufen. Im folgenden Beispiel wird gezeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business-Modul aus der Dateifreigabe aktualisieren.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Ausführlichere Informationen finden Sie unter Informationen [zur aktualisierbaren Hilfe](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Wenn Sie PowerShell Remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen. Wenn Sie mehr über die von PowerShell-Remoting verwendeten Ports erfahren möchten, lesen Sie [welchen Port verwendet PowerShell-Remoting?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

