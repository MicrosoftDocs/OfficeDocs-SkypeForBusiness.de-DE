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
# <a name="export-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="26cbf-103">Exportieren archivierter Daten in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="26cbf-103">Export archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="26cbf-104">**Zusammenfassung:** Informationen Sie zum Exportieren von archivierter Daten für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="26cbf-104">**Summary:** Learn how to export archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="26cbf-105">Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet **Export-CsArchivingData** Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern..</span><span class="sxs-lookup"><span data-stu-id="26cbf-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="26cbf-106">Daten werden archiviert, wenn Sie Microsoft Exchange-Integration aktivieren, in der Exchange-Speicher.</span><span class="sxs-lookup"><span data-stu-id="26cbf-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="26cbf-107">Daten, die in Exchange archiviert sind durchsuchbar und sichtbar.</span><span class="sxs-lookup"><span data-stu-id="26cbf-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="26cbf-108">Ausführliche Informationen zu den Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="26cbf-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="26cbf-109">Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="26cbf-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="26cbf-110">Sie können Daten mithilfe des Cmdlets „Export-CSArchivingData“ archivieren.</span><span class="sxs-lookup"><span data-stu-id="26cbf-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="26cbf-p102">Mit diesem Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank „atl-sql-001.contoso.com“ geschrieben wurden. Die entsprechende Ausgabedatei wird im Ordner „C:\ArchivingExports“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26cbf-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="26cbf-113">Der folgende Befehl exportiert Archivieren von Daten für einen einzelnen Benutzer: kenmyer@contoso.com. Dies erfolgt durch den Parameter "UserUri" gefolgt von SIP-Adresse des Benutzers einschließlich.</span><span class="sxs-lookup"><span data-stu-id="26cbf-113">The following command exports archiving data for a single user: kenmyer@contoso.com. This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="26cbf-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="26cbf-114">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="26cbf-115">Weitere Informationen finden Sie im Hilfethema für das [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="26cbf-115">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

