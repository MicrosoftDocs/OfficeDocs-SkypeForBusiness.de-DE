---
title: 'Lync Server 2013: Exportieren archivierter Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="6af1e-102">Exportieren archivierter Daten aus lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af1e-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6af1e-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6af1e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6af1e-104">In Archivierungsdatenbanken archivierte Daten sind nicht durchsuchbar oder in einem lesbaren Format, aber Sie können das Cmdlet Export-CsArchivingData verwenden, um Datensätze aus der Datenbank zu extrahieren und als EML-Datei (Outlook Electronic Mail) zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6af1e-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="6af1e-105">Ausführliche Informationen zum Exportieren archivierter Daten finden Sie unter [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6af1e-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="6af1e-106">Wenn Sie Microsoft Exchange Integration aktivieren, werden Daten in Exchange 2013 speichern archiviert.</span><span class="sxs-lookup"><span data-stu-id="6af1e-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="6af1e-107">In Exchange 2013 archivierte Daten sind durchsuchbar und auffindbar.</span><span class="sxs-lookup"><span data-stu-id="6af1e-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="6af1e-108">Ausführliche Informationen zur Unterstützung integrierter Kommunikation für Exchange 2013 und lync Server 2013 finden Sie unter [Exchange Server and SharePoint Integration Support in lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6af1e-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="6af1e-109">Ausführliche Informationen zum Zugreifen auf Daten, die in Exchange archiviert werden, finden Sie in der Exchange 2013 Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6af1e-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6af1e-110">Exportieren von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6af1e-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6af1e-111">Archivierungsdaten können mithilfe des Cmdlets "Export-CSArchivingData" exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="6af1e-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="6af1e-112">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6af1e-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6af1e-113">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="6af1e-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="6af1e-114">**So exportieren Sie Archivierungsdaten**</span><span class="sxs-lookup"><span data-stu-id="6af1e-114">**To export archiving data**</span></span>

  - <span data-ttu-id="6af1e-115">Mit diesem Befehl werden alle Archivierungsdaten, die in die Archivierungsdatenbank ATL-SQL-001.litwareinc.com geschrieben wurden, seit dem 1. Juni 2012 exportiert.</span><span class="sxs-lookup"><span data-stu-id="6af1e-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="6af1e-116">Die resultierende Ausgabedatei wird im Ordner C:\\ArchivingExports gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6af1e-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="6af1e-117">**So exportieren Sie Archivierungsdaten für einen einzelnen Benutzer**</span><span class="sxs-lookup"><span data-stu-id="6af1e-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="6af1e-p105">Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@litwareinc.com. Hierzu wird der Parameter "UserUri" gefolgt von der SIP-Adresse des Benutzers eingefügt. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6af1e-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="6af1e-121">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="6af1e-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6af1e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6af1e-122">See Also</span></span>


[<span data-ttu-id="6af1e-123">Unterstützung von Exchange Server und SharePoint-Integration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6af1e-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="6af1e-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="6af1e-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="6af1e-125">Verwalten der Lync Server 2013-Archivierung</span><span class="sxs-lookup"><span data-stu-id="6af1e-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

