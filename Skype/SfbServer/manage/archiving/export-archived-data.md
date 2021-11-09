---
title: Exportieren archivierter Daten in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Zusammenfassung: Erfahren Sie, wie Archivierte Daten für Skype for Business Server exportiert werden.'
ms.openlocfilehash: ef9ffca2612adb088f9d06cdbaad809f72278595
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856782"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportieren archivierter Daten in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Archivierte Daten für Skype for Business Server exportiert werden.
  
In Archivierungsdatenbanken archivierte Daten sind nicht durchsuchbar oder in einem lesbaren Format, aber Sie können das Cmdlet **"Export-CsArchivingData"** verwenden, um Datensätze aus der Datenbank zu extrahieren und als Outlook EML-Datei (Electronic Mail) zu speichern.
  
Wenn Sie die Integration von Microsoft Exchange aktivieren, werden die Daten in Exchange Speichern archiviert. In Exchange archivierte Daten sind durchsuchbar und auffindbar. Ausführliche Informationen zum Zugriff auf daten, die in Exchange archiviert werden, finden Sie in der dokumentation Exchange.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe Windows PowerShell Cmdlets

Sie können archivierte Daten mithilfe des Cmdlets Export-CSArchivingData exportieren. 
  
Mit dem folgenden Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank atl-sql-001.contoso.com geschrieben wurden. Die resultierende Ausgabedatei wird im Ordner "C:\ArchivingExports" gespeichert.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Der folgende Befehl exportiert Archivierungsdaten für einen einzelnen Benutzer: kenmyer@contoso.com. Dazu wird der Parameter "UserUri" gefolgt von der SIP-Adresse des Benutzers eingeschlossen. Beispiel: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["Export-CsArchivingData".](/powershell/module/skype/export-csarchivingdata?view=skype-ps)
