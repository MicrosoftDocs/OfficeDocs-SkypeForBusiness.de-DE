---
title: Exportieren von archivierten Daten in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.'
ms.openlocfilehash: 0d48441290eda49ad6b7fecd63d15d74b25148fe
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991570"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>Exportieren von archivierten Daten in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.
  
Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet **Export-CsArchivingData** Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern..
  
Wenn Sie die Microsoft Exchange-Integration aktivieren, werden die Daten in Exchange-Stores archiviert. In Exchange archivierte Daten sind durchsuchbar und auffindbar. Details zum Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange-Dokumentation.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets

Sie können Daten mithilfe des Cmdlets „Export-CSArchivingData“ archivieren. 
  
Mit diesem Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank „atl-sql-001.contoso.com“ geschrieben wurden. Die entsprechende Ausgabedatei wird im Ordner „C:\ArchivingExports“ gespeichert.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: „kenmyer@contoso.com“. Dies erfolgt durch Einschließen des UserUri-Parameters, gefolgt von der SIP-Adresse des Benutzers. Beispiel: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .
  

