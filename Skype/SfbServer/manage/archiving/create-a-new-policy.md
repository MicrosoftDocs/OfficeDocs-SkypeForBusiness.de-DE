---
title: Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992732"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.
  
Sie können neue Archivierungsrichtlinien über die Systemsteuerung oder mit Windows PowerShell-Cmdlets erstellen.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Erstellen einer neuen Archivierungsrichtlinie über die Systemsteuerung

So erstellen Sie eine neue Archivierungsrichtlinie über die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf **Neu** und führen Sie eine der folgenden Aktionen aus: 
    
   - Um eine Archivierungsrichtlinie auf Standortebene zu erstellen, klicken Sie auf **Standortrichtlinie** und anschließend unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
   - Um eine Archivierungsrichtlinie auf Benutzerebene zu erstellen, klicken Sie auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Richtlinie an (z. B. „externalContoso“).
    
   - Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Richtlinie an (z. B. Archivierungsrichtlinie für externe Benutzer von Contoso).
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der Kommunikation mit internen Benutzern zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit ausführen**.
    
    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Erstellen einer neuen Archivierungsrichtlinie mit Windows PowerShell

Sie können neue Archivierungsrichtlinien auch mit dem Windows PowerShell-Cmdlet **New-CsArchivingPolicy** erstellen. Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>So erstellen Sie eine neue Archivierungsrichtlinie auf Standortebene

Mit diesem Befehl wird eine neue Archivierungsrichtlinie für den Standort „Redmond“ erstellt:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>So erstellen Sie eine neue Archivierungsrichtlinie auf Benutzerebene

Um eine neue Archivierungsrichtlinie auf Benutzerebene zu erstellen, geben Sie beim Erstellen der Richtlinie einfach eine eindeutige ID an:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>So erstellen Sie eine neue Archivierungsrichtlinie zum Aktivieren der Archivierung interner Kommunikationssitzungen

Da in den vorhergehenden Befehlen keine Parameter (mit Ausnahme des Parameters zur obligatorischen Identität) angegeben wurden, verwenden die neuen Richtlinien die Standardwerte für alle ihre Eigenschaften. Zum Erstellen von Richtlinien, die unterschiedliche Eigenschaftswerte verwenden, fügen Sie einfach den entsprechenden Parameter-und Parameterwert hinzu. Mit dem folgenden Befehl wird beispielsweise eine Archivierungsrichtlinie erstellt, die die Archivierung interner Instant Messaging-Sitzungen ermöglicht: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>So erstellen Sie eine neue Archivierungsrichtlinie zur Archivierung interner und externer Kommunikationssitzungen

Mehrere Eigenschaftenwerte können durch Einschließen mehrerer Parameter geändert werden. Mit dem folgenden Befehl wird beispielsweise eine neue Richtlinie zum Archivieren interner und externer Chatsitzungen konfiguriert:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
