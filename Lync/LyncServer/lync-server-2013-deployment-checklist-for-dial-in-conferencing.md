---
title: Prüfliste für lync Server 2013-Bereitstellung für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a81a4baee7062936144d0a6d066d59cf0a8ef1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522792"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="67d51-102">Prüfliste für die Bereitstellung von Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67d51-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67d51-103">_**Letztes Änderungsstand des Themas:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="67d51-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="67d51-104">Die für Einwahlkonferenzen erforderlichen Komponenten werden bei der Bereitstellung der Konferenzarbeitsauslastung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="67d51-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="67d51-105">Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder ein Vermittlungsserver und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="67d51-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="67d51-106">Alle Schritte in der folgenden Tabelle müssen durchgeführt werden, damit Benutzer sich über ein Telefonfestnetz einwählen und an einer Audio/Video-Konferenz teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="67d51-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67d51-107">Wenn Sie von Office Communications Server 2007 R2 migrieren, müssen Sie vor der Bereitstellung von Einwahlkonferenzen die neuesten Updates auf Ihre Office Communications Server 2007 R2 Umgebung anwenden.</span><span class="sxs-lookup"><span data-stu-id="67d51-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="67d51-108">Verfahren zur Bereitstellung von Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="67d51-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67d51-109">Phase</span><span class="sxs-lookup"><span data-stu-id="67d51-109">Phase</span></span></th>
<th><span data-ttu-id="67d51-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="67d51-110">Steps</span></span></th>
<th><span data-ttu-id="67d51-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="67d51-111">Permissions</span></span></th>
<th><span data-ttu-id="67d51-112">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="67d51-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67d51-113"><strong>Erstellen Sie eine Topologie, die die Konferenz Arbeitsauslastung einschließlich einer Vermittlungsserver und eines PSTN-Gateways umfasst, und stellen Sie die Front-End-Pool oder Standard Edition-Server</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="67d51-114">Führen Sie den Topologie-Generator aus, um die Topologie zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="67d51-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="67d51-115">Wählen Sie beim Konfigurieren der Topologie die Einwahlkonferenzoption aus.</span><span class="sxs-lookup"><span data-stu-id="67d51-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="67d51-116">Veröffentlichen Sie die Topologie, und stellen Sie die Front-End-Pool oder Standard Edition-Server bereit.</span><span class="sxs-lookup"><span data-stu-id="67d51-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="67d51-117">Erstellen Sie bei Bedarf einen eigenständigen Vermittlungsserver und ordnen Sie ihn einem PSTN-Gateway zu.</span><span class="sxs-lookup"><span data-stu-id="67d51-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67d51-118">Dieser Schritt ist nur erforderlich, wenn Sie Enterprise-VoIP nicht bereitstellen und die Vermittlungsserver nicht mit dem collocate Enterprise-EditionFront-Server oder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="67d51-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="67d51-119">Wenn Sie Enterprise-VoIP bereitstellen, werden im Rahmen der Enterprise-VoIP-Bereitstellung Vermittlungsserver und PSTN-Gateways installiert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="67d51-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="67d51-120">Wenn Sie die Vermittlungsserver collocate, installieren und konfigurieren Sie die Vermittlungsserver im Rahmen der Front-End-Pool-oder Standard Edition-Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="67d51-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="67d51-121">Domänen-Admins</span><span class="sxs-lookup"><span data-stu-id="67d51-121">Domain Admins</span></span></p>
<p><span data-ttu-id="67d51-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-123">Administrator</span><span class="sxs-lookup"><span data-stu-id="67d51-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="67d51-124"><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="67d51-125">So erstellen Sie einen eigenständigen Vermittlungsserver Pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-126"><strong>Konfigurieren von Wähleinstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-127">Wähleinstellungen sind ein Satz von Rufnummernnormalisierungsregeln, die von einem bestimmten Standort aus gewählte Rufnummern in ein einziges Standardformat (E.164) übersetzen, um die Telefonautorisierung und das Anrufrouting zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="67d51-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="67d51-128">Eine von verschiedenen Standorten aus gewählte Rufnummer kann je nach Wähleinstellungen dem Standort entsprechend in unterschiedliche E.164-Nummern aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="67d51-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="67d51-129">Wenn Sie Enterprise-VoIP bereitstellen, richten Sie Wählpläne als Teil dieser Bereitstellung ein, und Sie müssen sicherstellen, dass die Wählpläne auch Einwahlkonferenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="67d51-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="67d51-130">Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie Wähleinstellungen für Einwahlkonferenzen einrichten.</span><span class="sxs-lookup"><span data-stu-id="67d51-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="67d51-131">Verwenden Sie die lync Server 2013-Systemsteuerung oder lync Server-Verwaltungsshell, um Wählpläne wie folgt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="67d51-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="67d51-132">Erstellen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl.</span><span class="sxs-lookup"><span data-stu-id="67d51-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="67d51-p105">Weisen Sie jedem Pool einen Standardsatz mit Wähleinstellungen zu. Legen Sie die <strong>Region für Einwahlkonferenzen</strong> auf den geografischen Standort fest, für den die Wähleinstellungen gelten. Die Region ordnet die Wähleinstellungen den Zugriffsnummern für die Einwahl zu.</span><span class="sxs-lookup"><span data-stu-id="67d51-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="67d51-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="67d51-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-141"><strong>Sicherstellen, dass Wählplänen Regionen zugewiesen werden</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-142">Führen Sie die Cmdlets <strong>Get-CsDialPlan</strong> und <strong>CsDialPlan</strong> aus, um sicherzustellen, dass allen Wählplänen eine Region zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="67d51-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="67d51-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="67d51-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Sicherstellen, dass den Wählplänen lync Server 2013 zugewiesene Regionen zugewiesen sind</a></span><span class="sxs-lookup"><span data-stu-id="67d51-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-148"><strong>(Optional) Überprüfen oder ändern Sie die Anforderungen an die persönliche Identifikationsnummer (PIN) der Benutzer.</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-149">Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um die Konferenz- <strong>PIN-Richtlinie</strong>anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67d51-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="67d51-150">Sie können eine PIN-Mindestlänge, eine maximale Anzahl von Anmeldeversuchen, ein PIN-Ablaufdatum und die Zulässigkeit gängiger Muster festlegen.</span><span class="sxs-lookup"><span data-stu-id="67d51-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="67d51-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Optional Überprüfen der PIN-Richtlinieneinstellungen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-155"><strong>Konfigurieren Sie die Konferenzrichtlinie so, dass Einwahlkonferenzen unterstützt werden.</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-156">Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um <strong>Konferenzrichtlinien</strong> Einstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="67d51-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="67d51-157">Legen Sie folgende Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="67d51-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="67d51-158">Die PSTN-Konferenzeinwahl ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="67d51-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="67d51-159">Benutzer können anonyme Teilnehmer einladen.</span><span class="sxs-lookup"><span data-stu-id="67d51-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="67d51-p108">Nicht authentifizierte Benutzer können über ausgehende Telefonverbindungen an einer Konferenz teilnehmen. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="67d51-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67d51-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Konfigurieren von Konferenzrichtlinien für die Einwahl in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-166"><strong>Konfigurieren von Zugriffsnummern für die Einwahl</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-167">Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um Zugriffsnummern für Einwahlen einzurichten, die von Benutzern bei der Einwahl in eine Konferenz aufgerufen werden, und geben Sie die Regionen an, die die Zugriffsnummer den entsprechenden Wählplänen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="67d51-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="67d51-168">Die ersten drei Zugriffsnummern für die Region, die durch die Wähleinstellungen des Organisators festgelegt wird, sind in der Konferenzeinladung enthalten.</span><span class="sxs-lookup"><span data-stu-id="67d51-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="67d51-169">Alle Zugriffsnummern stehen im Seite "Einstellungen für Einwahlkonferenzen" zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="67d51-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="67d51-170">Nachdem Sie Zugriffsnummern für die Einwahl erstellt haben, können Sie das Cmdlet " <STRONG>CsDialInConferencingAccessNumber</STRONG> " verwenden, um den Anzeigenamen der Active Directory Contact-Objekte zu ändern, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="67d51-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="67d51-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Konfigurieren von Zugriffsnummern für Einwahlkonferenzen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-175"><strong>(Optional) Überprüfen der Einwahlkonferenzeinstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-176">Suchen Sie mithilfe des Cmdlets <strong>Get-CsDialinConferencingAccessNumber</strong> nach Wähleinstellungen, deren Einwahlkonferenzregion von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern, denen keine Region zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="67d51-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="67d51-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="67d51-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="67d51-181">"Cshelpdesk"</span><span class="sxs-lookup"><span data-stu-id="67d51-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="67d51-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Optional Überprüfen der Einstellungen für Einwahlkonferenzen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-183"><strong>(Optional) Ändern der Tastenzuordnung von DTMF-Befehlen</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-184">Ändern Sie mithilfe des Cmdlets <strong>Set-CsDialinConferencingDtmfConfiguration</strong> die Tasten für DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren), mit denen Teilnehmer Konferenzeinstellungen steuern können (z. B. die Stummschaltung bzw. Aufhebung der Stummschaltung oder die Sperre bzw. Aufheben der Sperre).</span><span class="sxs-lookup"><span data-stu-id="67d51-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="67d51-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Optional Ändern der Tastenzuordnung für DTMF-Befehle in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-189"><strong>(Optional) Ändern Sie das Ankündigungsverhalten beim Beitreten oder Verlassen einer Konferenz</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-190">Ändern Sie mit dem Cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> die Funktionsweise von Ankündigungen, wenn Teilnehmer einer Konferenz beitreten bzw. diese verlassen.</span><span class="sxs-lookup"><span data-stu-id="67d51-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="67d51-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-195"><strong>(Optional) Überprüfen von Einwahlkonferenzen</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-196">Testen Sie mithilfe des Cmdlets <strong>Test-CsDialInConferencing</strong>, ob die Zugriffsnummern für den angegebenen Pool ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="67d51-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="67d51-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67d51-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Optional Überprüfen von Einwahlkonferenzen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-201"><strong>Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-202">Stellen Sie das Online Besprechungs-Add-in für lync 2013 bereit, damit Benutzer Konferenzen planen können, die Einwahlkonferenzen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="67d51-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="67d51-203">Das Online Besprechungs-Add-in für lync 2013 wird automatisch installiert, wenn Sie lync 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="67d51-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="67d51-204">Administratoren</span><span class="sxs-lookup"><span data-stu-id="67d51-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="67d51-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-206"><strong>Konfigurieren der Benutzerkontoeinstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-207">Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um den URI der Telefon <strong>Leitung</strong> als eindeutige, normalisierte Telefonnummer zu konfigurieren (beispielsweise Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="67d51-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="67d51-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67d51-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="67d51-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="67d51-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67d51-211"><a href="lync-server-2013-configure-user-account-settings.md">Konfigurieren von Benutzerkontoeinstellungen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67d51-212">Empfohlen Konfigurieren von Konferenz Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="67d51-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="67d51-213">Verwenden Sie das Cmdlet <strong>New-CsConferenceDirectory</strong> , um ein Konferenzverzeichnis für jeden 999-Benutzer im Pool zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="67d51-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="67d51-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="67d51-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in lync Server 2013</a> <a href="recommended-create-conference-directories.md">(empfohlen) Erstellen von Konferenz Verzeichnissen</a></span><span class="sxs-lookup"><span data-stu-id="67d51-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67d51-216"><strong>(Optional) Einladen von Benutzern zu Einwahlkonferenzen und Festlegen der anfänglichen PIN</strong></span><span class="sxs-lookup"><span data-stu-id="67d51-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="67d51-217">Verwenden Sie das Skript " <strong>CsPinSendCAWelcomeMail</strong> ", um die anfänglichen Pins der Benutzer festzulegen und eine Willkommens-e-Mail zu senden, die die anfängliche PIN und einen Link zum Seite "Einstellungen für Einwahlkonferenzen" enthält.</span><span class="sxs-lookup"><span data-stu-id="67d51-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="67d51-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67d51-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="67d51-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Optional Begrüßen von Benutzern für Einwahlkonferenzen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="67d51-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

