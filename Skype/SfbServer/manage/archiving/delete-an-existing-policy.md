---
title: Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992362"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.
  
Benutzer- und Standortrichtlinien können gelöscht werden, die globale Richtlinie jedoch nicht. Wenn Sie die globale Richtlinie löschen, setzt Skype for Business Server die Richtlinie automatisch auf die Standardwerte zurück.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Löschen einer Richtlinie über die Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Verwalten von Archivierungsrichtlinien über Windows PowerShell

Archivierungsrichtlinien können auch mit dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden.
  
Beispielsweise dient der folgende Befehl zum Löschen der Richtlinie mit der Identität „site:Redmond“. Für Benutzer, für die zuvor die Standortrichtlinie galt, wird nach dem Löschen einer auf Standortebene konfigurierten Richtlinie stattdessen automatisch die globale Archivierungsrichtlinie angewendet:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerebene festgelegt wurden:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
