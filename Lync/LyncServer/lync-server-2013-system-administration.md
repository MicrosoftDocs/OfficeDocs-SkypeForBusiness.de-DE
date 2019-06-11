---
title: 'Lync Server 2013: System Verwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="46368-102">System Verwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46368-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46368-103">_**Letztes Änderungsdatum des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="46368-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="46368-104">Die System Administration umfasst die täglichen administrativen Aufgaben, sowohl geplant als auch on-Demand, die erforderlich sind, um ein IT-System reibungslos funktionieren zu lassen.</span><span class="sxs-lookup"><span data-stu-id="46368-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="46368-105">In der Regel werden Systemverwaltungsaufgaben durch schriftliche Verfahren abgedeckt.</span><span class="sxs-lookup"><span data-stu-id="46368-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="46368-106">Mithilfe dieser Verfahren können Sie sicherstellen, dass alle Supportmitarbeiter dieselben Standardtools und-Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="46368-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="46368-107">In einer lync-Umgebung umfassen typische Systemverwaltungsaufgaben das Sichern und Archivieren von Pools, das Überwachen von Protokollen, das Erstellen und Verwalten von Benutzern und das Aktualisieren der Antivirensoftware.</span><span class="sxs-lookup"><span data-stu-id="46368-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="46368-108">System Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="46368-108">System troubleshooting</span></span>

<span data-ttu-id="46368-109">Eine Organisation muss bereit sein, mit unerwarteten Problemen umzugehen, und es sollte ein Verfahren zum Verwalten von Problemen ab dem Zeitpunkt vorhanden sein, zu dem Sie bis zu Ihrer Lösung gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="46368-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="46368-110">Informationen dazu, wie das Supportpersonal ein Problem diagnostiziert hat, sollten aufgezeichnet und in Zukunft verwendet werden, um eine unnötige Wiederholung der abgeschlossenen Arbeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="46368-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="46368-111">System Problembehandlungsprozess</span><span class="sxs-lookup"><span data-stu-id="46368-111">System troubleshooting process</span></span>

<span data-ttu-id="46368-112">Das folgende Diagramm zeigt den Systemproblem Behandlungsprozess und die Interaktionen mit anderen Vorgangs Rollen.</span><span class="sxs-lookup"><span data-stu-id="46368-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="46368-113">**System Problembehandlung-Flussdiagramm**</span><span class="sxs-lookup"><span data-stu-id="46368-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="46368-114">![System Problembehandlung-Flussdiagramm] (images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Problembehandlung-Flussdiagramm")</span><span class="sxs-lookup"><span data-stu-id="46368-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="46368-115">**Klassifizieren und priorisieren**   diese Aufgabe wird in der Regel vom Service Desk ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="46368-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="46368-116">Beispielsweise kann ein Problem als Softwareproblem oder Hardwareproblem gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="46368-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="46368-117">Das Problem wird dann zur Untersuchung an das geeignete Support Team weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="46368-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="46368-118">Die Regeln für die Bestimmung der Priorität eines Problems sowie die Zeit für die Antwort und die Zeit zum beheben werden in der Regel in der SLA definiert.</span><span class="sxs-lookup"><span data-stu-id="46368-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="46368-119">**Untersuchen und diagnostizieren**   des entsprechenden Support Teams, das das Problem diagnostiziert, und schlägt Änderungen vor, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="46368-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="46368-120">Wenn die Lösung einfach ist und keine Änderungssteuerung erforderlich ist, kann die Lösung sofort angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="46368-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="46368-121">Wenn es sich nicht um eine einfache Lösung handelt, sollte ein Änderungsantrag gestellt und die vorgeschlagene Arbeit vom Change Management-Prozess verwaltet werden, häufig unter einem "Fast-Tracking"-Verfahren.</span><span class="sxs-lookup"><span data-stu-id="46368-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="46368-122">Alle vorgenommenen Änderungen sollten mithilfe des Konfigurationsverwaltungsprozesses aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="46368-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="46368-123">**Schließen und aufzeichnen**   nachdem Sie die Lösung getestet haben, sollte das Problem geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="46368-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="46368-124">Wenn es Lektionen gibt, die aus dem Problem zu lernen sind, sollte ein Eintrag in der Knowledge Base erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="46368-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="46368-125">**Überprüfungs-und Trend Analyse**   regelmäßige Reviews zu aktuellen Problemen sollten durchgeführt werden, um Problem Trends zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="46368-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="46368-126">Wenn die Benutzer beispielsweise häufig Probleme mit langsamen Anmeldungen an Ihren lync-Websites haben, kann dies zu Problemen mit der Netzwerkbandbreite führen.</span><span class="sxs-lookup"><span data-stu-id="46368-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="46368-127">Die Problem Behebungszeiten und die Auswirkungen etwaiger Ausfälle auf die Systemverfügbarkeit sollten überprüft und mit der SLA verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="46368-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="46368-128">Die Person, die mit dem Kunden bei Dienstproblemen unterhält, beispielsweise ein Kontomanager, sollte über wichtige Probleme informiert werden.</span><span class="sxs-lookup"><span data-stu-id="46368-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="46368-129">Problemverwaltungstools</span><span class="sxs-lookup"><span data-stu-id="46368-129">Issue management tools</span></span>

<span data-ttu-id="46368-130">Mit Service Desk-Tools können Mitarbeiter neue Probleme aufzeichnen, klassifizieren und priorisieren.</span><span class="sxs-lookup"><span data-stu-id="46368-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="46368-131">Die Tools stellen dann die Workflowprozesse bereit, um die Problem Dienstanforderung durch Untersuchung und Diagnose zu verwalten, häufig von mehr als einem Support Team.</span><span class="sxs-lookup"><span data-stu-id="46368-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="46368-132">Tools, die häufig Berichte zu auflösungszeiten und Verlaufstrends bereitstellen, können auch eine Knowledge Base-Datenbank enthalten, die zum Durchsuchen vergangener Probleme verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="46368-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="46368-133">Die Microsoft Knowledge Base ist eine nützliche Aufzeichnung von Supportproblemen, die von Microsoft aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="46368-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="46368-134">Weitere Informationen finden Sie auf der Microsoft-Support Website<http://go.microsoft.com/fwlink/?linkid=14898>().</span><span class="sxs-lookup"><span data-stu-id="46368-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="46368-135">Für Software von Drittanbietern ist in der Regel eine Anpassung an die Anforderungen der Organisation erforderlich, wie etwa die Organisation von Teams, die Berichterstattungsanforderungen und die erforderlichen Maßnahmen für die SLA.</span><span class="sxs-lookup"><span data-stu-id="46368-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="46368-136">Zentralisierte vs. dezentrale Verwaltung</span><span class="sxs-lookup"><span data-stu-id="46368-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="46368-137">Rollen und Zuständigkeiten für die Durchführung von Systemverwaltungsaufgaben hängen davon ab, ob die Organisation einem zentralisierten Modell, einem dezentralisierten Modell oder einer Kombination aus beiden folgt.</span><span class="sxs-lookup"><span data-stu-id="46368-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="46368-138">**Zentrales Modell**   in einem zentralisierten Modell verwalten eine oder mehrere administrative Gruppen die vollständige Kontrolle über die gesamte lync Server-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="46368-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="46368-139">Dieses Verwaltungsmodell ähnelt einem Rechenzentrum, in dem alle Verwaltungsaufgaben von einer einzigen Informationstechnologiegruppe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46368-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="46368-140">Rollen und Zuständigkeiten innerhalb des Teams sollten nach Erfahrung und Fachwissen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="46368-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="46368-141">**Dezentrale Modelle**   dezentralisierte Organisationen befinden sich an verschiedenen geografischen Standorten und verfügen über funktionierende lync Server-Server und Administratoren Teams an verschiedenen Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="46368-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="46368-142">So können beispielsweise lokale Verwaltungsmitarbeiter und mindestens ein Server, auf dem lync Server 2013 ausgeführt wird, für jedes Land/jede Region vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="46368-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="46368-143">Möglicherweise gibt es einen Serverpool, auf dem lync Server 2013 und ein Verwaltungsteam für Nordamerika und eines für Europa ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46368-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="46368-144">Manchmal möchten Sie möglicherweise, dass Administratoren nur für Ihren eigenen geografischen Bereich verantwortlich sind und Berechtigungen zum Verwalten von Ressourcen in anderen Bereichen einschränken.</span><span class="sxs-lookup"><span data-stu-id="46368-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="46368-145">Mit lync Server können Sie auch bestimmte administrative Aufgaben mithilfe der rollenbasierten Zugriffssteuerung an bestimmte Personen oder Gruppen delegieren.</span><span class="sxs-lookup"><span data-stu-id="46368-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="46368-146">Mit RBAC können Administratoren bestimmte Benutzerrechte und Berechtigungen an andere Administratoren delegieren, um eine Teilmenge der möglichen administrativen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="46368-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="46368-147">Durch die Verwendung von RBAC hängt die Fähigkeit des Benutzers, bestimmte administrative Aufgaben auszuführen, von den Rollen ab, die dem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="46368-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="46368-148">RBAC bietet eine Liste der Cmdlets, die der Benutzer basierend auf den RBAC-Rollen ausführen kann, in denen der Benutzer Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="46368-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

