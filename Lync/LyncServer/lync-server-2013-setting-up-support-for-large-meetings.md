---
title: 'Lync Server 2013: Einrichten der Unterstützung für umfangreiche Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03196c705253320e31e2483cc89b2aca386ff1af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="757ce-102">Einrichten der Unterstützung für umfangreiche Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="757ce-102">Setting up support for large meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="757ce-103">_**Letztes Änderungsdatum des Themas:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="757ce-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="757ce-104">Zur Unterstützung großer Besprechungen mit bis zu 1000-Benutzern müssen eine geeignete Topologie erstellt, Hardware-und Softwarevoraussetzungen erfüllt und die Umgebung entsprechend konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="757ce-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="757ce-105">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="757ce-105">Topology Requirements</span></span>

<span data-ttu-id="757ce-106">Bei einer einzigen großen Besprechung sind mindestens ein Front-End und ein Back-End-Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="757ce-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="757ce-107">Zur Bereitstellung einer höheren Verfügbarkeit empfehlen wir jedoch einen zwei Front-End-Serverpool mit gespiegelten Back-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="757ce-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="757ce-108">Der Benutzer, der die umfangreichen Besprechungen hostet, muss sein Benutzerkonto in diesem Pool verwaltet haben.</span><span class="sxs-lookup"><span data-stu-id="757ce-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="757ce-109">Es wird jedoch nicht empfohlen, andere Benutzerkonten in diesem Pool zu hosten.</span><span class="sxs-lookup"><span data-stu-id="757ce-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="757ce-110">Verwenden Sie Sie stattdessen nur für die umfangreichen Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="757ce-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="757ce-111">Die bewährte Methode besteht darin, ein spezielles Benutzerkonto in diesem Pool zu erstellen, das nur zum Hosten großer Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="757ce-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="757ce-112">Da die große Besprechungs Einstellung für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme haben, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu bewerben, wenn ein PSTN-Endpunkt involviert ist.</span><span class="sxs-lookup"><span data-stu-id="757ce-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="757ce-113">Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="757ce-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="757ce-114">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheitsinformationen in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="757ce-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="757ce-115">Wenn Sie zusätzlich optional eine Sicherung zur Notfallwiederherstellung und ein Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie ihn auch gemeinsam mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum verwenden.</span><span class="sxs-lookup"><span data-stu-id="757ce-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="757ce-116">Ausführliche Informationen finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="757ce-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="757ce-117">![Konfiguration des umfangreichen Besprechungs Pools] (images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Konfiguration des umfangreichen Besprechungs Pools")</span><span class="sxs-lookup"><span data-stu-id="757ce-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="757ce-118">Zusätzliche Notizen zur Topologie:</span><span class="sxs-lookup"><span data-stu-id="757ce-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="757ce-119">Eine Dateifreigabe ist erforderlich, um Besprechungsinhalte zu speichern und um, wenn ein Archivierungsserver bereitgestellt und aktiviert wurde, die Archivierungsdateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="757ce-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="757ce-120">Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="757ce-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="757ce-121">Details zum Konfigurieren der Dateifreigabe finden Sie unter [Konfigurieren des Dateispeichers für lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="757ce-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="757ce-122">Ein Office Web Apps-Server ist erforderlich, um die PowerPoint-Präsentations Funktionalität in umfangreichen Besprechungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="757ce-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="757ce-123">Der Office Web Apps-Server kann für den umfangreichen Besprechungs Pool dediziert sein, oder er kann derselbe Office Web Apps-Server sein, der von anderen Pools auf der Website verwendet wird, in der der dedizierte Pool bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="757ce-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="757ce-124">Bei einem Lastenausgleich für die Front-End-Server ist ein Hardwaregerät zum Lastenausgleich für den HTTP-Datenverkehr (z. B. beim Herunterladen von Besprechungsinhalten) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="757ce-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="757ce-125">DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen.</span><span class="sxs-lookup"><span data-stu-id="757ce-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="757ce-126">Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="757ce-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="757ce-127">Wenn Sie den Monitoring Server für den dedizierten groß Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung des Überwachungsservers und der zugehörigen Datenbank, die für alle Front-End-Server Pools in ihrer lync Server-Bereitstellung freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="757ce-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="757ce-128">Hardware-und Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="757ce-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="757ce-129">Die Hardwareanforderungen für Server in einem dedizierten groß Besprechungs Pool sind dieselben wie für Ihre anderen lync Server 2013-Server.</span><span class="sxs-lookup"><span data-stu-id="757ce-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="757ce-130">Details zu den Hardwareanforderungen finden Sie unter "[Server-Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="757ce-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="757ce-131">Server in einem dedizierten groß Besprechungs Pool müssen allen lync Server 2013-Softwareanforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="757ce-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="757ce-132">Details zu den Softwareanforderungen finden Sie in der folgenden Dokumentation:</span><span class="sxs-lookup"><span data-stu-id="757ce-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="757ce-133">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="757ce-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="757ce-134">Unterstützte Datenbanksoftware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="757ce-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="757ce-135">Zusätzliche Softwareanforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="757ce-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="757ce-136">Darüber hinaus müssen sowohl lync Server 2013 als auch alle lync Server 2013-Clients über die neuesten Updates verfügen.</span><span class="sxs-lookup"><span data-stu-id="757ce-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="757ce-137">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="757ce-137">Configuration Requirements</span></span>

<span data-ttu-id="757ce-138">Wir empfehlen, speziell für große Besprechungen eine neue konferenzrichtlinie zu erstellen und dann die konferenzrichtlinie den Benutzern zuzuweisen, die sich in dem dedizierten Pool für große Besprechungen befinden.</span><span class="sxs-lookup"><span data-stu-id="757ce-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="757ce-139">Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="757ce-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="757ce-140">Setzen Sie die Option **MaxMeetingSize** auf **1000**.</span><span class="sxs-lookup"><span data-stu-id="757ce-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="757ce-141">(Der Standardwert ist **250**.)</span><span class="sxs-lookup"><span data-stu-id="757ce-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="757ce-142">Legen Sie die Option **AllowLargeMeetings** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="757ce-143">Legen Sie die Option **EnableAppDesktopSharing** auf **None** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="757ce-144">Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="757ce-145">Legen Sie die Option **AllowSharedNotes** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="757ce-146">Legen Sie die Option **AllowAnnotations** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="757ce-147">Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="757ce-148">Legen Sie die Option **AllowMultiview** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="757ce-149">Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="757ce-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="757ce-150">Die Unterstützung für 1000-Benutzer große Besprechungen in lync Server 2013 setzt voraus, dass die <STRONG>AllowLargeMeetings</STRONG> -Einstellung in der konferenzrichtlinie für den Besprechungsplaner auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="757ce-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="757ce-151">Wenn diese Einstellung auf "true" festgelegt ist, wird die lync-Benutzeroberfläche für besonders große Besprechungen optimiert, wenn Benutzer einer solchen Besprechung beitreten.</span><span class="sxs-lookup"><span data-stu-id="757ce-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="757ce-152">In einer umfangreichen Besprechung wird in lync nicht das erste oder das Update der vollständigen Besprechungsteilnehmer Liste angezeigt, bei der es sich um einen Leistungsengpass für den Client und lync Server 2013 handelt.</span><span class="sxs-lookup"><span data-stu-id="757ce-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="757ce-153">Stattdessen werden in lync nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="757ce-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="757ce-154">Lync zeigt weiterhin die Gesamtzahl der Teilnehmer an, die in den umfangreichen Besprechungen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="757ce-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="757ce-155">Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen, die für große Besprechungen nicht erforderlich sind, zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="757ce-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="757ce-156">Darüber hinaus müssen Sie den dedizierten Pool für große Besprechungen so konfigurieren, dass jeder lync Server 2013-Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungs Zeitplans verantwortlich ist, über die entsprechenden Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="757ce-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="757ce-157">Gehen Sie hierzu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="757ce-157">To do this, do the following:</span></span>

  - <span data-ttu-id="757ce-p114">Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.</span><span class="sxs-lookup"><span data-stu-id="757ce-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="757ce-161">Stellen Sie sicher, dass das Kontrollkästchen **zugewiesene Konferenztyp Standard** mäßig nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="757ce-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="757ce-162">Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für lync 2013 Konferenzen immer mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über die gleiche URL und Audioinformationen für die Teilnahme verfügen.</span><span class="sxs-lookup"><span data-stu-id="757ce-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="757ce-163">In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, weil jeder eine eigene, individuell zugewiesene Konferenz hat, und die URL-und Audioinformationen für die dauerhafte Teilnahme helfen, eine schnellere Besprechung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="757ce-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="757ce-164">Im Szenario mit großer Besprechung plant der große Besprechungs Support die umfangreichen Besprechungen jedoch mit einem einzigen Satz von Benutzeranmeldeinformationen und stellt dann den Besprechungs anfordernden Teilnehmer-URLs und Audioinformationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="757ce-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="757ce-165">In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.</span><span class="sxs-lookup"><span data-stu-id="757ce-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="757ce-166">Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="757ce-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="757ce-167">Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für lync 2013 geplant wird, wenn keine zugewiesene Konferenz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="757ce-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="757ce-168">Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="757ce-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="757ce-169">Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="757ce-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="757ce-170">Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="757ce-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

