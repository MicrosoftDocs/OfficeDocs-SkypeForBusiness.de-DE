---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung. Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.
ms.openlocfilehash: 243ff7a684bb14f73ef9f4836ce00e8048fbb236
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884201"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung. Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile zu verwalten. Enthalten sind eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde als Release zum Herunterladen für Windows-Betriebssystems spät im 2006 eingeführt, und wurde als die Befehlszeilenschnittstelle für die Verwaltung von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft Server-Produkte, einschließlich Lync und Skype-Servern, die mit Lync Server 2010 integriert. 700 Lync und Skype bestimmte Cmdlets stehen in der Skype für Business Server-Verwaltungsshell zur Verfügung.
  
> [!NOTE]
> Skype für Business-Cmdlet-Referenz verschoben zu docs.microsoft.com. Durch Klicken auf die unten aufgeführten Links gelangen Sie zu der neuen Seite docs.microsoft.com. Der Inhalt ist jetzt open stammenden und bereit zur Community-Beiträge über GitHub. Belohnung interessiert? Checken Sie die Infodatei in der Repo hier:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype für Business Server im Lieferumfang von mehr als 700 Cmdlets, mit die Administratoren Skype für Business Server mithilfe der Skype für Business Server-Verwaltungsshell verwalten können. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, wenn Sie einen Befehl wie den folgenden eingeben:
  
```
Get-Help New-CsVoicePolicy -Full
```

Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab. Wenn Sie Hilfeinformationen zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.
  
Geben Sie den folgenden Befehl an der Eingabeaufforderung ein, um eine vollständige Liste der verfügbaren Cmdlets für Skype for Business Server anzuzeigen: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Wichtige Informationen zu Windows PowerShell in Skype für Business Server:
  
- Öffnen Sie zum Ausführen der Skype für Business Server-Cmdlets die Skype für Business Server-Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie ein Windows PowerShell-Fenster, statt die Skype für Business Server-Verwaltungsshell öffnen, werden standardmäßig Sie die Skype-Cmdlets ausführen möglicherweise nicht. Um Skype für Business Server-Cmdlets von Windows PowerShell ausgeführt werden soll, geben Sie zuerst Folgendes an der Windows PowerShell-Eingabeaufforderung: >`Import-Module SkypeforBusiness`
  
- Skype für Business Server-Verwaltungsshell wird automatisch auf jedem Skype für Business Server Enterprise Edition-Front-End-Server oder Standard Edition-Server installiert.
    
- Sie können die Skype für Business Server-Verwaltungsshell-Hilfe-Inhalten durch Ausführen des Cmdlets [Update-Hilfe](https://technet.microsoft.com/en-us/library/hh849720.aspx) aktualisieren. Das Cmdlet Update-Hilfe herunterladen und installieren die neuesten Dateien für alle Module auf Ihrem Computer, einschließlich Updates für Skype für Business-Cmdlets installiert.
    
    Standardmäßig wird das Cmdlet **Update-Hilfe** alle Module installiert auf Ihre Skype für Business Server aktualisiert. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Umfang des Cmdlets anhand des Parameters _Module_ einschränken. Im folgende Beispiel wird nur die Skype für Business Modul aktualisiert.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern, die nicht mit dem Internet verbunden sind, aktualisieren müssen, können Sie das Cmdlet [Get-Help speichern](https://technet.microsoft.com/en-us/library/hh849724.aspx) der neuesten Version der Hilfe, und speichern Sie sie an einem Speicherort, den Sie angeben. Sie können das Cmdlet **Update-Hilfe** klicken Sie dann mit dem _SourcePath -_ Parameter auf Servern, die nicht mit dem Internet verbunden verwenden, die aktualisierte Abrufen von Hilfe aus dem Speicherort, den, die Sie ausgewählt haben. Das folgende Beispiel veranschaulicht die Hilfedateien auf einer Netzwerkfreigabe speichern, und aktualisieren Sie die Hilfe für die Skype für Business Modul aus der Dateifreigabe.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Ausführlichere Informationen finden Sie unter [Aktualisierbare Info](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Wenn Sie Remote PowerShell verwenden, müssen Sie durch eine Firewall hindurch Kommunikation zu ermöglichen. Weitere Informationen zu den Ports PowerShell-Remoting verwendet, finden Sie unter [Was ist PowerShell-Remoting Portverwendung?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

