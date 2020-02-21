---
title: 'Lync Server 2013: Bereitstellungsprozess für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6e11f85cb929cdd3dbddcab23caaffcf434f303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="a8ab6-102">Bereitstellungsprozess für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ab6-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8ab6-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="a8ab6-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="a8ab6-104">Dieser Abschnitt enthält eine Übersicht über die Schritte zur Bereitstellung des Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="a8ab6-105">Sie müssen Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie das Parken von anrufen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="a8ab6-106">Die für das Parken von Anrufen erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="a8ab6-107">Bereitstellungsprozess für die Funktion zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="a8ab6-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8ab6-108">Phase</span><span class="sxs-lookup"><span data-stu-id="a8ab6-108">Phase</span></span></th>
<th><span data-ttu-id="a8ab6-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="a8ab6-109">Steps</span></span></th>
<th><span data-ttu-id="a8ab6-110">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="a8ab6-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="a8ab6-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="a8ab6-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8ab6-112">Konfigurieren der Orbitbereiche zum Parken von Anrufen in der Orbittabelle</span><span class="sxs-lookup"><span data-stu-id="a8ab6-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-113">Verwenden Sie lync Server-Systemsteuerung oder das Cmdlet <strong>New-CSCallParkOrbit</strong> , um die Umlaufbahn Bereiche in der Orbit-Tabelle für das Parken von Anrufen zu erstellen und Sie dem Anwendungsdienst zuzuordnen, der die Anwendung zum Parken von Anrufen hostet.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a8ab6-p102">Für eine nahtlose Integration in vorhandene Wähleinstellungen werden Orbitbereiche typischerweise als ein Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="a8ab6-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8ab6-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a8ab6-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Erstellen oder Ändern eines Umlaufbahn Bereichs für das Parken von Anrufen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8ab6-121">Konfigurieren von Einstellungen für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="a8ab6-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-122">Verwenden Sie das Cmdlet " <strong>CsCpsConfiguration</strong> ", um die Einstellungen für das Parken von Anrufen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="a8ab6-123">Es wird empfohlen, die <strong>OnTimeoutURI</strong> -Option so zu konfigurieren, dass das Fallback-Ziel beim Timeout eines geparkten Anrufs verwendet wird. Sie können auch die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a8ab6-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="a8ab6-124">(Optional) <strong>EnableMusicOnHold</strong> zum Aktivieren oder Deaktivieren von Wartemusik.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="a8ab6-125">(Optional) <strong>MaxCallPickupAttempts</strong> zum Festlegen der Anzahl von Rückrufversuchen, die für einen geparkten Anruf beim antwortenden Telefon erfolgen, bevor der Anruf an den Fallback-URI (Uniform Resource Locator) weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="a8ab6-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> zum Festlegen der Zeitspanne, für die ein Anruf geparkt bleibt, bevor ein Rückruf beim antwortenden Telefon erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a8ab6-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8ab6-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a8ab6-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-131"><a href="lync-server-2013-configure-call-park-settings.md">Konfigurieren von Einstellungen für das Parken von Anrufen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8ab6-132">Wartemusik anpassen (optional)</span><span class="sxs-lookup"><span data-stu-id="a8ab6-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-133">Verwenden Sie das <strong>Set-CsCallParkServiceMusicOnHoldFile</strong>-Cmdlet zum Anpassen und Hochladen einer Audiodatei, wenn Sie nicht die standardmäßige Wartemusik verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8ab6-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a8ab6-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Anpassen der Wartemusik für das Parken von Anrufen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8ab6-139">Konfigurieren der VoIP-Richtlinie zum Aktivieren des Anruf Parks für Benutzer</span><span class="sxs-lookup"><span data-stu-id="a8ab6-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-140">Verwenden Sie lync Server-Systemsteuerung oder das Cmdlet " <strong>CSVoicePolicy</strong> " mit der Option " <strong>EnableCallPark</strong> ", um den Anruf Park für Benutzer in der VoIP-Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a8ab6-141">Standardmäßig ist das Parken von Anrufen für alle Benutzer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="a8ab6-142">Wenn Sie mehrere VoIP-Richtlinien verwenden, stellen Sie sicher, dass die Eigenschaft "EnableCallPark" nicht nur für die Standardrichtlinie, sondern für alle VoIP-Richtlinien festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="a8ab6-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8ab6-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a8ab6-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-147"><a href="lync-server-2013-enable-call-park-for-users.md">Parken von Anrufen für Benutzer in lync Server 2013 aktivieren</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8ab6-148">Überprüfen der Normalisierungsregeln für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="a8ab6-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-p104">Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Stellen Sie sicher, dass Ihre Normalisierungsregeln keinen der Orbitbereiche umfassen. Falls erforderlich, erstellen Sie zusätzliche Normalisierungsregeln, um eine Normalisierung von Orbits zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8ab6-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a8ab6-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a8ab6-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8ab6-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Überprüfen der Normalisierungsregeln für das Parken von Anrufen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8ab6-157">Überprüfen der Bereitstellung des Anruf Parks</span><span class="sxs-lookup"><span data-stu-id="a8ab6-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="a8ab6-158">Testen Sie das Parken und Abrufen von anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a8ab6-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="a8ab6-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Optional Überprüfen der Bereitstellung des Anruf Parks in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a8ab6-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

