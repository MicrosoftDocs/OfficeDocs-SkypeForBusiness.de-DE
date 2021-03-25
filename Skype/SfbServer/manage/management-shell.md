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
description: Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es baut auf Windows PowerShell und enthält eine umfassende Reihe von Verwaltungs- und Verwaltungs-Cmdlets, die speziell für Skype- und ältere Lync-Serverprodukte geeignet sind.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118584"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server-Verwaltungsshell
 
Die Skype for Business Server-Verwaltungsshell stellt die Befehlszeilenschnittstelle für die Serververwaltung und -verwaltung bereit. Es baut auf Windows PowerShell und enthält eine umfassende Reihe von Verwaltungs- und Verwaltungs-Cmdlets, die speziell für Skype- und ältere Lync-Serverprodukte geeignet sind.
  
Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Windows PowerShell wurde ende 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert. Es wurde in die meisten Microsoft Server-Produkte integriert, einschließlich Lync- und Skype-Server ab Lync Server 2010. In der Skype for Business Server Management Shell sind mehr als 700 Lync- und Skype-spezifische Cmdlets verfügbar.
  
> [!NOTE]
> Der Skype for Business-Cmdletverweis wurde zu docs.microsoft.com. Wenn Sie auf die folgenden Links klicken, gelangen Sie zur neuen docs.microsoft.com Seite. Der Inhalt ist nun open sourced und steht über GitHub für Communitybeiträge zur Verfügung. Möchten Sie mitwirken? Sehen Sie sich die README im Repository hier an: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server ist mit mehr als 700 Cmdlets verfügbar, mit denen Administratoren Skype for Business Server mithilfe der Skype for Business Server-Verwaltungsshell verwalten können. Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, indem Sie einen Befehl wie den folgenden eingeben:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Der vorstehende Befehl ruft die vollständige Hilfe ab, die für das **Cmdlet New-CsVoicePolicy** verfügbar ist. Wenn Sie Hilfe für ein anderes Cmdlet anzeigen möchten, ersetzen Sie **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie Hilfe abrufen möchten.
  
Um eine vollständige Liste der cmdlets abzurufen, die für die Verwaltung von Skype for Business Server verfügbar sind, geben Sie an der Shell-Eingabeaufforderung Folgendes ein: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informationen zu Windows PowerShell in Skype for Business Server:
  
- Öffnen Sie zum Ausführen der Skype for Business Server-Cmdlets die Skype for Business Server-Verwaltungsshell.
    
    > [!CAUTION]
    > Wenn Sie ein Windows PowerShell und nicht die Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype-Cmdlets möglicherweise nicht ausführen. Geben Sie zum Ausführen von Skype for Business Server-Cmdlets Windows PowerShell an der Eingabeaufforderung Windows PowerShell ein: >  `Import-Module SkypeforBusiness`
  
- Die Skype for Business Server-Verwaltungsshell wird automatisch auf jedem Skype for Business Server Enterprise Edition Front-End-Server oder Standard Edition-Server installiert.
    
- Sie können die Hilfeinhalte der Skype for Business Server-Verwaltungsshell aktualisieren, indem Sie das [Cmdlet Update-Help](/powershell/module/microsoft.powershell.core/update-help) ausführen. Das Update-Help-Cmdlet lädt die neuesten Hilfedateien herunter, die für alle auf Ihrem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business-Cmdlets.
    
    Standardmäßig aktualisiert das **Cmdlet Update-Help** alle module, die auf Ihrem Skype for Business Server installiert sind. Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den _Parameter Module_ verwenden, um den Bereich des Cmdlets zu beschränken. Im folgenden Beispiel wird nur das Skype for Business-Modul aktualisiert.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das [Cmdlet Save-Help](/powershell/module/microsoft.powershell.core/save-help) verwenden, um die neueste Version der Hilfe zu erhalten und sie an einem von Ihnen angegebenen Speicherort zu speichern. Anschließend können Sie das **Cmdlet Update-Help** mit dem _Parameter -SourcePath_ auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe vom ausgewählten Speicherort zu erhalten. Das folgende Beispiel zeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business-Modul aus der Dateifreigabe aktualisieren.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Weitere Informationen finden Sie unter [Informationen zur Updatable-Hilfe](/powershell/module/microsoft.powershell.core/about/about_updatable_help).
    
    > [!NOTE]
    > Wenn Sie PowerShell remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen. Weitere Informationen zu den Von PowerShell Remoting verwendeten Ports finden Sie unter [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).
