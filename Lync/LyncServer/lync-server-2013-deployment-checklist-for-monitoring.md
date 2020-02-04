---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71b7d69054df266139f3f13ca0ca53e1803f44b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="6454f-102">Prüfliste zur Bereitstellung für die Überwachung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6454f-102">Deployment checklist for monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6454f-103">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="6454f-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="6454f-104">Obwohl die Überwachung auf jedem Front-End-Server bereits installiert und aktiviert ist, müssen Sie noch einige Schritte Unternehmen, bevor Sie tatsächlich Überwachungsdaten für Microsoft lync Server 2013 erfassen können.</span><span class="sxs-lookup"><span data-stu-id="6454f-104">Although monitoring is already installed and activated on each Front End server, there are still several steps that you must undertake before you can actually being to collect monitoring data for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6454f-105">Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6454f-105">These steps are outlined in the following checklist:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6454f-106">Phase</span><span class="sxs-lookup"><span data-stu-id="6454f-106">Phase</span></span></p></td>
<td><p><span data-ttu-id="6454f-107">Schritte</span><span class="sxs-lookup"><span data-stu-id="6454f-107">Steps</span></span></p></td>
<td><p><span data-ttu-id="6454f-108">Rolle und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="6454f-108">Role and group membership</span></span></p></td>
<td><p><span data-ttu-id="6454f-109">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6454f-109">Documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6454f-110"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="6454f-110"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6454f-111">Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.</span><span class="sxs-lookup"><span data-stu-id="6454f-111">Install a supported version of Microsoft SQL Server on the computer that will act as the backend data store for monitoring.</span></span></p></td>
<td><p><span data-ttu-id="6454f-112">Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6454f-112">Domain user who is also a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="6454f-113"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> im Supporthandbuch</span><span class="sxs-lookup"><span data-stu-id="6454f-113"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability guide</span></span></p>
<p><span data-ttu-id="6454f-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Unterstützung von Server Software und-Infrastruktur in lync Server 2013</a> im Supporthandbuch</span><span class="sxs-lookup"><span data-stu-id="6454f-114"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability Guide</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6454f-115"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Überwachung</strong></span><span class="sxs-lookup"><span data-stu-id="6454f-115"><strong>Create the appropriate internal topology to support monitoring</strong></span></span></p></td>
<td><p><span data-ttu-id="6454f-116">Verwenden Sie den lync Server 2013-Topologie-Generator, um der Topologie Überwachungsdatenbanken hinzuzufügen, und veröffentlichen Sie dann die aktualisierte Topologie.</span><span class="sxs-lookup"><span data-stu-id="6454f-116">Use Lync Server 2013 Topology Builder to add monitoring databases to the topology, then published the updated topology.</span></span></p></td>
<td><p><span data-ttu-id="6454f-117">Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6454f-117">To define a topology, a user who is a member of the local users group.</span></span></p>
<p><span data-ttu-id="6454f-118">Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6454f-118">To publish the topology, a user who is a member if the domain administrators group and the RTCUniversalServerAdmins group.</span></span></p></td>
<td><p><span data-ttu-id="6454f-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013</a> im Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="6454f-119"><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Associating a monitoring store with a Front End pool in Lync Server 2013</a> in the Deployment guide</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6454f-120"><strong>Aktivieren der entsprechenden Überwachungseinstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="6454f-120"><strong>Enable the appropriate monitoring settings</strong></span></span></p></td>
<td><p><span data-ttu-id="6454f-121">Aktivieren Sie die Anrufdetailaufzeichnung (CDR) und/oder die QoE-Überwachung (Quality of Experience) auf den globalen und/oder den Website Bereichen.</span><span class="sxs-lookup"><span data-stu-id="6454f-121">Enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global and/or the site scopes.</span></span></p></td>
<td><p><span data-ttu-id="6454f-122">Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6454f-122">A user who is a member of the RTCUniversalServerAdmins group or who has been assigned an RBAC role that provides access to the CsCdrConfiguration and CsQoEConfiguration cmdlets.</span></span></p></td>
<td><p><span data-ttu-id="6454f-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Konfigurieren der Einstellungen für die Anrufdetailaufzeichnung und die Qualität der Benutzerfreundlichkeit in lync Server 2013</a> im Betriebshandbuch</span><span class="sxs-lookup"><span data-stu-id="6454f-123"><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</a> in the Operations guide</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

