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
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286137"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="7e85f-103">Exportieren von archivierten Daten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7e85f-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="7e85f-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie archivierte Daten für Skype for Business Server exportieren.</span><span class="sxs-lookup"><span data-stu-id="7e85f-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="7e85f-105">Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet **Export-CsArchivingData** Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern..</span><span class="sxs-lookup"><span data-stu-id="7e85f-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="7e85f-106">Wenn Sie die Microsoft Exchange-Integration aktivieren, werden die Daten in Exchange-Stores archiviert.</span><span class="sxs-lookup"><span data-stu-id="7e85f-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="7e85f-107">In Exchange archivierte Daten sind durchsuchbar und auffindbar.</span><span class="sxs-lookup"><span data-stu-id="7e85f-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="7e85f-108">Details zum Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="7e85f-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7e85f-109">Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7e85f-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7e85f-110">Sie können Daten mithilfe des Cmdlets „Export-CSArchivingData“ archivieren.</span><span class="sxs-lookup"><span data-stu-id="7e85f-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="7e85f-p102">Mit diesem Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank „atl-sql-001.contoso.com“ geschrieben wurden. Die entsprechende Ausgabedatei wird im Ordner „C:\ArchivingExports“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7e85f-p102">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012. The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="7e85f-113">Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: „kenmyer@contoso.com“.</span><span class="sxs-lookup"><span data-stu-id="7e85f-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="7e85f-114">Dies erfolgt durch Einschließen des UserUri-Parameters, gefolgt von der SIP-Adresse des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="7e85f-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="7e85f-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e85f-115">For example:</span></span> 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="7e85f-116">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7e85f-116">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
  

