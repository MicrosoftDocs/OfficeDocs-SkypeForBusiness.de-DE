---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d68f13c636b24729db989f25da7055333968cbbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7283c-102">Prüfliste für die Bereitstellung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7283c-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7283c-103">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="7283c-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="7283c-104">Für eine effektive Planung der Anrufsteuerung müssen die folgenden Aspekte berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="7283c-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="7283c-105">Voraussetzungen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="7283c-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="7283c-106">Erforderliche Informationen für die Anrufsteuerung und erforderliche Entscheidungen zur Konfiguration, bevor Sie mit der Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="7283c-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="7283c-107">Voraussetzungen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="7283c-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="7283c-108">Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie Ihre lync Server 2013 internen Server bereits bereitgestellt haben, einschließlich einer Front-End-Pool oder einer Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="7283c-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="7283c-109">Erforderliche Informationen für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="7283c-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="7283c-110">In der folgenden Tabelle sind die erforderlichen Informationen für die Bereitstellung der Anrufsteuerung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7283c-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="7283c-111">Erforderliche Informationen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="7283c-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7283c-112">Informationen</span><span class="sxs-lookup"><span data-stu-id="7283c-112">Information</span></span></th>
<th><span data-ttu-id="7283c-113">Zusammenfassung der erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="7283c-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="7283c-114">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="7283c-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7283c-115">Lync Server von Ihrer Organisation benötigten Funktionen</span><span class="sxs-lookup"><span data-stu-id="7283c-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-116">Funktionen, die von Ihrer Organisation unterstützt werden sollen</span><span class="sxs-lookup"><span data-stu-id="7283c-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="7283c-117">Funktionen, die für einzelne Benutzer aktiviert werden sollen</span><span class="sxs-lookup"><span data-stu-id="7283c-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7283c-119">Topologien und Komponenten, die bereitgestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="7283c-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-120">Zugehörige Komponenten im Zusammenhang mit der Anrufsteuerung werden automatisch im Rahmen von lync Server 2013 installiert</span><span class="sxs-lookup"><span data-stu-id="7283c-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7283c-122">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="7283c-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-123">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="7283c-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="7283c-124">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="7283c-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="7283c-125">Anforderungen für die gemeinsame Ausführung</span><span class="sxs-lookup"><span data-stu-id="7283c-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-126"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7283c-127">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="7283c-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-128">Für die Anrufsteuerung liegen keine besonderen Infrastrukturanforderungen vor</span><span class="sxs-lookup"><span data-stu-id="7283c-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastrukturanforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7283c-130">Netzwerkschnittstellenanforderungen</span><span class="sxs-lookup"><span data-stu-id="7283c-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-131">Informationen zu internen und externen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7283c-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="7283c-132">Routing Informationen (einschließlich Informationen im NextHop-Blog unter <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft lync Server Team Kundenantwort Kanal)</span><span class="sxs-lookup"><span data-stu-id="7283c-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-133"><a href="lync-server-2013-deploying-external-user-access.md">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7283c-134">Bereitstellungsstrategie</span><span class="sxs-lookup"><span data-stu-id="7283c-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-135">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="7283c-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="7283c-136">Arbeitsgruppe oder Domäne</span><span class="sxs-lookup"><span data-stu-id="7283c-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="7283c-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7283c-137">Security</span></span></p></li>
<li><p><span data-ttu-id="7283c-138">Überwachung und Prüfung</span><span class="sxs-lookup"><span data-stu-id="7283c-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="7283c-139">Überlegungen zur Hardware</span><span class="sxs-lookup"><span data-stu-id="7283c-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Bewährte Methoden für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7283c-141">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="7283c-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7283c-142">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7283c-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="7283c-143">Erforderliche Informationen</span><span class="sxs-lookup"><span data-stu-id="7283c-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="7283c-144">Prozess und Verfahren</span><span class="sxs-lookup"><span data-stu-id="7283c-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7283c-145"><a href="lync-server-2013-configure-call-admission-control.md">Konfigurieren der Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7283c-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

