---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es baut auf Windows PowerShell auf und enthält einen umfassenden Satz von Verwaltungs- und Verwaltungs-Cmdlets, die speziell für Skype- und ältere Lync -Serverprodukte geeignet sind.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816535"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es baut auf Windows PowerShell auf und enthält einen umfassenden Satz von Verwaltungs- und Verwaltungs-Cmdlets, die speziell für Skype- und ältere Lync -Serverprodukte geeignet sind.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde Ende 2006 als herunterladbare Version für das Betriebssystem Windows eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Sie wurde in die meisten Microsoft Server-Produkte integriert, einschließlich Lync- und Skype-Servern, die mit Lync Server 2010 beginnen. In der Skype for Business Server-Verwaltungsshell sind über 700 Lync- und Skype-spezifische Cmdlets verfügbar.
  
> [!NOTE]
> Die Referenz zum Skype for Business-Cmdlet wurde zu docs.microsoft.com. Wenn Sie auf die folgenden Links klicken, gelangen Sie zur neuen docs.microsoft.com Seite. Der Inhalt ist nun open sourced und für Communitybeiträge über GitHub verfügbar. Möchten Sie mitwirken? Sehen Sie sich die README im Repository hier an: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server ist mit mehr als 700 Cmdlets erhältlich, mit denen Administratoren Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell verwalten können. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl wie den folgenden eingeben:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Mit dem vorstehenden Befehl wird die vollständige Hilfe abgerufen, die für das **Cmdlet "New-CsVoicePolicy"** verfügbar ist. Zum Anzeigen der Hilfe für ein anderes Cmdlet ersetzen Sie **"New-CsVoicePolicy"** durch den Namen des Cmdlets, für das Sie Hilfe abrufen möchten.
  
Geben Sie an der Shell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der cmdlets abzurufen, die für die Verwaltung von Skype for Business Server verfügbar sind: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informationen zu Windows PowerShell in Skype for Business Server:
  
- Öffnen Sie zum Ausführen der Skype for Business Server-Cmdlets die Skype for Business Server-Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie ein fenster Windows PowerShell anstatt der Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype-Cmdlets möglicherweise nicht ausführen. Um Skype for Business Server-Cmdlets in Windows PowerShell auszuführen, geben Sie zuerst an der Eingabeaufforderung Windows PowerShell ein: >  `Import-Module SkypeforBusiness`
  
- Skype for Business Server Management Shell wird automatisch auf jedem Skype for Business Server Enterprise Edition-Front-End-Server oder Standard Edition-Server installiert.
    
- Sie können die Hilfeinhalte der Skype for Business Server-Verwaltungsshell aktualisieren, indem Sie das [Cmdlet "Update-Help"](https://technet.microsoft.com/library/hh849720.aspx) ausführen. Das Update-Help-Cmdlet lädt die neuesten Hilfedateien herunter, die für alle auf Ihrem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business-Cmdlets.
    
    Standardmäßig aktualisiert das **Update-Help-Cmdlet** alle Module, die auf Ihrem Skype for Business Server installiert sind. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Parameter _"Module"_ verwenden, um den Bereich des Cmdlets zu beschränken. Im folgenden Beispiel wird nur das Skype for Business-Modul aktualisiert.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das Cmdlet ["Save-Help"](https://technet.microsoft.com/library/hh849724.aspx) verwenden, um die neueste Version der Hilfe zu erhalten und sie an einem von Ihnen angegebenen Speicherort zu speichern. Anschließend können Sie das **Cmdlet "Update-Help"** mit dem Parameter _"-SourcePath"_ auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe von dem ausgewählten Speicherort zu erhalten. Das folgende Beispiel zeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business-Modul aus der Dateifreigabe aktualisieren.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Ausführlichere Informationen finden Sie in [der Hilfe zum Thema "Updatable".](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > Wenn Sie PowerShell remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen. Weitere Informationen zu den Von PowerShell Remoting verwendeten Ports finden Sie unter [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

