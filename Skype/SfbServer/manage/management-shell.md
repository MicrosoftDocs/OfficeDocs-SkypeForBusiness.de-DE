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
description: Die Skype for Business Server Management-Shell stellt die Befehlszeilenschnittstelle für die Server Verwaltung und-Verwaltung bereit. Es basiert auf Windows PowerShell und umfasst eine umfassende Reihe von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044257"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype for Business Server Management-Shell stellt die Befehlszeilenschnittstelle für die Server Verwaltung und-Verwaltung bereit. Es basiert auf Windows PowerShell und umfasst eine umfassende Reihe von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft-Serverprodukte integriert, einschließlich lync-und Skype-Servern, die mit lync Server 2010 beginnen. In der Skype for Business Server-Verwaltungsshell stehen über 700 lync-und Skype-spezifische Cmdlets zur Verfügung.
  
> [!NOTE]
> Die Skype for Business-Cmdlet-Referenz wurde zu docs.Microsoft.com verschoben. Durch Klicken auf die unten aufgeführten Links gelangen Sie zur neuen docs.Microsoft.com-Seite. Der Inhalt ist nun Open sourced und für Community-Beiträge über GitHub verfügbar. Möchten Sie einen Beitrag leisten? Lesen Sie die Readme-Datei im Repo hier:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server ist mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren Skype for Business Server mithilfe der Skype for Business Server Verwaltungsshell verwalten können. Sie können die Hilfe für ein Cmdlet direkt von der Befehlszeile aus abrufen, indem Sie einen Befehl wie den folgenden eingeben:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Der obige Befehl ruft die vollständige Hilfe ab, die für das Cmdlet **New-CsVoicePolicy** zur Verfügung steht. Wenn Sie Hilfe zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie die Hilfe abrufen möchten.
  
Geben Sie an der Shell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der für die Verwaltung von Skype for Business Server verfügbaren Cmdlets abzurufen: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Wissenswerte über Windows PowerShell in Skype for Business Server:
  
- Öffnen Sie zum Ausführen der Skype for Business Server-Cmdlets die Skype for Business Server-Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie ein Windows PowerShell Fenster anstelle der Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype-Cmdlets möglicherweise nicht ausführen. Wenn Sie Skype for Business Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein: >`Import-Module SkypeforBusiness`
  
- Skype for Business Server Verwaltungsshell wird automatisch auf allen Skype for Business Server Enterprise Edition-Front-End-Server oder-Standard Edition-Server installiert.
    
- Sie können die Hilfeinhalte für die Skype for Business Server Verwaltungsshell aktualisieren, indem Sie das Cmdlet [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) ausführen. Mit dem Cmdlet Update-Help werden die neuesten Hilfedateien heruntergeladen und installiert, die für alle auf Ihrem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business-Cmdlets.
    
    Standardmäßig aktualisiert das Cmdlet **Update-Help** alle Module, die auf Ihrem Skype for Business Server installiert sind. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Bereich des Cmdlets mit dem Parameter _Module_ einschränken. Im folgenden Beispiel wird nur das Skype for Business Modul aktualisiert.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das [Save-Help-](https://technet.microsoft.com/library/hh849724.aspx) Cmdlet verwenden, um die neueste Version der Hilfe abzurufen und an einem von Ihnen angegebenen Speicherort zu speichern. Anschließend können Sie das Cmdlet **Update-Help** mit dem Parameter _-SourcePath_ auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe von dem ausgewählten Speicherort abzurufen. Im folgenden Beispiel wird gezeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business Modul aus der Dateifreigabe aktualisieren.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Ausführlichere Informationen finden Sie unter Informationen [zur aktualisierbaren Hilfe](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Wenn Sie PowerShell Remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen. Weitere Informationen zu den von PowerShell-Remoting verwendeten Ports finden Sie unter [welchen Port verwendet PowerShell-Remoting?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

