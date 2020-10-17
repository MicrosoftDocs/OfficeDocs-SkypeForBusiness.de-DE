---
title: 'Lync Server 2013: Bereitstellungsprozess für die gruppenanrufannahme'
description: 'Lync Server 2013: Bereitstellungsprozess für die Gruppenanruf Abholung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a01409b257c685ae71dfdb13074f2d8ea590cd9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552491"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="306bf-103">Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="306bf-103">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="306bf-104">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="306bf-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="306bf-105">Dieser Abschnitt enthält eine Übersicht über die Schritte zur Bereitstellung der gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="306bf-105">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="306bf-106">Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die gruppenanrufannahme konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="306bf-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="306bf-107">Die für die gruppenanrufannahme erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="306bf-107">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="306bf-108">Bereitstellungsprozess für Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="306bf-108">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="306bf-109">Phase</span><span class="sxs-lookup"><span data-stu-id="306bf-109">Phase</span></span></th>
<th><span data-ttu-id="306bf-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="306bf-110">Steps</span></span></th>
<th><span data-ttu-id="306bf-111">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="306bf-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="306bf-112">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="306bf-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="306bf-113">Aktivieren des SEFAUtil Resource Kit-Tools in der Topologie</span><span class="sxs-lookup"><span data-stu-id="306bf-113">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="306bf-114">Verwenden Sie das Cmdlet <strong>New-CsTrustedApplicationPool</strong> , um einen neuen vertrauenswürdigen Anwendungspool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="306bf-114">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="306bf-115">Verwenden Sie das Cmdlet <strong>New-CsTrustedApplication</strong> , um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="306bf-115">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="306bf-116">Führen Sie das Cmdlet <strong>enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="306bf-116">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="306bf-117">Installieren Sie die Resource Kit-Tools auf einem Front-End-Server im vertrauenswürdigen Anwendungspool, der in Schritt 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="306bf-117">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="306bf-118">Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es zur Anzeige der Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung führen.</span><span class="sxs-lookup"><span data-stu-id="306bf-118">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="306bf-119">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="306bf-119">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="306bf-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Bereitstellen des SEFAUtil-Tools in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="306bf-120"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="306bf-121">Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbit-Tabelle "Parken"</span><span class="sxs-lookup"><span data-stu-id="306bf-121">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="306bf-122">Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong> , um Nummernbereiche für die Anrufannahme in der Orbit-Tabelle für das Parken von Anrufen zu erstellen und den Anruf abholbereichen den Typ GroupPickup zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="306bf-122">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="306bf-123">Sie müssen lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Abhol Nummernbereichen in der Orbit-Tabelle für das Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="306bf-123">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="306bf-124">Gruppenanruf-Pickup-Nummernbereiche sind in lync Server-Systemsteuerung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="306bf-124">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="306bf-125">Für die nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Erweiterungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="306bf-125">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="306bf-126">Das Zuweisen von Durchwahlnummern (DID) als Bereichs Nummern in der Orbit-Tabelle für das Parken von Anrufen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="306bf-126">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="306bf-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="306bf-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="306bf-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="306bf-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="306bf-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="306bf-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="306bf-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="306bf-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="306bf-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Nummern für die Anrufannahme Gruppe in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="306bf-131"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="306bf-132">Zuweisen einer Anruf Abholnummer zu Benutzern und Aktivieren der gruppenanrufannahme für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="306bf-132">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="306bf-133">Verwenden Sie den Parameter/enablegrouppickup im SEFAUtil Resource Kit-Tool, um die gruppenanrufannahme zu aktivieren und eine Anrufannahme Nummer für Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="306bf-133">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="306bf-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</a></span><span class="sxs-lookup"><span data-stu-id="306bf-134"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="306bf-135">Benachrichtigen der Benutzer über die zugewiesene Anruf Abholnummer und andere Interessen</span><span class="sxs-lookup"><span data-stu-id="306bf-135">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="306bf-136">Da ein beliebiger Benutzer einen Anruf an einen Benutzer der gruppenanrufannahme abrufen kann, möchten Benutzer möglicherweise mehrere Gruppen überwachen.</span><span class="sxs-lookup"><span data-stu-id="306bf-136">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="306bf-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Mitteilen von Gruppenanruf-Pickup-Zuweisungen an Benutzer in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="306bf-137"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="306bf-138">Überprüfen der Bereitstellung von Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="306bf-138">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="306bf-139">Testen Sie das platzieren und Abrufen von anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="306bf-139">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="306bf-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Überprüfen der Gruppenanruf-Pickup-Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="306bf-140"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

