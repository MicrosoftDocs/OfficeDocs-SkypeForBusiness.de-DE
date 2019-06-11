---
title: 'Lync Server 2013: Exportieren von archivierten Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="c00b1-102">Exportieren von archivierten Daten aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c00b1-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c00b1-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c00b1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c00b1-104">Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet Export-CsArchivingData Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern..</span><span class="sxs-lookup"><span data-stu-id="c00b1-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="c00b1-105">Ausführliche Informationen zum Exportieren von archivierten Daten finden Sie unter [exportieren-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c00b1-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="c00b1-106">Wenn Sie die Microsoft Exchange-Integration aktivieren, werden die Daten in Exchange 2013-Stores archiviert.</span><span class="sxs-lookup"><span data-stu-id="c00b1-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="c00b1-107">In Exchange 2013 archivierte Daten sind durchsuchbar und auffindbar.</span><span class="sxs-lookup"><span data-stu-id="c00b1-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="c00b1-108">Details zur Unterstützung der integrierten Kommunikation für Exchange 2013 und lync Server 2013 finden Sie unter Unterstützung für [Exchange Server und SharePoint-Integration in lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="c00b1-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="c00b1-109">Details zum Zugriff auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange 2013-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="c00b1-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c00b1-110">Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c00b1-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c00b1-111">Archivierungsdaten können mithilfe des Cmdlets Export-CSArchivingData exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="c00b1-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="c00b1-112">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c00b1-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c00b1-113">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c00b1-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="c00b1-114">**So exportieren Sie Archivierungsdaten**</span><span class="sxs-lookup"><span data-stu-id="c00b1-114">**To export archiving data**</span></span>

  - <span data-ttu-id="c00b1-115">Mit diesem Befehl werden alle Archivierungsdaten exportiert, die in die Archivierungsdatenbank ATL-SQL-001.litwareinc.com seit dem 1. Juni 2012 geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="c00b1-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="c00b1-116">Die resultierende Ausgabedatei wird im Ordner C:\\ArchivingExports gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c00b1-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="c00b1-117">**So exportieren Sie Archivierungsdaten für einen einzelnen Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c00b1-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="c00b1-118">Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c00b1-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="c00b1-119">Hierzu wird der Parameter „UserUri“, gefolgt von der SIP-Adresse des Benutzers, eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c00b1-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="c00b1-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c00b1-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="c00b1-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="c00b1-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c00b1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c00b1-122">See Also</span></span>


[<span data-ttu-id="c00b1-123">Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c00b1-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="c00b1-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="c00b1-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="c00b1-125">Verwalten der Lync Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="c00b1-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

