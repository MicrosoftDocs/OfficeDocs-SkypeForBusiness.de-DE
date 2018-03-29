---
title: Exportieren archivierter Daten in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Zusammenfassung: Informationen Sie zum Exportieren von archivierter Daten für Skype für Business Server 2015.'
ms.openlocfilehash: f5fe222589efa5ce6e8e21151817042497fb6cc6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="export-archived-data-in-skype-for-business-server-2015"></a>Exportieren archivierter Daten in Skype for Business Server 2015

**Zusammenfassung:** Informationen Sie zum Exportieren von archivierter Daten für Skype für Business Server 2015.
  
Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet **Export-CsArchivingData** Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern..
  
Daten werden archiviert, wenn Sie Microsoft Exchange-Integration aktivieren, in der Exchange-Speicher. Daten, die in Exchange archiviert sind durchsuchbar und sichtbar. Ausführliche Informationen zu den Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange-Dokumentation.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets

Sie können Daten mithilfe des Cmdlets „Export-CSArchivingData“ archivieren. 
  
Mit diesem Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank „atl-sql-001.contoso.com“ geschrieben wurden. Die entsprechende Ausgabedatei wird im Ordner „C:\ArchivingExports“ gespeichert.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Der folgende Befehl exportiert Archivieren von Daten für einen einzelnen Benutzer: kenmyer@contoso.com. Dies erfolgt durch den Parameter "UserUri" gefolgt von SIP-Adresse des Benutzers einschließlich. Beispiel: 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema für das [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) -Cmdlet.
  

