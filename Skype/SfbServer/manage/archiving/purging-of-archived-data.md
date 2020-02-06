---
title: Verwalten der Bereinigung archivierter Daten in Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie das Löschen archivierter Daten für Skype for Business Server verwalten.'
ms.openlocfilehash: 7953c6085183e3ace0e395f0c8751897acd49380
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818877"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Verwalten der Bereinigung archivierter Daten in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie das Löschen archivierter Daten für Skype for Business Server verwalten.
  
Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine e-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in andere Speicher verschoben werden müssen. Skype for Business Server bietet ein Sitzungs Export Tool, mit dem Sie archivierte Daten in durchsuchbare Transkripte exportieren können. Sie müssen festlegen, wann archivierte und exportierte Daten gelöscht werden sollen. 
  
Weitere Informationen zum Exportieren von Daten mithilfe des Cmdlets **Export-CsArchivingData** finden Sie unter [Exportieren von archivierten Daten in Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Löschen von Daten über die Systemsteuerung

So löschen Sie archivierte Daten über die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
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
    
Der folgende Befehl ermöglicht beispielsweise, alle archivierten Daten zu löschen. Nachdem dieser Befehl ausgeführt wurde, löscht Skype for Business Server alle Archivierungsdaten Sätze, die älter als der für den "keeparchivingdatafordays"-Parameter angegebene Wert sind. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Der folgende Befehl beschränkt das Löschen auf archivierte Datensätze, die (mit dem Cmdlet **Export-CSArchivingData**) in eine Datendatei exportiert wurden. Außerdem müssen Sie den Parameter PurgeExportedArchivesOnly auf „True“ ($True) setzen:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Nachdem dieser Befehl ausgeführt wurde, werden von Skype for Business Server nur Archivierungsdaten Sätze bereinigt, die zwei Kriterien erfüllen: 1) Sie sind älter als der für den "keeparchivingdatafordays"-Parameter angegebene Wert; und 2) Sie wurden mit dem Cmdlet **Export-CsArchivingData** exportiert.
  
Setzen Sie zum Deaktivieren der automatischen Löschung archivierter Datensätze den Parameter „EnablePurging“ auf „False“ ($False).
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

Im folgenden Beispiel wird das **Invoke-CsArchivingDatabasePurge-** Cmdlet verwendet, um alle Datensätze, die mehr als 24 Stunden alt sind, aus der Archivierungsdatenbank auf ATL-SQL-001.contoso.com zu entfernen. Um sicherzustellen, dass alle Datensätze gelöscht werden (also auch Datensätze, die nicht exportiert wurden), wird der Parameter „PurgeExportedArchivesOnly“ auf „False“ ($False) festgelegt:
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
