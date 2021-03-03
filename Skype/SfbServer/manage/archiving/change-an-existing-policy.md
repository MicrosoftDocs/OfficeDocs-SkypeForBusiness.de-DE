---
title: Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Zusammenfassung: Erfahren Sie, wie Sie Benutzerarchivierungsrichtlinien für Skype for Business Server ändern.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817705"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Benutzerarchivierungsrichtlinien für Skype for Business Server ändern.
  
Bei der ersten Bereitstellung von Skype for Business Server richten Sie anfängliche Archivierungsrichtlinien ein, die bestimmen, wie die Archivierung für die Benutzer in Ihrer Bereitstellung implementiert wird. In diesem Thema wird beschrieben, wie Richtlinien verwaltet und geändert werden. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Ändern von Archivierungsrichtlinien mithilfe der Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
4. Führen Sie in der Liste der Richtlinie einen der folgenden Schritte aus: 
    
   - Klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**, um die Richtlinie für Ihre gesamte Bereitstellung zu ändern.
    
   - Um die Richtlinie für einen einzelnen Standort zu ändern, klicken Sie in der Liste der Richtlinien auf den Standortnamen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
   - Um die Richtlinie für einen einzelnen Benutzer oder eine Benutzergruppe zu ändern, klicken Sie in der Liste der Richtlinien auf den Benutzer- oder Gruppennamen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
5. Führen Sie auf der Seite **Bearbeiten der Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die interne Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die externe Archivierung für die Bereitstellung zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit**.
    
    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Weitere Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Ändern von Archivierungsrichtlinien mithilfe Windows PowerShell

Sie können Archivierungsrichtlinien auch mit dem cmdlet Windows PowerShell **Set-CsArchivingPolicy** ändern.
  
### <a name="enable-archiving-policies"></a>Aktivieren von Archivierungsrichtlinien

Um die Archivierung interner Kommunikationssitzungen zu aktivieren, legen Sie den Wert des Parameters "ArchiveInternal" auf "True" ($True) $True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Um die Archivierung externer Kommunikationssitzungen zu aktivieren, legen Sie den Wert des Parameters "ArchiveExternal" auf "True" ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Um die Archivierung von internen und externen Kommunikationssitzungen zu aktivieren, legen Sie den Wert der Parameter "ArchiveInternal" und "ArchiveExternal" auf "True" fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Archivierungsrichtlinien deaktivieren

Wenn Sie die Archivierung vollständig deaktivieren möchten, legen Sie den Wert der Parameter "ArchiveInternal" und "ArchiveExternal" auf "False" ($False) fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
