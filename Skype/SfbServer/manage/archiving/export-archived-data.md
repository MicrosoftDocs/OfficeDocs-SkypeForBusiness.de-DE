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
description: 'Zusammenfassung: Erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.'
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817565"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportieren archivierter Daten in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.
  
In Archivierungsdatenbanken archivierte Daten sind nicht durchsuchbar oder in einem lesbaren Format, Aber Sie können das **Cmdlet "Export-CsArchivingData"** verwenden, um Datensätze aus der Datenbank zu extrahieren und als Outlook Electronic Mail (EML)-Datei zu speichern.
  
Wenn Sie die Microsoft Exchange-Integration aktivieren, werden Daten in den Exchange-Speichern archiviert. In Exchange archivierte Daten sind durchsuchbar und aufsuchbar. Ausführliche Informationen zum Zugriff auf in Exchange archivierte Daten finden Sie in der Exchange-Dokumentation.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe Windows PowerShell Cmdlets

Sie können archivierte Daten mithilfe des cmdlets Export-CSArchivingData exportieren. 
  
Mit dem folgenden Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 atl-sql-001.contoso.com Archivierungsdatenbank geschrieben wurden. Die resultierende Ausgabedatei wird im Ordner "C:\ArchivingExports" gespeichert.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@contoso.com. Dazu wird der Parameter "UserUri" gefolgt von der BENUTZER-SIP-Adresse verwendet. Beispiel: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Export-CsArchivingData".](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps)
  

