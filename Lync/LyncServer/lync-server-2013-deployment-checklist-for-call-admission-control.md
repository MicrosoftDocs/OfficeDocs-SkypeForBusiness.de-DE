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
ms.openlocfilehash: 0bf88529734530e70c4d0536d5337395ff0742d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dda2d-102">Prüfliste für die Bereitstellung der Anrufsteuerung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dda2d-102">Deployment checklist for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dda2d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="dda2d-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="dda2d-104">Damit Sie effektiv für die Anrufsteuerung (CAC) planen können, müssen Sie Folgendes in Frage stellen:</span><span class="sxs-lookup"><span data-stu-id="dda2d-104">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="dda2d-105">Voraussetzungen für die Bereitstellung von CAC.</span><span class="sxs-lookup"><span data-stu-id="dda2d-105">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="dda2d-106">Informationen, die für CAC-und Konfigurationsentscheidungen erforderlich sind, die Sie im Vorfeld der Bereitstellung vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="dda2d-106">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="dda2d-107">Voraussetzungen für die Bereitstellung der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="dda2d-107">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="dda2d-108">Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie Ihre lync Server 2013-internen Server bereits bereitgestellt haben, einschließlich eines Front-End-Pools oder eines Standard Edition-Servers.</span><span class="sxs-lookup"><span data-stu-id="dda2d-108">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="dda2d-109">Informationsanforderungen für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="dda2d-109">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="dda2d-110">In der folgenden Tabelle sind die erforderlichen Informationen für die Bereitstellung der Anrufsteuerung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="dda2d-110">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="dda2d-111">Informationsanforderungen für die Bereitstellung von Anruf Zulassungs Steuerungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-111">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dda2d-112">Informationen</span><span class="sxs-lookup"><span data-stu-id="dda2d-112">Information</span></span></th>
<th><span data-ttu-id="dda2d-113">Zusammenfassung der erforderlichen Informationen</span><span class="sxs-lookup"><span data-stu-id="dda2d-113">Summary of Information Required</span></span></th>
<th><span data-ttu-id="dda2d-114">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="dda2d-114">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dda2d-115">Für Ihre Organisation erforderliche lync Server-Funktionen</span><span class="sxs-lookup"><span data-stu-id="dda2d-115">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-116">Von Ihrer Organisation unterstützte Funktionen</span><span class="sxs-lookup"><span data-stu-id="dda2d-116">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="dda2d-117">Funktionen, die für einzelne Benutzer aktiviert werden können</span><span class="sxs-lookup"><span data-stu-id="dda2d-117">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-118"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda2d-119">Topologien und Komponenten, die bereitgestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="dda2d-119">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-120">Mit CAC verknüpfte Komponenten werden automatisch als Teil von lync Server 2013 installiert</span><span class="sxs-lookup"><span data-stu-id="dda2d-120">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-121"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda2d-122">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-122">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-123">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-123">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="dda2d-124">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-124">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="dda2d-125">Anforderungen für die Übersetzung</span><span class="sxs-lookup"><span data-stu-id="dda2d-125">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-126"><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda2d-127">Infrastrukturanforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-127">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-128">Für CAC sind keine spezifischen Infrastrukturanforderungen erforderlich</span><span class="sxs-lookup"><span data-stu-id="dda2d-128">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastrukturanforderungen für die Anrufsteuerung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-129"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda2d-130">Netzwerkschnittstellen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-130">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-131">Interne und externe Schnittstelleninformationen</span><span class="sxs-lookup"><span data-stu-id="dda2d-131">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="dda2d-132">Routing Informationen (einschließlich Informationen im NextHop-Blog unter <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>dem Kundenantwort Kanal des Microsoft lync Server-Teams)</span><span class="sxs-lookup"><span data-stu-id="dda2d-132">Routing information (including information on the NextHop blog at <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-133"><a href="lync-server-2013-deploying-external-user-access.md">Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-133"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dda2d-134">Bereitstellungsstrategie</span><span class="sxs-lookup"><span data-stu-id="dda2d-134">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-135">Bereitstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="dda2d-135">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="dda2d-136">Arbeitsgruppe oder Domäne</span><span class="sxs-lookup"><span data-stu-id="dda2d-136">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="dda2d-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dda2d-137">Security</span></span></p></li>
<li><p><span data-ttu-id="dda2d-138">Überwachen und überwachen</span><span class="sxs-lookup"><span data-stu-id="dda2d-138">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="dda2d-139">Hardware Überlegungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-139">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Bewährte Methoden für die Anrufsteuerung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-140"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dda2d-141">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="dda2d-141">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dda2d-142">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-142">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="dda2d-143">Informationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="dda2d-143">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="dda2d-144">Verfahren und Verfahren</span><span class="sxs-lookup"><span data-stu-id="dda2d-144">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dda2d-145"><a href="lync-server-2013-configure-call-admission-control.md">Konfigurieren der Anrufsteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dda2d-145"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

