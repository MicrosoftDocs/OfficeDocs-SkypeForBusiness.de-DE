---
title: Skype for Business Server 2015-Verwaltungsshell
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung. Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Skype for Business Server 2015-Verwaltungsshell
 
Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung. Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile zu verwalten. Enthalten sind eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde als Release zum Herunterladen für Windows-Betriebssystems spät im 2006 eingeführt, und wurde als die Befehlszeilenschnittstelle für die Verwaltung von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft Server-Produkte, einschließlich Lync und Skype-Servern, die mit Lync Server 2010 integriert. 700 Lync und Skype bestimmte Cmdlets stehen in der Skype für Business Server-Verwaltungsshell zur Verfügung.
  
> [!NOTE]
> Skype für Business-Cmdlet-Referenz verschoben zu docs.microsoft.com. Durch Klicken auf die unten aufgeführten Links gelangen Sie zu der neuen Seite docs.microsoft.com. Der Inhalt ist jetzt open stammenden und bereit zur Community-Beiträge über GitHub. Belohnung interessiert? Checken Sie die Infodatei in der Repo hier:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype für Business Server 2015 im Lieferumfang von mehr als 700 Cmdlets, mit die Administratoren Skype für Business Server mithilfe der Skype für Business Server-Verwaltungsshell verwalten können. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, wenn Sie einen Befehl wie den folgenden eingeben:
  
```
Get-Help New-CsVoicePolicy -Full
```

Mit dem vorstehende Befehl ruft die vollständige Hilfe für das **New-CsVoicePolicy** -Cmdlet zur Verfügung. Ersetzen Sie zum Anzeigen der Hilfe für einen anderen Cmdlet **New-CsVoicePolicy** mit dem Namen des Cmdlets für die Hilfe abgerufen werden soll.
  
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
    
    Standardmäßig wird das Cmdlet **Update-Hilfe** alle Module installiert auf Ihre Skype für Business Server aktualisiert. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den _Modul_ -Parameter zum Einschränken des Bereichs des Cmdlets verwenden. Im folgende Beispiel wird nur die Skype für Business Modul aktualisiert.
    
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
    

