---
title: Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Zusammenfassung: Erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.'
ms.openlocfilehash: 7793575e75fcee4509c96cd6a569520a4a34576e850818a52dd20518ee725de2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280978"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Erstellen einer neuen Archivierungsrichtlinie in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine neue Archivierungsrichtlinie für Skype for Business Server erstellen.
  
Sie können neue Archivierungsrichtlinien mithilfe der Systemsteuerung oder mit Windows PowerShell Cmdlets erstellen.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Erstellen einer neuen Archivierungsrichtlinie mithilfe der Systemsteuerung

So erstellen Sie eine neue Archivierungsrichtlinie mithilfe der Systemsteuerung:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
4. Klicken Sie auf **Neu**, und führen Sie eine der folgenden Aktionen aus: 
    
   - Klicken Sie zum Erstellen einer Archivierungsrichtlinie auf Standortebene auf **Standortrichtlinie,** und klicken Sie dann unter **"Standort auswählen"** auf den Standort, auf den die Richtlinie angewendet werden soll.
    
   - Um eine Archivierungsrichtlinie auf Benutzerebene zu erstellen, klicken Sie auf **Benutzerrichtlinie**.
    
5. Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
   - Geben Sie unter **Name** einen Namen für die neue Richtlinie an (z. B. "externalContoso").
    
   - Geben Sie unter **Beschreibung** Einzelheiten über den Zweck der Richtlinie an (z. B. Archivierungsrichtlinie für externe Benutzer für Contoso)
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der Kommunikation mit internen Benutzern zu aktivieren oder zu deaktivieren.
    
   - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation zu aktivieren oder zu deaktivieren.
    
6. Klicken Sie auf **Commit**.
    
    > [!IMPORTANT]
    > Die Einstellungen einer Benutzerrichtlinie gelten nur für bestimmte Benutzer und Benutzergruppen, auf die Sie die Richtlinie anwenden. Ausführliche Informationen finden Sie unter [Anwenden einer Archivierungsrichtlinie auf Benutzer in Skype for Business Server.](apply-a-policy-to-users.md) 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Erstellen einer neuen Archivierungsrichtlinie mithilfe von Windows PowerShell

Sie können auch neue Archivierungsrichtlinien erstellen, indem Sie das Cmdlet Windows PowerShell **New-CsArchivingPolicy** verwenden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["New-CsArchivingPolicy".](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>So erstellen Sie eine neue Archivierungsrichtlinie auf Standortebene

Mit diesem Befehl wird eine neue Archivierungsrichtlinie für den Standort "Redmond" erstellt:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>So erstellen Sie eine neue Archivierungsrichtlinie auf Benutzerebene

Um eine neue Archivierungsrichtlinie auf Benutzerebene zu erstellen, geben Sie beim Erstellen der Richtlinie einfach eine eindeutige Identität an:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>So erstellen Sie eine neue Archivierungsrichtlinie, die die Archivierung interner Kommunikationssitzungen ermöglicht

Da in den vorherigen Befehlen keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, verwenden die neuen Richtlinien die Standardwerte für alle ihre Eigenschaften. Um Richtlinien zu erstellen, die unterschiedliche Eigenschaftswerte verwenden, fügen Sie einfach den entsprechenden Parameter und Parameterwert ein. Mit dem folgenden Befehl wird beispielsweise eine Archivierungsrichtlinie erstellt, die die Archivierung interner Chatsitzungen zulässt: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>So erstellen Sie eine neue Archivierungsrichtlinie, die die Archivierung von internen und externen Kommunikationssitzungen ermöglicht

Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Mit diesem Befehl wird beispielsweise die neue Richtlinie so konfiguriert, dass sowohl interne als auch externe Chatsitzungen archiviert werden:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```