---
title: 'Lync Server 2013: System Administration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c830b689f0f55c2af191443583394e9f8c22eed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497502"
---
# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="37a43-102">System Verwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37a43-102">System administration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a43-103">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="37a43-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="37a43-104">Die System Administration umfasst die täglichen administrativen Aufgaben, sowohl geplant als auch bedarfsgesteuert, die erforderlich sind, damit ein IT-System reibungslos funktioniert.</span><span class="sxs-lookup"><span data-stu-id="37a43-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="37a43-105">In der Regel werden Systemverwaltungsaufgaben in schriftlichen Verfahren behandelt.</span><span class="sxs-lookup"><span data-stu-id="37a43-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="37a43-106">Mithilfe dieser Verfahren wird sichergestellt, dass alle Supportmitarbeiter dieselben Standardtools und-Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="37a43-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="37a43-107">In einer lync-Umgebung umfassen die typischen Systemverwaltungsaufgaben das Sichern und Archivieren von Pools, das Überwachen von Protokollen, das Erstellen und Verwalten von Benutzern und das Aktualisieren von Antivirensoftware.</span><span class="sxs-lookup"><span data-stu-id="37a43-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="37a43-108">System Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="37a43-108">System troubleshooting</span></span>

<span data-ttu-id="37a43-109">Eine Organisation muss bereit sein, mit unerwarteten Problemen fertig zu werden, und Sie sollte über ein Verfahren zum Verwalten von Problemen von dem Zeitpunkt an verfügen, an dem Sie bis zu Ihrer Lösung gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="37a43-110">Informationen darüber, wie Supportmitarbeiter ein Problem diagnostiziert haben, sollten aufgezeichnet und in Zukunft verwendet werden, um zu vermeiden, dass die abgeschlossene Arbeit unnötig wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="37a43-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="37a43-111">System Problembehandlungsprozess</span><span class="sxs-lookup"><span data-stu-id="37a43-111">System troubleshooting process</span></span>

<span data-ttu-id="37a43-112">Das folgende Diagramm zeigt den Systemproblem Behandlungsprozess und die Interaktionen mit anderen Betriebs Rollen.</span><span class="sxs-lookup"><span data-stu-id="37a43-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="37a43-113">**Flussdiagramm zur System Problembehandlung**</span><span class="sxs-lookup"><span data-stu-id="37a43-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="37a43-114">![Flussdiagramm zur System Problembehandlung](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Flussdiagramm zur System Problembehandlung")</span><span class="sxs-lookup"><span data-stu-id="37a43-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="37a43-115">**Klassifizieren und priorisieren**     Diese Aufgabe wird in der Regel vom Service Desk ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="37a43-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="37a43-116">Beispielsweise kann ein Problem als Softwareproblem oder Hardwareproblem gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="37a43-117">Das Problem wird dann zur Untersuchung an das entsprechende Support Team weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="37a43-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="37a43-118">Die Regeln für die Bestimmung der Priorität eines Problems sowie die Reaktionszeit und die Auflösungszeit sind in der Regel in der SLA definiert.</span><span class="sxs-lookup"><span data-stu-id="37a43-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="37a43-119">**Untersuchen und diagnostizieren**     Das entsprechende Support Team diagnostiziert das Problem und schlägt Änderungen vor, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="37a43-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="37a43-120">Wenn die Lösung einfach ist und keine Änderungssteuerung erfordert, kann die Lösung sofort angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="37a43-121">Wenn die Lösung nicht einfach ist, sollte eine Änderungsanforderung ausgelöst werden, und die vorgeschlagene Arbeit sollte durch den Change Management-Prozess verwaltet werden, häufig unter einem "Fast-Track"-Verfahren.</span><span class="sxs-lookup"><span data-stu-id="37a43-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="37a43-122">Alle vorgenommenen Änderungen sollten mit dem Konfigurationsverwaltungsprozess aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="37a43-123">**Schließen und aufzeichnen**     Nach dem Testen der Lösung sollte das Problem geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="37a43-124">Wenn aus dem Problem Lektionen gelernt werden müssen, sollte ein Eintrag in der Knowledge Base erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="37a43-125">**Überprüfung und Trend Analyse**     Regelmäßige Überprüfungen der aktuellen Probleme sollten durchgeführt werden, um Problem Trends zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="37a43-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="37a43-126">Wenn die Benutzer beispielsweise häufig Probleme mit langsamen Anmeldungen an Ihren lync-Websites auftreten, können Probleme mit der Netzwerkbandbreite verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="37a43-127">Die Problem Behebungszeiten und die Auswirkungen von Ausfällen auf die Systemverfügbarkeit sollten überprüft und mit der SLA verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="37a43-128">Die Person, die mit dem Kunden bei Dienstproblemen kontaktiert, wie beispielsweise ein Account Manager, sollte über wichtige Probleme informiert werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="37a43-129">Problemverwaltungstools</span><span class="sxs-lookup"><span data-stu-id="37a43-129">Issue management tools</span></span>

<span data-ttu-id="37a43-130">Service Desk-Tools ermöglichen es Mitarbeitern, neue Probleme aufzuzeichnen, zu klassifizieren und zu priorisieren.</span><span class="sxs-lookup"><span data-stu-id="37a43-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="37a43-131">Tools stellt dann die Workflowprozesse zur Verwaltung der Problem Dienstanforderung durch Untersuchung und Diagnose bereit, häufig von mehr als einem Support Team.</span><span class="sxs-lookup"><span data-stu-id="37a43-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="37a43-132">Tools, die häufig Berichte über Lösungszeiten und Verlaufstrends bereitstellen, können auch eine Knowledge Base-Datenbank enthalten, die zum Durchsuchen früherer Probleme verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="37a43-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="37a43-133">Die Microsoft Knowledge Base ist eine nützliche Aufzeichnung von Supportproblemen, die von Microsoft aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="37a43-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="37a43-134">Weitere Informationen finden Sie auf der Microsoft-Support-Website ( <https://go.microsoft.com/fwlink/?linkid=14898> ).</span><span class="sxs-lookup"><span data-stu-id="37a43-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="37a43-135">Bei Drittanbietersoftware ist in der Regel eine Anpassung erforderlich, die den Anforderungen der Organisation entspricht, beispielsweise die Organisation von Teams, Berichtsanforderungen und für die SLA erforderlichen Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="37a43-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="37a43-136">Zentralisierte vs. dezentrale Verwaltung</span><span class="sxs-lookup"><span data-stu-id="37a43-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="37a43-137">Rollen und Verantwortlichkeiten für die Ausführung von Systemverwaltungsaufgaben hängen davon ab, ob die Organisation einem zentralisierten Modell, einem dezentralisierten Modell oder einer Kombination aus beiden folgt.</span><span class="sxs-lookup"><span data-stu-id="37a43-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="37a43-138">**Zentrales Modell**     In einem zentralisierten Modell behalten eine oder mehrere administrative Gruppen die vollständige Kontrolle über die gesamte lync Server Umgebung bei.</span><span class="sxs-lookup"><span data-stu-id="37a43-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="37a43-139">Dieses Verwaltungsmodell ähnelt einem Rechenzentrum, in dem alle Verwaltungsaufgaben von einer einzigen Informationstechnologiegruppe ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="37a43-140">Die Funktionen und Verantwortlichkeiten innerhalb des Teams sollten gemäß der Erfahrung und der Kenntnisse definiert werden.</span><span class="sxs-lookup"><span data-stu-id="37a43-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="37a43-141">**Dezentralisiertes Modell**     Dezentrale Organisationen befinden sich an mehreren geografischen Standorten und funktionieren lync Server Server und Administratoren Teams an unterschiedlichen Standorten.</span><span class="sxs-lookup"><span data-stu-id="37a43-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="37a43-142">Beispielsweise kann es lokale Verwaltungsmitarbeiter und einen oder mehrere Server geben, auf denen lync Server 2013 für jedes Land/dieselbe Region laufen.</span><span class="sxs-lookup"><span data-stu-id="37a43-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="37a43-143">Oder es kann ein Serverpool mit lync Server 2013 und ein Verwaltungsteam für Nordamerika und eins für Europa geben.</span><span class="sxs-lookup"><span data-stu-id="37a43-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="37a43-144">Möglicherweise möchten Sie, dass Administratoren nur für Ihren eigenen geografischen Bereich zuständig sind und Berechtigungen zum Verwalten von Ressourcen in anderen Bereichen einschränken.</span><span class="sxs-lookup"><span data-stu-id="37a43-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="37a43-145">Mit lync Server können Sie auch bestimmte administrative Aufgaben mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) an bestimmte Personen oder Gruppen delegieren.</span><span class="sxs-lookup"><span data-stu-id="37a43-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="37a43-146">Mit RBAC können Administratoren bestimmte Benutzerrechte und-Berechtigungen an andere Administratoren delegieren, um eine Teilmenge der möglichen administrativen Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="37a43-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="37a43-147">Durch die Verwendung von RBAC hängt die Fähigkeit des Benutzers, bestimmte administrative Aufgaben auszuführen, von den dem Benutzer zugewiesenen RBAC-Rollen ab.</span><span class="sxs-lookup"><span data-stu-id="37a43-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="37a43-148">RBAC enthält eine Liste der Cmdlets, die der Benutzer basierend auf den RBAC-Rollen ausführen kann, bei denen der Benutzer Mitglied ist.</span><span class="sxs-lookup"><span data-stu-id="37a43-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

