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
description: 'Zusammenfassung: Erfahren Sie, wie Archivierte Daten für Skype for Business Server exportiert werden.'
ms.openlocfilehash: bb23861ea7615584de3ce6247f7281d94b5c60853767aaaa6ae495d3a6264dc7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311083"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportieren archivierter Daten in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Archivierte Daten für Skype for Business Server exportiert werden.
  
In Archivierungsdatenbanken archivierte Daten sind nicht durchsuchbar oder in einem lesbaren Format, aber Sie können das Cmdlet **"Export-CsArchivingData"** verwenden, um Datensätze aus der Datenbank zu extrahieren und sie als Outlook EML-Datei (Electronic Mail) zu speichern.
  
Wenn Sie die Integration von Microsoft Exchange aktivieren, werden die Daten in Exchange Speichern archiviert. In Exchange archivierte Daten sind durchsuchbar und auffindbar. Ausführliche Informationen zum Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange Dokumentation.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe Windows PowerShell Cmdlets

Sie können archivierte Daten mithilfe des Cmdlets Export-CSArchivingData exportieren. 
  
Der folgende Befehl exportiert alle Archivierungsdaten, die seit dem 1. Juni 2012 in die Archivierungsdatenbank atl-sql-001.contoso.com geschrieben wurden. Die resultierende Ausgabedatei wird im Ordner "C:\ArchivingExports" gespeichert.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Der folgende Befehl exportiert Archivierungsdaten für einen einzelnen Benutzer: kenmyer@contoso.com. Dazu wird der Parameter "UserUri" gefolgt von der SIP-Adresse des Benutzers eingeschlossen. Zum Beispiel: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Export-CsArchivingData".](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
