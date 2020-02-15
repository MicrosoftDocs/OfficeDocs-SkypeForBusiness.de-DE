---
title: 'Lync Server 2013: durchführen und Überwachen von Sicherungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 631ec1c7c383bf6200e44378b37db7273bbf125d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="eb576-102">Durchführen und Überwachen von Sicherungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb576-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb576-103">_**Letztes Änderungsstand des Themas:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="eb576-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="eb576-104">Ihre geschäftlichen Prioritäten sollten die Spezifikation der Sicherungs-und Wiederherstellungsanforderungen für Ihre Organisation vorantreiben.</span><span class="sxs-lookup"><span data-stu-id="eb576-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="eb576-105">Das Durchführen von Sicherungen der Server und Daten ist die erste Verteidigungslinie bei der Planung eines Notfalls.</span><span class="sxs-lookup"><span data-stu-id="eb576-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="eb576-106">Computer, auf denen lync Server 2013 Dienste oder Server Rollen ausgeführt werden, müssen über eine Kopie der aktuellen Topologie, der aktuellen Konfigurationseinstellungen und der aktuellen Richtlinien verfügen, bevor Sie in ihrer benannten Rolle funktionieren können.</span><span class="sxs-lookup"><span data-stu-id="eb576-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="eb576-107">Lync Server ist dafür verantwortlich, sicherzustellen, dass diese Informationen an jeden Computer weitergeleitet werden, der ihn benötigt.</span><span class="sxs-lookup"><span data-stu-id="eb576-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="eb576-108">Die Cmdlets **Export-CsConfiguration** und **Import-CsConfiguration** werden verwendet, um die lync Server Topologie, die Konfigurationseinstellungen und Richtlinien während eines Upgrades des zentralen Verwaltungsspeichers zu sichern und wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="eb576-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="eb576-109">Mit den Cmdlets **Export-CsConfiguration** können Sie Daten in a exportieren. ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="eb576-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="eb576-110">Anschließend können Sie das Cmdlet **Import-CsConfiguration** verwenden, um dies zu lesen. ZIP-Datei, und stellen Sie die Topologie, die Konfigurationseinstellungen und Richtlinien im zentralen Verwaltungsspeicher wieder her.</span><span class="sxs-lookup"><span data-stu-id="eb576-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="eb576-111">Anschließend repliziert die Replikationsdienste von lync Server die wiederhergestellten Informationen auf andere Computer, auf denen lync Server Dienste installiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb576-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="eb576-112">Die Möglichkeit zum Exportieren und Importieren von Konfigurationsdaten wird auch während der anfänglichen Konfiguration von Computern verwendet, die sich in Ihrem Umkreisnetzwerk befinden (beispielsweise Edgeserver).</span><span class="sxs-lookup"><span data-stu-id="eb576-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="eb576-113">Wenn Sie einen Computer im Umkreisnetzwerk konfigurieren, müssen Sie zunächst eine manuelle Replikation mit den CsConfiguration-Cmdlets ausführen: Sie müssen die Konfigurationsdaten mithilfe von **Export-CsConfiguration** exportieren und dann kopieren. ZIP-Datei auf dem Computer im Umkreisnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="eb576-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="eb576-114">Anschließend können Sie die Daten mit dem Cmdlet **Import-CsConfiguration** und dem Parameter "LocalStore" importieren.</span><span class="sxs-lookup"><span data-stu-id="eb576-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="eb576-115">Sie müssen dies nur einmal tun.</span><span class="sxs-lookup"><span data-stu-id="eb576-115">You only have to do this one time.</span></span> <span data-ttu-id="eb576-116">Danach erfolgt die Replikation automatisch.</span><span class="sxs-lookup"><span data-stu-id="eb576-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="eb576-117">Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet **Export-CsConfiguration** lokal ausführen: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="eb576-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="eb576-118">Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der Windows PowerShell Aufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="eb576-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="eb576-119">Alle SQL 2012-Back-End-Datenbanken sollten gemäß [bewährter SQL-Methoden](http://go.microsoft.com/fwlink/p/?linkid=290716)gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="eb576-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="eb576-120">Regelmäßige Tests des Notfallwiederherstellungsplans für Ihre lync Server 2013 Infrastruktur sollten in einer Laborumgebung durchgeführt werden, die die Produktionsumgebung so genau wie möglich imitiert.</span><span class="sxs-lookup"><span data-stu-id="eb576-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="eb576-121">Weitere Informationen zum Testen der Notfallwiederherstellung erhalten Sie in den monatlichen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="eb576-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="eb576-122">Beachten Sie, dass die Sicherungshäufigkeit basierend auf Ihrem Wiederherstellungs-und Wiederherstellungspunkte-Ziel angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb576-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="eb576-123">Als bewährte Methode sollten Sie regelmäßige, periodische Momentaufnahmen im Laufe des Tages durchführen.</span><span class="sxs-lookup"><span data-stu-id="eb576-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="eb576-124">Im Allgemeinen sollten Sie alle 24 Stunden vollständige Sicherungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="eb576-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eb576-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb576-125">See Also</span></span>


[<span data-ttu-id="eb576-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb576-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="eb576-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb576-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="eb576-128">Bewährte Methoden für SQL</span><span class="sxs-lookup"><span data-stu-id="eb576-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

