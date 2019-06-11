---
title: 'Lync Server 2013: durchführen und Überwachen von Sicherungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="3363b-102">Durchführen und Überwachen von Sicherungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3363b-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3363b-103">_**Letztes Änderungsdatum des Themas:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="3363b-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="3363b-104">Ihre geschäftlichen Prioritäten sollten die Spezifikation von Sicherungs-und Wiederherstellungsanforderungen für Ihre Organisation steuern.</span><span class="sxs-lookup"><span data-stu-id="3363b-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="3363b-105">Das Durchführen von Sicherungen der Server und Daten ist die erste Verteidigungslinie bei der Planung eines Notfalls.</span><span class="sxs-lookup"><span data-stu-id="3363b-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="3363b-106">Computer, auf denen lync Server 2013-Dienste oder Serverrollen ausgeführt werden, müssen über eine Kopie der aktuellen Topologie, der aktuellen Konfigurationseinstellungen und der aktuellen Richtlinien verfügen, bevor Sie in ihrer benannten Rolle funktionieren können.</span><span class="sxs-lookup"><span data-stu-id="3363b-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="3363b-107">Lync Server ist dafür verantwortlich, sicherzustellen, dass diese Informationen an jeden Computer weitergeleitet werden, der Sie benötigt.</span><span class="sxs-lookup"><span data-stu-id="3363b-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="3363b-108">Die Cmdlets **Export-CsConfiguration** und **Import-CsConfiguration** werden verwendet, um die lync Server-Topologie, die Konfigurationseinstellungen und Richtlinien während eines Upgrades des zentralen Verwaltungsspeichers zu sichern und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="3363b-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="3363b-109">Mit den Cmdlets **Export-CsConfiguration** können Sie Daten in eine exportieren. ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="3363b-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="3363b-110">Anschließend können Sie das Cmdlet **Import-CsConfiguration** verwenden, um dies zu lesen. ZIP-Datei aus, und stellen Sie die Topologie, die Konfigurationseinstellungen und Richtlinien im zentralen Verwaltungsspeicher wieder her.</span><span class="sxs-lookup"><span data-stu-id="3363b-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="3363b-111">Anschließend werden die wiederhergestellten Informationen von den Replikationsdiensten von lync Server auf andere Computer repliziert, auf denen lync Server-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3363b-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="3363b-112">Die Möglichkeit zum Exportieren und Importieren von Konfigurationsdaten wird auch bei der Erstkonfiguration von Computern verwendet, die sich in Ihrem Umkreisnetzwerk befinden (beispielsweise Edgeserver).</span><span class="sxs-lookup"><span data-stu-id="3363b-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="3363b-113">Wenn Sie einen Computer im Umkreisnetzwerk konfigurieren, müssen Sie zuerst eine manuelle Replikation mithilfe der CsConfiguration-Cmdlets durchführen: Sie müssen die Konfigurationsdaten mithilfe von **Export-CsConfiguration** exportieren und dann das Kopieren. ZIP-Datei auf dem Computer im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="3363b-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="3363b-114">Anschließend können Sie **Import-CsConfiguration** und den localstore-Parameter verwenden, um die Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3363b-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="3363b-115">Sie müssen dies nur einmal tun.</span><span class="sxs-lookup"><span data-stu-id="3363b-115">You only have to do this one time.</span></span> <span data-ttu-id="3363b-116">Anschließend erfolgt die Replikation automatisch.</span><span class="sxs-lookup"><span data-stu-id="3363b-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="3363b-117">Wer dieses Cmdlet ausführen kann: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das **Export-CsConfiguration-** Cmdlet lokal auszuführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3363b-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="3363b-118">Führen Sie den folgenden Befehl aus der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugeordnet ist (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):</span><span class="sxs-lookup"><span data-stu-id="3363b-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="3363b-119">Alle SQL 2012-Back-End-Datenbanken sollten gemäß den [bewährten SQL-Methoden](http://go.microsoft.com/fwlink/p/?linkid=290716)gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="3363b-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="3363b-120">Regelmäßige Tests des Disaster Recovery-Plans für Ihre lync Server 2013-Infrastruktur sollten in einer Lab-Umgebung durchgeführt werden, die die Produktionsumgebung so genau wie möglich imitiert.</span><span class="sxs-lookup"><span data-stu-id="3363b-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="3363b-121">Weitere Informationen zu Disaster Recovery-Tests finden Sie in den monatlichen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="3363b-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="3363b-122">Beachten Sie, dass die Sicherungshäufigkeit basierend auf den Wiederherstellungspunkt-und Wiederherstellungspunkt Zielen angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="3363b-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="3363b-123">Als bewährte Methode können Sie regelmäßige, periodische Schnappschüsse über den ganzen Tag hinweg erstellen.</span><span class="sxs-lookup"><span data-stu-id="3363b-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="3363b-124">Im Allgemeinen sollten Sie alle 24 Stunden vollständige Sicherungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="3363b-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3363b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3363b-125">See Also</span></span>


[<span data-ttu-id="3363b-126">Importieren-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3363b-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="3363b-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="3363b-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="3363b-128">Bewährte Methoden für SQL</span><span class="sxs-lookup"><span data-stu-id="3363b-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

