---
title: 'Lync Server 2013: Bereitstellungsprozess für die gruppenanrufannahme'
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
ms.openlocfilehash: 150434b57aa90048c1009851473349093435c116
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="9a05e-102">Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a05e-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a05e-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="9a05e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="9a05e-104">Dieser Abschnitt enthält eine Übersicht über die Schritte zur Bereitstellung der gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="9a05e-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="9a05e-105">Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die gruppenanrufannahme konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9a05e-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="9a05e-106">Die für die gruppenanrufannahme erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9a05e-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="9a05e-107">Bereitstellungsprozess für Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="9a05e-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a05e-108">Phase</span><span class="sxs-lookup"><span data-stu-id="9a05e-108">Phase</span></span></th>
<th><span data-ttu-id="9a05e-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="9a05e-109">Steps</span></span></th>
<th><span data-ttu-id="9a05e-110">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="9a05e-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="9a05e-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="9a05e-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a05e-112">Aktivieren des SEFAUtil Resource Kit-Tools in der Topologie</span><span class="sxs-lookup"><span data-stu-id="9a05e-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="9a05e-113">Verwenden Sie das Cmdlet <strong>New-CsTrustedApplicationPool</strong> , um einen neuen vertrauenswürdigen Anwendungspool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9a05e-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="9a05e-114">Verwenden Sie das Cmdlet <strong>New-CsTrustedApplication</strong> , um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9a05e-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="9a05e-115">Führen Sie das Cmdlet <strong>enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9a05e-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="9a05e-116">Installieren Sie die Resource Kit-Tools auf einem Front-End-Server im vertrauenswürdigen Anwendungspool, der in Schritt 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9a05e-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="9a05e-117">Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es zur Anzeige der Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung führen.</span><span class="sxs-lookup"><span data-stu-id="9a05e-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="9a05e-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9a05e-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9a05e-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Bereitstellen des SEFAUtil-Tools in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9a05e-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a05e-120">Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbit-Tabelle "Parken"</span><span class="sxs-lookup"><span data-stu-id="9a05e-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="9a05e-121">Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong> , um Nummernbereiche für die Anrufannahme in der Orbit-Tabelle für das Parken von Anrufen zu erstellen und den Anruf abholbereichen den Typ GroupPickup zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9a05e-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9a05e-122">Sie müssen lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Abhol Nummernbereichen in der Orbit-Tabelle für das Parken von Anrufen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a05e-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="9a05e-123">Gruppenanruf-Pickup-Nummernbereiche sind in lync Server-Systemsteuerung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9a05e-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="9a05e-124">Für die nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Erweiterungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9a05e-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="9a05e-125">Das Zuweisen von Durchwahlnummern (DID) als Bereichs Nummern in der Orbit-Tabelle für das Parken von Anrufen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9a05e-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="9a05e-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9a05e-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9a05e-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="9a05e-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="9a05e-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9a05e-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="9a05e-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9a05e-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="9a05e-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Nummern für die Anrufannahme Gruppe in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9a05e-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a05e-131">Zuweisen einer Anruf Abholnummer zu Benutzern und Aktivieren der gruppenanrufannahme für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="9a05e-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="9a05e-132">Verwenden Sie den Parameter/enablegrouppickup im SEFAUtil Resource Kit-Tool, um die gruppenanrufannahme zu aktivieren und eine Anrufannahme Nummer für Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9a05e-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9a05e-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der gruppenanrufannahme für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</a></span><span class="sxs-lookup"><span data-stu-id="9a05e-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a05e-134">Benachrichtigen der Benutzer über die zugewiesene Anruf Abholnummer und andere Interessen</span><span class="sxs-lookup"><span data-stu-id="9a05e-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="9a05e-135">Da ein beliebiger Benutzer einen Anruf an einen Benutzer der gruppenanrufannahme abrufen kann, möchten Benutzer möglicherweise mehrere Gruppen überwachen.</span><span class="sxs-lookup"><span data-stu-id="9a05e-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9a05e-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Mitteilen von Gruppenanruf-Pickup-Zuweisungen an Benutzer in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9a05e-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a05e-137">Überprüfen der Bereitstellung von Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="9a05e-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="9a05e-138">Testen Sie das platzieren und Abrufen von anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9a05e-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="9a05e-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Überprüfen der Gruppenanruf-Pickup-Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9a05e-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

