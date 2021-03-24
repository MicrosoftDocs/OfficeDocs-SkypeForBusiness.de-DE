---
title: Exportieren archivierter Daten in Skype for Business Server
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
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Zusammenfassung: Informationen zum Exportieren archivierter Daten für Skype for Business Server.'
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095379"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportieren archivierter Daten in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.
  
In Archivierungsdatenbanken archivierte Daten sind nicht durchsuchbar oder in einem lesbaren Format, Aber Sie können das **Cmdlet Export-CsArchivingData** verwenden, um Datensätze aus der Datenbank zu extrahieren und als Outlook Electronic Mail (EML)-Datei zu speichern.
  
Wenn Sie die Microsoft Exchange-Integration aktivieren, werden Daten in Exchange-Speichern archiviert. In Exchange archivierte Daten können durchsucht und gefunden werden. Ausführliche Informationen zum Zugriff auf in Exchange archivierte Daten finden Sie in der Exchange-Dokumentation.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe Windows PowerShell Cmdlets

Sie können archivierte Daten mithilfe des cmdlets Export-CSArchivingData exportieren. 
  
Mit dem folgenden Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 atl-sql-001.contoso.com Archivierungsdatenbank geschrieben wurden. Die resultierende Ausgabedatei wird im Ordner C:\ArchivingExports gespeichert.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@contoso.com. Dazu wird der Parameter UserUri gefolgt von der SIP-Adresse des Benutzers verwendet. Zum Beispiel: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet Export-CsArchivingData.](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
