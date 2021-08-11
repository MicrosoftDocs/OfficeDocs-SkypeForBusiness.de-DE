---
title: Verwalten des Löschens archivierter Daten in Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Bereinigung archivierter Daten für Skype for Business Server verwalten.'
ms.openlocfilehash: f6eafbacedc715dc3684a16eb17cd5e1b1ae59923046af5cf180e92bbf6a2266
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307076"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Verwalten des Löschens archivierter Daten in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Bereinigung archivierter Daten für Skype for Business Server verwalten.
  
Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine E-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in einen anderen Speicher verschoben werden müssen. Skype for Business Server stellt ein Sitzungsexporttool bereit, mit dem Sie archivierte Daten in durchsuchbare Transkripte exportieren können. Sie müssen definieren, wann archivierte und exportierte Daten gelöscht werden sollen. 
  
Weitere Informationen zum Exportieren von Daten mithilfe des Cmdlets **"Export-CsArchivingData"** finden Sie unter [Exportieren archivierter Daten in Skype for Business Server.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Verwalten des Löschens von Daten mithilfe der Systemsteuerung

So verwalten Sie das Löschen archivierter Daten mithilfe der Systemsteuerung:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration. Klicken Sie dann auf **Bearbeiten** und auf **Details anzeigen**, und gehen Sie anschließend folgendermaßen vor.
    
   - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
    
     - Zum Löschen aller Datensätze klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie die Anzahl der Tage an.
    
     - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
   - Zum Deaktivieren des Löschvorgangs deaktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**.
    
5. Klicken Sie auf **Commit**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Verwalten des Löschens von Daten mithilfe von Windows PowerShell

Sie können das Löschen archivierter Daten mithilfe der folgenden Windows PowerShell Cmdlets verwalten:
  
- Mit dem Cmdlet **"Set-CsArchivingConfiguration"** mit dem Parameter "EnablePurging" können Sie das Löschen archivierter Daten aktivieren oder deaktivieren.
    
- **Mit Invoke-CsArchivingDatabasePurge** können Sie Datensätze manuell aus der Archivierungsdatenbank löschen.
    
Beispielsweise ermöglicht der folgende Befehl das Löschen aller archivierten Daten. Nachdem dieser Befehl ausgeführt wurde, löscht Skype for Business Server alle Archivierungsdatensätze, die älter als der für den Parameter "KeepArchivingDataForDays" angegebene Wert sind. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Der folgende Befehl beschränkt das Löschen auf archivierte Datensätze, die in eine Datendatei exportiert wurden (mithilfe des Cmdlets **"Export-CSArchivingData").** Sie müssen auch den Parameter "PurgeExportedArchivesOnly" auf "True" ($True) festlegen:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Nachdem dieser Befehl ausgeführt wurde, löscht Skype for Business Server nur Archivierungsdatensätze, die zwei Kriterien erfüllen: 1) sie sind älter als der für den Parameter "KeepArchivingDataForDays" angegebene Wert; und, 2) sie wurden mithilfe des Cmdlets **"Export-CsArchivingData"** exportiert.
  
Um das automatische Löschen von Archivierungsdatensätzen zu deaktivieren, legen Sie den Parameter "EnablePurging" auf "False" ($False) fest:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

Im folgenden Beispiel wird das Cmdlet **Invoke-CsArchivingDatabasePurge** verwendet, um alle Datensätze, die älter als 24 Stunden sind, aus der Archivierungsdatenbank auf atl-sql-001.contoso.com zu löschen. Um sicherzustellen, dass alle Datensätze gelöscht werden, einschließlich datensätzen, die nicht exportiert wurden, wird der Parameter PurgeExportedArchivesOnly auf False ($False) festgelegt:
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
