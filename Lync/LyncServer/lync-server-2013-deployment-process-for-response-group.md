---
title: 'Lync Server 2013: Bereitstellungsprozess für Reaktionsgruppen'
description: 'Lync Server 2013: Bereitstellungsprozess für Reaktionsgruppen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b50fb7903a2fcc301bbf435013b8f8df4e775a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551031"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="5296a-103">Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5296a-103">Deployment process for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5296a-104">_**Letztes Änderungsstand des Themas:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="5296a-104">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="5296a-105">Dieser Abschnitt enthält eine Übersicht über die Phasen und Schritte bei der Bereitstellung des Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="5296a-105">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="5296a-106">Prozess zur Bereitstellung von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="5296a-106">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5296a-107">Phase</span><span class="sxs-lookup"><span data-stu-id="5296a-107">Phase</span></span></th>
<th><span data-ttu-id="5296a-108">Schritte</span><span class="sxs-lookup"><span data-stu-id="5296a-108">Steps</span></span></th>
<th><span data-ttu-id="5296a-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5296a-109">Permissions</span></span></th>
<th><span data-ttu-id="5296a-110">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="5296a-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5296a-111">Installieren des Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="5296a-111">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="5296a-112">Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5296a-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="5296a-113">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-113">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5296a-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5296a-115">Installieren von Komponenten für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="5296a-115">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="5296a-116">Lync Server-Cmdlets, das lync Server-Systemsteuerung, das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents und der Client-Webdienst der Reaktionsgruppe werden als Teil von Webdienste installiert.</span><span class="sxs-lookup"><span data-stu-id="5296a-116">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="5296a-117">Webdienste wird installiert, wenn Sie einen Enterprise Edition-Pool oder ein Standard Edition-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5296a-117">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="5296a-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5296a-119"><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-119"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5296a-120">Aktivieren von Benutzern für lync 2013 und für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="5296a-120">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="5296a-121">Aktivieren Sie Benutzer, die Agents für lync Server und Enterprise-VoIP sein sollen.</span><span class="sxs-lookup"><span data-stu-id="5296a-121">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="5296a-122">Benutzer müssen aktiviert sein, bevor Sie Sie zu Agentgruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="5296a-122">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="5296a-123">In der Regel werden Benutzer während der Enterprise Edition-oder Standard Edition-Server-Bereitstellung für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5296a-123">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="5296a-124">Benutzer sind während der Enterprise-VoIP-Bereitstellung für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5296a-124">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="5296a-125">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-125">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="5296a-126">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-126">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="5296a-127">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-127">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5296a-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5296a-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5296a-130">Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen</span><span class="sxs-lookup"><span data-stu-id="5296a-130">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5296a-131">Verwenden Sie die lync Server-Systemsteuerung oder lync Server-Verwaltungsshell, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="5296a-131">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="5296a-132">Erstellen und Konfigurieren von Agentgruppen</span><span class="sxs-lookup"><span data-stu-id="5296a-132">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="5296a-133">Erstellen und Konfigurieren von Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="5296a-133">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="5296a-134">Verwenden Sie optional lync Server-Verwaltungsshell, um vordefinierte Reaktionsgruppen-Geschäftszeiten und Feiertage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5296a-134">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="5296a-135">Verwenden Sie das Reaktionsgruppen-Konfigurations Tool oder lync Server-Verwaltungsshell, um Workflows (Sammelanschlüsse oder interaktive Sprachantwort-Anruf Flüsse) zu erstellen, einschließlich benutzerdefinierter Reaktionsgruppen-Geschäftszeiten und Feiertage.</span><span class="sxs-lookup"><span data-stu-id="5296a-135">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5296a-136">Sie können über lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5296a-136">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="5296a-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5296a-138">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-138">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5296a-139">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-139">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5296a-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-140">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5296a-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-141">CsAdministrator</span></span></p>
<p><span data-ttu-id="5296a-142">Rolle csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="5296a-142">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="5296a-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Erstellen von Gruppen für Reaktionsgruppen-Agents lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5296a-144"><a href="lync-server-2013-create-response-group-queues.md">Erstellen von Warteschlangen für Reaktionsgruppen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-144"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5296a-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5296a-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5296a-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Erstellen oder Ändern eines Workflows in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5296a-148">(Optional) Anpassen der Einstellungen auf Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="5296a-148">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="5296a-149">Verwenden Sie lync Server-Verwaltungsshell zum Anpassen der standardmäßigen Music-on-Hold-Konfiguration, der standardmäßigen Music-on-Hold-Audiodatei, der Kulanzfrist für den Agent-Rückruf und der Anrufkontext Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5296a-149">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="5296a-150">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-150">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5296a-151">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-151">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5296a-152">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-152">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5296a-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5296a-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5296a-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5296a-156">(Optional) Delegieren der Verwaltung von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="5296a-156">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="5296a-157">Weisen Sie Benutzern die Rolle csresponsegroupmanager-Rolle zu, um die Konfiguration von Reaktionsgruppen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="5296a-157">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="5296a-158">Reaktionsgruppen-Manager können dann die Ihnen zugewiesenen Reaktionsgruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5296a-158">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="5296a-159">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5296a-159">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5296a-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-160">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5296a-161">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-161">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5296a-162">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-162">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5296a-163">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5296a-163">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5296a-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5296a-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5296a-165">Überprüfen der Reaktionsgruppenbereitstellung</span><span class="sxs-lookup"><span data-stu-id="5296a-165">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="5296a-166">Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5296a-166">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

