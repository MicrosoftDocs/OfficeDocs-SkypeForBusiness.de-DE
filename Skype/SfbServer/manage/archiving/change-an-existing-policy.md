---
title: Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Richtlinien für die Benutzer Archivierung für Skype for Business Server ändern.'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818987"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Ändern einer vorhandenen Archivierungsrichtlinie in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Richtlinien für die Benutzer Archivierung für Skype for Business Server ändern.
  
Bei der ersten Bereitstellung von Skype for Business Server richten Sie anfängliche Archivierungsrichtlinien ein, die bestimmen, wie die Archivierung für die Benutzer in Ihrer Bereitstellung implementiert wird. In diesem Thema wird beschrieben, wie Richtlinien verwaltet und bearbeitet werden. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Bearbeiten von Archivierungsrichtlinien über die Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Führen Sie in der Liste der Richtlinie einen der folgenden Schritte aus: 
    
   - Um die Richtlinie für Ihre gesamte Bereitstellung zu ändern, klicken Sie in der Liste der Richtlinien auf **Global**, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
    
   - Um die Richtlinie für einen einzelnen Standort zu ändern, klicken Sie in der Liste der Richtlinien auf den Standortnamen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
   - Um die Richtlinie für einen einzelnen Benutzer oder eine Benutzergruppe zu ändern, klicken Sie in der Liste der Richtlinien auf den Benutzer- oder Gruppennamen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
5. Führen Sie auf der Seite **Bearbeiten der Archivierungsrichtlinien** die folgenden Aktionen aus:
    
   - Markieren Sie das Kontrollkästchen **Interne Kommunikation archivieren** oder entfernen Sie die Markierung, um die interne Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.
    
   - Markieren Sie das Kontrollkästchen **Externe Kommunikation archivieren** oder entfernen Sie die Markierung, um die externe Archivierung für die Richtlinie zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Bearbeiten von Archivierungsrichtlinien mit Windows PowerShell

Archivierungsrichtlinien können auch mit dem Windows PowerShell-Cmdlet **Set-CsArchivingPolicy** bearbeitet werden.
  
### <a name="enable-archiving-policies"></a>Archivierungsrichtlinien aktivieren

Setzen Sie den Wert des Parameters „ArchiveInternal“ auf „True ($True)“, um die Archivierung von internen Kommunikationssitzungen zu aktivieren. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Setzen Sie den Wert des Parameters „ArchiveExternal“ auf „True ($True)“, um die Archivierung von externen Kommunikationssitzungen zu aktivieren. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Um die Archivierung sowohl interner als auch externer Kommunikationssitzungen zu ermöglichen, setzen Sie den Wert für die ArchiveInternal-und ArchiveExternal-Parameter auf true: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Archivierungsrichtlinien deaktivieren

Setzen Sie die Werte der Parameter für „ArchiveInternal“ und „ArchiveExternal“ auf „False ($False)“, um die Archivierung vollständig zu deaktivieren. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
