---
title: 'Lync Server 2013: Bereitstellungsprozess für die Gruppenanruf Abholung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="ba142-102">Bereitstellungsprozess für die Gruppenanruf Abholung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba142-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba142-103">_**Letztes Änderungsdatum des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ba142-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ba142-104">Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen von Gruppenanruf Pickups erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ba142-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="ba142-105">Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie die Gruppenanruf Abholung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ba142-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="ba142-106">Die für die Gruppenanruf Abholung erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ba142-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="ba142-107">Bereitstellungsprozess für die Gruppenanrufannahme</span><span class="sxs-lookup"><span data-stu-id="ba142-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba142-108">Phase</span><span class="sxs-lookup"><span data-stu-id="ba142-108">Phase</span></span></th>
<th><span data-ttu-id="ba142-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="ba142-109">Steps</span></span></th>
<th><span data-ttu-id="ba142-110">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="ba142-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ba142-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ba142-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba142-112">Aktivieren des SEFAUtil Resource Kit-Tools in der Topologie</span><span class="sxs-lookup"><span data-stu-id="ba142-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ba142-113">Erstellen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplicationPool</strong> einen neuen vertrauenswürdigen Anwendungspool.</span><span class="sxs-lookup"><span data-stu-id="ba142-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="ba142-114">Legen Sie mithilfe des Cmdlets <strong>New-CsTrustedApplication</strong> das SEFAUtil-Tool als vertrauenswürdige Anwendung fest.</span><span class="sxs-lookup"><span data-stu-id="ba142-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="ba142-115">Führen Sie das Cmdlet <strong>Enable-CsTopology</strong> aus, um die Topologie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ba142-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="ba142-116">Installieren Sie die Resource Kit-Tools auf einem Front-End-Server, der sich im vertrauenswürdigen Anwendungspool befindet, der in Schritt 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba142-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="ba142-117">Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba142-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ba142-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba142-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba142-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba142-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba142-120">Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="ba142-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="ba142-121">Verwenden Sie das Cmdlet <strong>New-CSCallParkOrbit</strong> , um die Nummernbereiche für die Anruf Abholung in der Umlaufbahn Tabelle des Anrufs zu erstellen, und weisen Sie den Anruf-abholbereich den Typ GroupPickup zu.</span><span class="sxs-lookup"><span data-stu-id="ba142-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ba142-122">Sie müssen die lync Server-Verwaltungsshell zum Erstellen, ändern, entfernen und Anzeigen von Gruppenanruf-Pickup-Nummernbereichen in der Orbit-Tabelle des Anruf Parks verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba142-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="ba142-123">Gruppenanruf-Abhol Nummernbereiche sind in der lync Server-Systemsteuerung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba142-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="ba142-p103">Um eine nahtlose Integration in vorhandene Wählpläne zu ermöglichen, sind Nummernbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID (Direct Inward Dialing)-Nummern als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba142-p103">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="ba142-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba142-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ba142-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba142-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ba142-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba142-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ba142-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba142-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba142-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Konfigurieren von Gruppennummern für die Anruf Abholung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba142-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba142-131">Zuweisen einer Anruf-Abholnummer zu Benutzern und Aktivieren der Gruppenanruf Abholung für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="ba142-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="ba142-132">Verwenden Sie den/enablegrouppickup-Parameter im SEFAUtil Resource Kit-Tool, um die Gruppenanruf Abholung zu aktivieren und Benutzern eine Anruf-Abholnummer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ba142-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ba142-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Aktivieren der Gruppenanruf Abholung für Benutzer in lync Server 2013 und Zuweisen einer Gruppennummer</a></span><span class="sxs-lookup"><span data-stu-id="ba142-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba142-134">Informieren der Benutzer über die ihnen zugewiesene Nummer für die Anrufannahme und weitere relevante Nummern</span><span class="sxs-lookup"><span data-stu-id="ba142-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="ba142-135">Da Benutzer einen Anruf an einen Gruppenanruf-Pickup-Benutzer abrufen können, möchten Sie möglicherweise mehr als eine Gruppe überwachen.</span><span class="sxs-lookup"><span data-stu-id="ba142-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ba142-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Übermitteln von Gruppenanruf-Abholaufträgen an Benutzer in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba142-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba142-137">Überprüfen der Bereitstellung Ihrer Gruppenanruf Abholung</span><span class="sxs-lookup"><span data-stu-id="ba142-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="ba142-138">Testen Sie Anrufe und das Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ba142-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ba142-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional Überprüfen der Bereitstellung für die Gruppenanruf Abholung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba142-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

