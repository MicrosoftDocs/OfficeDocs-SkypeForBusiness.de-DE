---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungs- und Verwaltungs-Cmdlets, die spezifisch für Skype und ältere Lync-Serverprodukte sind.
ms.openlocfilehash: 1867789d18e5b0c28cb0772cb46d70c1918789de
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392487"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungs- und Verwaltungs-Cmdlets, die spezifisch für Skype und ältere Lync-Serverprodukte sind.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde ende 2006 als herunterladbare Version für das Windows Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft Server-Produkte integriert, einschließlich Lync- und Skype servern ab Lync Server 2010. In der Skype for Business Server Verwaltungsshell sind über 700 Lync- und Skype bestimmte Cmdlets verfügbar.
  
> [!NOTE]
> Skype for Business Cmdlet-Referenz wurde zu docs.microsoft.com verschoben. Wenn Sie auf die unten aufgeführten Links klicken, gelangen Sie zur neuen docs.microsoft.com Seite. Der Inhalt ist jetzt open sourced und für Community-Beiträge über GitHub verfügbar. Möchten Sie mitwirken? Sehen Sie sich die README im Repository hier an: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server werden mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren Skype for Business Server mithilfe der Skype for Business Server Verwaltungsshell verwalten können. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl wie den folgenden eingeben:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Der vorherige Befehl ruft die vollständige Hilfe ab, die für das Cmdlet **"New-CsVoicePolicy** " verfügbar ist. Um hilfe für ein anderes Cmdlet anzuzeigen, ersetzen Sie **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie Hilfe abrufen möchten.
  
Geben Sie an der Shell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der cmdlets abzurufen, die für die Verwaltung von Skype for Business Server verfügbar sind: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Wichtige Informationen zu Windows PowerShell in Skype for Business Server:
  
- Um die cmdlets Skype for Business Server auszuführen, öffnen Sie die Skype for Business Server Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie anstelle der Skype for Business Server Verwaltungsshell ein Windows PowerShell Fenster öffnen, können Sie die cmdlets Skype möglicherweise nicht ausführen. Um Skype for Business Server Cmdlets in Windows PowerShell auszuführen, geben Sie an der Eingabeaufforderung Windows PowerShell zuerst Folgendes ein: >`Import-Module SkypeforBusiness`
  
- Skype for Business Server Verwaltungsshell wird automatisch auf jedem Skype for Business Server Enterprise Edition Front-End-Server oder Standard Edition-Server installiert.
    
- Sie können den Hilfeinhalt der Skype for Business Server Verwaltungsshell aktualisieren, indem Sie das Cmdlet ["Update-Hilfe](/powershell/module/microsoft.powershell.core/update-help)" ausführen. Das Update-Help Cmdlet lädt die neuesten Hilfedateien herunter, die für alle auf Ihrem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business Cmdlets.
    
    Standardmäßig aktualisiert das Cmdlet **"Update-Hilfe**" alle module, die auf Ihrem Skype for Business Server installiert sind. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Parameter _"Module"_ verwenden, um den Umfang des Cmdlets einzuschränken. Im folgenden Beispiel wird nur das Skype for Business Modul aktualisiert.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das Cmdlet ["Save-Help](/powershell/module/microsoft.powershell.core/save-help) " verwenden, um die neueste Version der Hilfe abzurufen und an einem von Ihnen angegebenen Speicherort zu speichern. Sie können dann das Cmdlet **"Update-Help"** mit dem Parameter _"-SourcePath_ " auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe von dem ausgewählten Speicherort abzurufen. Das folgende Beispiel zeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business-Modul aus der Dateifreigabe aktualisieren.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Ausführlichere Informationen finden Sie in der [aktualisierbaren Hilfe](/powershell/module/microsoft.powershell.core/about/about_updatable_help).
    
    > [!NOTE]
    > Wenn Sie PowerShell remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen. Weitere Informationen zu den verwendeten Ports für PowerShell-Remoting finden Sie unter [Welchen Port verwendet PowerShell-Remoting?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).
