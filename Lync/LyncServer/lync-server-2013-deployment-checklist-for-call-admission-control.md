---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung'
description: 'Lync Server 2013: Prüfliste für die Bereitstellung der Anrufsteuerung.'
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
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557691"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="060dd-103">Prüfliste für die Bereitstellung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="060dd-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="060dd-104">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="060dd-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="060dd-105">Für eine effektive Planung der Anrufsteuerung müssen die folgenden Aspekte berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="060dd-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="060dd-106">Voraussetzungen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="060dd-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="060dd-107">Erforderliche Informationen für die Anrufsteuerung und erforderliche Entscheidungen zur Konfiguration, bevor Sie mit der Bereitstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="060dd-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="060dd-108">Voraussetzungen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="060dd-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="060dd-109">Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie Ihre lync Server 2013 internen Server bereits bereitgestellt haben, einschließlich einer Front-End-Pool oder einer Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="060dd-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="060dd-110">Erforderliche Informationen für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="060dd-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="060dd-111">In der folgenden Tabelle sind die erforderlichen Informationen für die Bereitstellung der Anrufsteuerung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="060dd-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="060dd-112">Erforderliche Informationen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="060dd-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="060dd-113">Informationen</span><span class="sxs-lookup"><span data-stu-id="060dd-113">Information</span></span></th>
<th><span data-ttu-id="060dd-114">Zusammenfassung der erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="060dd-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="060dd-115">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="060dd-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="060dd-116">Lync Server von Ihrer Organisation benötigten Funktionen</span><span class="sxs-lookup"><span data-stu-id="060dd-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-117">Funktionen, die von Ihrer Organisation unterstützt werden sollen</span><span class="sxs-lookup"><span data-stu-id="060dd-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="060dd-118">Funktionen, die für einzelne Benutzer aktiviert werden sollen</span><span class="sxs-lookup"><span data-stu-id="060dd-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060dd-120">Topologien und Komponenten, die bereitgestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="060dd-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-121">Zugehörige Komponenten im Zusammenhang mit der Anrufsteuerung werden automatisch im Rahmen von lync Server 2013 installiert</span><span class="sxs-lookup"><span data-stu-id="060dd-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060dd-123">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="060dd-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-124">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="060dd-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="060dd-125">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="060dd-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="060dd-126">Anforderungen für die gemeinsame Ausführung</span><span class="sxs-lookup"><span data-stu-id="060dd-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-127"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060dd-128">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="060dd-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-129">Für die Anrufsteuerung liegen keine besonderen Infrastrukturanforderungen vor</span><span class="sxs-lookup"><span data-stu-id="060dd-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastrukturanforderungen für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060dd-131">Netzwerkschnittstellenanforderungen</span><span class="sxs-lookup"><span data-stu-id="060dd-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-132">Informationen zu internen und externen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="060dd-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="060dd-133">Routing Informationen (einschließlich Informationen im NextHop-Blog unter <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , Microsoft lync Server Team Kundenantwort Kanal)</span><span class="sxs-lookup"><span data-stu-id="060dd-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-134"><a href="lync-server-2013-deploying-external-user-access.md">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060dd-135">Bereitstellungsstrategie</span><span class="sxs-lookup"><span data-stu-id="060dd-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-136">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="060dd-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="060dd-137">Arbeitsgruppe oder Domäne</span><span class="sxs-lookup"><span data-stu-id="060dd-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="060dd-138">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="060dd-138">Security</span></span></p></li>
<li><p><span data-ttu-id="060dd-139">Überwachung und Prüfung</span><span class="sxs-lookup"><span data-stu-id="060dd-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="060dd-140">Überlegungen zur Hardware</span><span class="sxs-lookup"><span data-stu-id="060dd-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Bewährte Methoden für die Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060dd-142">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="060dd-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="060dd-143">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="060dd-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="060dd-144">Erforderliche Informationen</span><span class="sxs-lookup"><span data-stu-id="060dd-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="060dd-145">Prozess und Verfahren</span><span class="sxs-lookup"><span data-stu-id="060dd-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="060dd-146"><a href="lync-server-2013-configure-call-admission-control.md">Konfigurieren der Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060dd-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

