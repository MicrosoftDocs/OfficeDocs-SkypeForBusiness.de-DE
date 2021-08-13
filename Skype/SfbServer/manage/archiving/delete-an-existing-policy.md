---
title: Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.'
ms.openlocfilehash: bee5cb3d48c079f0c918e15c607c163f3f67aea9e1dfed92309700b1795c699d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320247"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Löschen einer vorhandenen Archivierungsrichtlinie in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Archivierungsrichtlinie für Skype for Business Server löschen.
  
Sie können eine Benutzer- oder Standortrichtlinie löschen, jedoch nicht die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, setzt Skype for Business Server die Richtlinie automatisch auf die Standardwerte zurück.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Löschen einer Richtlinie mithilfe der Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
4. Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.
    
5. Klicken Sie auf **Commit**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Löschen einer Richtlinie mithilfe von Windows PowerShell

Sie können Archivierungsrichtlinien auch mithilfe des Cmdlets **"Remove-CsArchivingPolicy"** löschen.
  
Mit dem folgenden Befehl wird beispielsweise die Richtlinie mit dem Identitätswert "site:Redmond" gelöscht. Wenn eine auf Standortebene konfigurierte Richtlinie gelöscht wird, werden Benutzer, die zuvor von der Standortrichtlinie verwaltet wurden, stattdessen automatisch von der globalen Archivierungsrichtlinie gesteuert:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf Benutzerebene angewendet werden:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Remove-CsArchivingPolicy".](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)