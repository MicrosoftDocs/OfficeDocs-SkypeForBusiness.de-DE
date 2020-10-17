---
title: 'Lync Server 2013: Einrichten der Unterstützung für große Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e7d7796a879398d5f73ebfc67cc6cc6a68b5b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497582"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="31439-102">Einrichten der Unterstützung für große Besprechungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31439-102">Setting up support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31439-103">_**Letztes Änderungsstand des Themas:** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="31439-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="31439-104">Wenn Besprechungen mit mehr als 1000 Benutzern unterstützt werden sollen, ist es erforderlich, eine entsprechende Topologie zu erstellen, die Anforderungen an Hardware und Software zu erfüllen und die Umgebung entsprechend zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31439-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="31439-105">Anforderungen im Hinblick auf die Topologie</span><span class="sxs-lookup"><span data-stu-id="31439-105">Topology Requirements</span></span>

<span data-ttu-id="31439-106">Eine einzelne große Besprechung erfordert mindestens eine Front-End-Server und einen Back-End-Server.</span><span class="sxs-lookup"><span data-stu-id="31439-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="31439-107">Um eine hohe Verfügbarkeit zu gewährleisten, wird jedoch ein zwei Front-End-Server Pool mit gespiegelten Back-End-Servern empfohlen.</span><span class="sxs-lookup"><span data-stu-id="31439-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="31439-108">Die Benutzerkonten der Benutzer, die große Besprechungen durchführen, müssen in diesem Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="31439-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="31439-109">Es wird jedoch nicht empfohlen, dass andere Benutzerkonten in diesem Pool gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="31439-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="31439-110">Er sollte nur für diese großen Besprechungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31439-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="31439-111">In diesem Pool sollte ein spezielles Benutzerkonto erstellt werden, das nur zur Durchführung großer Besprechungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31439-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="31439-112">Da die Einstellung für große Besprechungen für die Leistung optimiert ist, kann die Verwendung als normaler Benutzer Probleme verursachen, beispielsweise die Unfähigkeit, eine P2P-Sitzung zu einer Besprechung zu heraufstufen, wenn ein PSTN-Endpunkt beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="31439-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="31439-113">Bei der Verwaltung eines Pools mit genau zwei Front-End-Servern sind spezielle Überlegungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31439-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="31439-114">Weitere Informationen finden Sie unter [Topologien und Komponenten für Front-End-Server, Instant Messaging und Anwesenheit in lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="31439-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="31439-115">Wenn Sie optional Notfall Wiederherstellungs Sicherungen und Failover für den für große Besprechungen verwendeten Pool bereitstellen möchten, können Sie diese mit einem ähnlich eingerichteten dedizierten Pool in einem anderen Rechenzentrum koppeln.</span><span class="sxs-lookup"><span data-stu-id="31439-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="31439-116">Ausführliche Informationen finden Sie unter [Planung für hohe Verfügbarkeit und Notfallwiederherstellung in lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="31439-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="31439-117">![Konfiguration für umfangreiche Besprechungs Pools](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Konfiguration für umfangreiche Besprechungs Pools")</span><span class="sxs-lookup"><span data-stu-id="31439-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="31439-118">Zusätzliche Notizen zur Topologie:</span><span class="sxs-lookup"><span data-stu-id="31439-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="31439-119">Eine Dateifreigabe ist zum Speichern der Archivierungsdateien erforderlich, wenn der Besprechungsinhalt gespeichert wird und wenn Archivierungsserver bereitgestellt und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="31439-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="31439-120">Die Dateifreigabe kann dem Pool zugeordnet werden oder dieselbe Dateifreigabe sein, die von einem anderen Pool an diesem Standort verwendet wurde, an dem der Pool bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="31439-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="31439-121">Ausführliche Informationen zum Konfigurieren der Dateifreigabe finden Sie unter [configure File Storage for lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="31439-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="31439-122">Für die Aktivierung der PowerPoint-Präsentationsfunktion in großen Besprechungen ist ein Office-webapps-Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31439-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="31439-123">Der Office Web Apps-Server kann für den großen Besprechungs Pool reserviert werden, oder es kann sich um denselben Office Web Apps-Server handeln, der von anderen Pools an dem Standort verwendet wird, an dem der dedizierte Pool bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="31439-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="31439-124">Für den Lastenausgleich der Front-End-Server ist ein Hardwarelastenausgleich für den HTTP-Datenverkehr erforderlich (beispielsweise das Herunterladen von Besprechungsinhalten).</span><span class="sxs-lookup"><span data-stu-id="31439-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="31439-125">DNS-Lastenausgleich wird für den SIP-Datenverkehr empfohlen.</span><span class="sxs-lookup"><span data-stu-id="31439-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="31439-126">Ausführliche Informationen finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31439-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="31439-127">Wenn Sie Monitoring Server für den dedizierten großen Besprechungs Pool verwenden möchten, empfehlen wir die Verwendung der Monitoring Server und der zugehörigen Datenbank, die für alle Front-End-Server Pools in ihrer lync Server-Bereitstellung freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="31439-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="31439-128">Voraussetzungen für Hardware und Software</span><span class="sxs-lookup"><span data-stu-id="31439-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="31439-129">Die Hardwareanforderungen für Server in einem dedizierten großen Besprechungs Pool entsprechen denen für andere lync Server 2013 Server.</span><span class="sxs-lookup"><span data-stu-id="31439-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="31439-130">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter "[Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="31439-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="31439-131">Server in einem dedizierten großen Besprechungs Pool müssen alle lync Server 2013 Softwareanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="31439-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="31439-132">Ausführliche Informationen zu den Softwareanforderungen finden Sie in den folgenden Dokumentationen:</span><span class="sxs-lookup"><span data-stu-id="31439-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="31439-133">Betriebssystemunterstützung für Server und Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31439-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="31439-134">Unterstützung der Datenbanksoftware in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31439-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="31439-135">Zusätzliche Softwareanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31439-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="31439-136">Darüber hinaus müssen sowohl lync Server 2013 als auch alle lync Server 2013-Clients über die neuesten Updates verfügen.</span><span class="sxs-lookup"><span data-stu-id="31439-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="31439-137">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="31439-137">Configuration Requirements</span></span>

<span data-ttu-id="31439-p110">Es wird empfohlen, eine neue Konferenzrichtlinie speziell für große Besprechungen zu erstellen und diese anschließend den Benutzern zuzuweisen, die auf den dedizierten großen Besprechungspools gehostet werden. Mithilfe der folgenden Einstellungen können Sie die Konferenzrichtlinie konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="31439-p110">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool. Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="31439-p111">Legen Sie die Option **MaxMeetingSize** auf **1000** fest. (Der Standardwert ist **250**.)</span><span class="sxs-lookup"><span data-stu-id="31439-p111">Set the **MaxMeetingSize** option to **1000**. (The default is **250**.)</span></span>

  - <span data-ttu-id="31439-142">Legen Sie die Option **AllowLargeMeetings** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="31439-143">Legen Sie die Option **EnableAppDesktopSharing** auf **Keine** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="31439-144">Legen Sie die Option **AllowUserToScheduleMeetingsWithAppSharing** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="31439-145">Legen Sie die Option **AllowSharedNotes** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="31439-146">Legen Sie die Option **AllowAnnotations** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="31439-147">Legen Sie die Option **DisablePowerPointAnnotations** auf **True** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="31439-148">Legen Sie die Option **AllowMultiview** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="31439-149">Legen Sie die Option **EnableMultiviewJoin** auf **False** fest.</span><span class="sxs-lookup"><span data-stu-id="31439-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31439-150">Die Unterstützung für 1000 Benutzer große Besprechungen in lync Server 2013 erfordert, dass die <STRONG>AllowLargeMeetings</STRONG> -Einstellung in der konferenzrichtlinie für den Besprechungsplaner auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="31439-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="31439-151">Wenn diese Einstellung auf "true" festgelegt ist, wird die lync-Umgebung für extra große Besprechungen optimiert, wenn Benutzer einer solchen Besprechung beitreten.</span><span class="sxs-lookup"><span data-stu-id="31439-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="31439-152">In einer großen Besprechung wird in lync nicht die anfängliche oder aktualisierte Liste der vollständigen Besprechungsteilnehmer angezeigt, die sowohl für den Client als auch für den lync Server 2013 einen Leistungsengpass darstellt.</span><span class="sxs-lookup"><span data-stu-id="31439-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="31439-153">Stattdessen werden in lync nur Informationen über den Benutzer und die Liste der Referenten der Besprechung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31439-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="31439-154">In lync wird weiterhin die Gesamtzahl der Teilnehmer angezeigt, die in den großen Besprechungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="31439-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="31439-155">Mit Ausnahme der Einstellung **Maximale Besprechungsgröße** sind alle anderen hier angegeben Konferenzrichtlinieneinstellungen erforderlich, um die Konferenzfunktionen zu deaktivieren, die für große Besprechungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="31439-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="31439-156">Darüber hinaus müssen Sie den dedizierten großen Besprechungs Pool so konfigurieren, dass jeder lync Server 2013 Benutzer, der im Pool verwaltet wird und für die Verwaltung des Besprechungs Zeitplans zuständig ist, über die entsprechenden Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="31439-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="31439-157">Gehen Sie hierzu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="31439-157">To do this, do the following:</span></span>

  - <span data-ttu-id="31439-p114">Legen Sie die Option **Als Referenten festlegen** auf **Keine** fest. Normalerweise sind nur einige wenige Benutzer der gesamten Teilnehmer einer großen Besprechung Referenten, sodass die Teilnehmer nicht automatisch als Referenten für große Besprechungen zugelassen werden sollten. Die Referenten sollten stattdessen bei der geplanten Besprechung explizit festgelegt oder während der großen Besprechung explizit ernannt werden.</span><span class="sxs-lookup"><span data-stu-id="31439-p114">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="31439-161">Stellen Sie sicher, dass das Kontrollkästchen **zugewiesener Konferenztyp Standard** mäßig nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="31439-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="31439-162">Mit dieser Einstellung wird gesteuert, ob das Online Besprechungs-Add-in für lync 2013 Konferenzen immer mit der zugewiesenen Konferenz des Organisators plant, was bedeutet, dass geplante Besprechungen über dieselbe Join-URL und Audioinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="31439-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="31439-163">In Szenarien für die Zusammenarbeit in kleinen Gruppen funktioniert der zugewiesene Konferenztyp gut, da jeder über eine eigene zugewiesene Konferenz verfügt, und die URL und die Audioinformationen für den konstanten Beitritt helfen, eine schnellere Besprechungsteilnahme zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="31439-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="31439-164">Im Szenario mit großen Besprechungen werden die großen Besprechungen jedoch mithilfe eines einzigen Satzes von Benutzeranmeldeinformationen geplant, und dann werden den Besprechungs anfordernden Join-URLs und Audioinformationen zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="31439-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="31439-165">In diesem Fall funktioniert die Verwendung einer anderen URL für die Teilnahme an jeder Besprechung besser.</span><span class="sxs-lookup"><span data-stu-id="31439-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="31439-166">Stellen Sie sicher, dass das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen** nur aktiviert wird, wenn es erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31439-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="31439-167">Diese Einstellung wirkt sich auf den standardmäßigen Besprechungs Zugriffstyp aus, der vom Online Besprechungs-Add-in für lync 2013 geplant wird, wenn keine zugewiesene Konferenz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31439-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="31439-168">Die geeignete Option für diese Einstellung hängt von den Anforderungen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="31439-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="31439-169">Wenn die meisten großen Besprechungen in Ihrer Organisation interne Besprechungen sind, sollte diese Option nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="31439-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="31439-170">Wenn beim Großteil der großen Besprechungen externe Benutzer teilnehmen, sollte diese Option ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="31439-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

