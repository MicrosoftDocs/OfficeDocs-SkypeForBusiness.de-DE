---
title: Erstellen einer Archivierungskonfiguration in Skype for Business Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie eine Archivierungskonfiguration für Skype for Business Server erstellen.'
ms.openlocfilehash: f00e5b2b9254b53760351c162ea86cd195473788
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095429"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>Erstellen einer Archivierungskonfiguration in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie eine Archivierungskonfiguration für Skype for Business Server erstellen.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Konfigurieren von Archivierungsoptionen mithilfe der Systemsteuerung

So konfigurieren Sie Archivierungsoptionen für einen bestimmten Standort oder Pool: 
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie **auf der** Seite Archivierungskonfiguration auf **Neu,** und gehen Sie dann wie folgt vor: 
    
   - Klicken Sie zum Erstellen einer Standortarchivierungskonfiguration auf Standortkonfiguration, und wählen Sie dann unter Standort auswählen den Standort **aus,** der für die Archivierung konfiguriert werden soll.
    
   - Klicken Sie zum Erstellen einer Poolarchivierungskonfiguration auf **Poolkonfiguration,** und wählen Sie dann unter **Pool** auswählen den Pool aus, der für die Archivierung konfiguriert werden soll.
    
5. Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
   - Um nur Sofortnachrichtensitzungen zu archivieren, klicken Sie auf **Sofortnachrichtensitzungen archivieren**.
    
   - Klicken Sie zum Aktivieren der Archivierung für Im-Mail-Sitzungen und Webkonferenzen auf Im-Mail- und **Webkonferenzsitzungen archivieren.**
    
   - Klicken Sie auf Archivierung deaktivieren, um die Archivierung für diese Konfiguration **zu deaktivieren.**
    
6. Gehen Sie unter **Neue Archivierungseinstellung** wie folgt vor:
    
   - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um die Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
   - Klicken Sie auf das Kontrollkästchen Microsoft **Exchange-Integration,** um Microsoft Exchange Server Archivierungsdaten zu speichern.
    
   - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
    
     - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
    
     - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Konfigurieren von Archivierungsoptionen mithilfe Windows PowerShell

Sie können archivierungsoptionen auch für einen bestimmten Standort oder Pool konfigurieren, indem Sie das **Cmdlet New-CsArchivingConfiguration** verwenden.
  
Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungskonfigurationseinstellungen für den Standort "Redmond" erstellt:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. 
  
Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Im folgenden Beispiel wird eine Sammlung von Archivierungskonfigurationseinstellungen erstellt, die standardmäßig nur die Archivierung von Chatsitzungen zulassen:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Mit diesem Befehl werden beispielsweise die neuen Einstellungen zum Archivieren von Chatsitzungen und zum Blockieren von Chatnachrichten des Archivierungsdiensts konfiguriert:
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet New-CsArchivingConfiguration.](/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps)