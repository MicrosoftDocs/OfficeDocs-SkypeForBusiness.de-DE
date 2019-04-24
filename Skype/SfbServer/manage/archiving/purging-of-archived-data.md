---
title: Verwalten der Löschung von archivierten Daten in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Zusammenfassung: Informationen Sie zum Verwalten der Löschung von archivierten Daten für Skype für Business Server.'
ms.openlocfilehash: 5483871d69932239f5d6e654c95edf1feac7b9d9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211032"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Verwalten der Löschung von archivierten Daten in Skype für Business Server

**Zusammenfassung:** Informationen Sie zum Verwalten der Löschung von archivierten Daten für Skype für Business Server.
  
Die Archivierungsdatenbank kann nicht für die langfristige Aufbewahrung und Skype für Business Server bietet keiner (Suche) e-Discovery-Lösung für archivierte Daten, damit Daten in einen anderen Speicher verschoben werden müssen. Skype für Business Server bietet eine Sitzung Exporttool, die Sie zum Exportieren von archivierter Daten in durchsuchbare Protokolle verwenden können. Sie müssen festlegen, wann archivierte und exportierte Daten gelöscht werden sollen. 
  
Weitere Informationen zum Exportieren von Daten mithilfe des **Export-CsArchivingData** -Cmdlets finden Sie unter [Exportieren von archivierten Daten in Skype für Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Löschen von Daten über die Systemsteuerung

So löschen Sie archivierte Daten über die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.
    
4. Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:
    
   - Aktivieren Sie zum Starten des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
    
     - Wenn Sie alle Datensätze löschen möchten, klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie die Anzahl der Tage an.
    
     - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
   - Deaktivieren Sie zum Beenden des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren**.
    
5. Klicken Sie auf **Commit ausführen**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Löschen von Daten über die Windows PowerShell

Mit den folgenden Windows PowerShell-Cmdlets können Sie archivierte Daten löschen:
  
- Mit dem Cmdlet **Set-CsArchivingConfiguration** und dem Parameter EnablePurging können Sie das Löschen archivierter Daten aktivieren oder deaktivieren.
    
- Mit **Invoke-CsArchivingDatabasePurge** können Sie Datensätze manuell aus der Archivierungsdatenbank löschen.
    
Der folgende Befehl ermöglicht beispielsweise, alle archivierten Daten zu löschen. Nachdem dieser Befehl ausgeführt wird, wird die Skype für Business Server alle archivierten Datensätze, die älter sind als der Wert für den Parameter KeepArchivingDataForDays angegebene entfernen. 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Der folgende Befehl beschränkt das Löschen auf archivierte Datensätze, die (mit dem Cmdlet **Export-CSArchivingData**) in eine Datendatei exportiert wurden. Außerdem müssen Sie den Parameter PurgeExportedArchivesOnly auf „True“ ($True) setzen:
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Nachdem Sie diesen Befehl ausgeführt haben, bereinigen Skype für Business Server nur archivierten Datensätze, die zwei Kriterien erfüllen: 1) sie älter als der Wert für den Parameter KeepArchivingDataForDays; angegeben sind und 2) sie mithilfe des **Export-CsArchivingData** -Cmdlets ausgeführt worden sind.
  
Setzen Sie zum Deaktivieren der automatischen Löschung archivierter Datensätze den Parameter „EnablePurging“ auf „False“ ($False).
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

Das folgende Beispiel verwendet das Cmdlet " **Invoke-CsArchivingDatabasePurge** ", um alle Datensätze aus der Archivierungsdatenbank auf Atl-Sql-001.contoso.com mehr als 24 Stunden bereinigen. Um sicherzustellen, dass alle Datensätze gelöscht werden (also auch Datensätze, die nicht exportiert wurden), wird der Parameter „PurgeExportedArchivesOnly“ auf „False“ ($False) festgelegt:
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
