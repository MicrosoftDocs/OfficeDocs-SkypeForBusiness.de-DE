---
title: Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype für Business Server 2015 zu löschen.'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server 2015

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype für Business Server 2015 zu löschen.
  
Benutzer- und Standortrichtlinien können gelöscht werden, die globale Richtlinie jedoch nicht. Wenn Sie die globale Richtlinie löschen, setzt Skype für Business Server automatisch die Richtlinie auf die Standardwerte zurück.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Löschen einer Richtlinie über die Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Verwalten von Archivierungsrichtlinien über Windows PowerShell

Archivierungsrichtlinien können auch mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.
  
Beispielsweise dient der folgende Befehl zum Löschen der Richtlinie mit der Identität „site:Redmond“. Für Benutzer, für die zuvor die Standortrichtlinie galt, wird nach dem Löschen einer auf Standortebene konfigurierten Richtlinie stattdessen automatisch die globale Archivierungsrichtlinie angewendet:
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerebene festgelegt wurden:
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) -Cmdlet.