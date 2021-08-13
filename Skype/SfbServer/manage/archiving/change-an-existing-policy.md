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
ms.openlocfilehash: 571f32a4cf5fb0bddd006719f3a9886c852df3f7196adf774f554cda216ea0a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315711"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Benutzerarchivierungsrichtlinien für Skype for Business Server ändern.
  
Wenn Sie Skype for Business Server zum ersten Mal bereitstellen, richten Sie anfängliche Archivierungsrichtlinien ein, die bestimmen, wie die Archivierung für die Benutzer in Ihrer Bereitstellung implementiert wird. In diesem Thema wird beschrieben, wie Sie Richtlinien verwalten und ändern. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Ändern von Archivierungsrichtlinien mithilfe der Systemsteuerung

1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
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
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Ändern von Archivierungsrichtlinien mithilfe von Windows PowerShell

Sie können Archivierungsrichtlinien auch mithilfe des Cmdlets Windows PowerShell **Set-CsArchivingPolicy** ändern.
  
### <a name="enable-archiving-policies"></a>Aktivieren von Archivierungsrichtlinien

Um die Archivierung interner Kommunikationssitzungen zu aktivieren, legen Sie den Wert des Parameters "ArchiveInternal" auf "True" ($True) fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Um die Archivierung externer Kommunikationssitzungen zu aktivieren, legen Sie den Wert des Parameters "ArchiveExternal" auf "True" ($True) fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Um die Archivierung von internen und externen Kommunikationssitzungen zu aktivieren, legen Sie den Wert der Parameter "ArchiveInternal" und "ArchiveExternal" auf "True" fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Deaktivieren von Archivierungsrichtlinien

Um die Archivierung vollständig zu deaktivieren, legen Sie den Wert der Parameter "ArchiveInternal" und "ArchiveExternal" auf "False" ($False) fest: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
