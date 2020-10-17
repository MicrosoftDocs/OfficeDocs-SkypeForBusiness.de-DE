---
title: Prüfliste für lync Server 2013 Bereitstellung für A/V-Konferenzen
description: Lync Server 2013-Bereitstellungsprüfliste für A/V-Konferenzen.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557771"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="b986c-103">Prüfliste für die Bereitstellung von A/V-Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b986c-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b986c-104">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b986c-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b986c-105">Wie bei der Bereitstellung Ihrer anderen lync Server 2013 Komponenten erfordert die Bereitstellung von a/V-Konferenzen die Verwendung des Topologie-Generators zum Erstellen und Veröffentlichen einer Topologie, in der Konferenzen integriert sind.</span><span class="sxs-lookup"><span data-stu-id="b986c-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="b986c-106">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="b986c-106">Deployment Sequence</span></span>

<span data-ttu-id="b986c-107">Sie können Konferenzen gleichzeitig bereitstellen, wenn Sie die anfängliche Topologie bereitstellen oder nachdem Sie mindestens eine Front-End-Pool oder Standard Edition-Server bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="b986c-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="b986c-108">Bereitstellungsverfahren für Konferenzen</span><span class="sxs-lookup"><span data-stu-id="b986c-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="b986c-109">Die folgende Tabelle bietet einen Überblick über die erforderlichen Schritte zur Bereitstellung von Konferenzen in einer vorhandenen Topologie.</span><span class="sxs-lookup"><span data-stu-id="b986c-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b986c-110">Phase</span><span class="sxs-lookup"><span data-stu-id="b986c-110">Phase</span></span></th>
<th><span data-ttu-id="b986c-111">Schritte</span><span class="sxs-lookup"><span data-stu-id="b986c-111">Steps</span></span></th>
<th><span data-ttu-id="b986c-112">Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="b986c-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="b986c-113">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="b986c-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b986c-114"><strong>Installieren der erforderlichen Hardware und Software</strong></span><span class="sxs-lookup"><span data-stu-id="b986c-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="b986c-115">Konferenzen werden auf Front-End-Servern einer Front-End-Pool-und Standard Edition-Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b986c-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="b986c-116">Es bestehen keine zusätzlichen Hardware- oder Softwareanforderungen, die die Installationsanforderungen für diese Server übersteigen.</span><span class="sxs-lookup"><span data-stu-id="b986c-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b986c-117">Lync Server 2013 verwendet Office-Webanwendungen und den Office-webapps-Server, um die Freigabe und das Rendern von PowerPoint-Präsentationen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b986c-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="b986c-118">Ausführliche Informationen zum Installieren und Konfigurieren des Office-webapps-Servers finden Sie unter <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office-webapps Server und lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b986c-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="b986c-119">Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</span><span class="sxs-lookup"><span data-stu-id="b986c-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="b986c-120"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="b986c-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="b986c-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="b986c-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="b986c-122"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b986c-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="b986c-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Voraussetzungen für die Archivierung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b986c-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b986c-124"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung von Konferenzen</strong></span><span class="sxs-lookup"><span data-stu-id="b986c-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="b986c-125">Führen Sie den Topologie-Generator aus, um der Topologie Konferenzen hinzuzufügen, und veröffentlichen Sie dann die Topologie.</span><span class="sxs-lookup"><span data-stu-id="b986c-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="b986c-126">Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</span><span class="sxs-lookup"><span data-stu-id="b986c-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="b986c-127">So veröffentlichen Sie die Topologie, ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist und die über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die Dateifreigabe verfügt, die für den lync Server 2013 Dateispeicher verwendet werden soll (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</span><span class="sxs-lookup"><span data-stu-id="b986c-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="b986c-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b986c-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b986c-129"><strong>Konfigurieren von Konferenzrichtlinien und -unterstützung</strong></span><span class="sxs-lookup"><span data-stu-id="b986c-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="b986c-130">Verwenden Sie die lync Server 2013-Systemsteuerung oder lync Server-Verwaltungsshell, um Konferenzeinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b986c-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="b986c-131">RTCUniversalServerAdmins-Gruppe (nur Windows PowerShell) oder Zuweisen von Benutzern zur Rolle "[]" oder "CSAdministrator"</span><span class="sxs-lookup"><span data-stu-id="b986c-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="b986c-132"><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in lync Server 2013</a> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b986c-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b986c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b986c-133">See Also</span></span>


[<span data-ttu-id="b986c-134">Übersicht über Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b986c-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="b986c-135">Definieren der Anforderungen für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b986c-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

