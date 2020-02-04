---
title: 'Lync Server 2013: Bereitstellungsprozess für die Reaktionsgruppe'
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
ms.openlocfilehash: 2eb302f57cd335decf3523c271ff464f2954db86
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="59a98-102">Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59a98-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59a98-103">_**Letztes Änderungsdatum des Themas:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="59a98-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="59a98-104">Dieser Abschnitt enthält eine Übersicht über die Phasen und Schritte, die beim Bereitstellen der reaktionsgruppenanwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="59a98-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="59a98-105">Prozess zur Bereitstellung von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="59a98-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59a98-106">Phase</span><span class="sxs-lookup"><span data-stu-id="59a98-106">Phase</span></span></th>
<th><span data-ttu-id="59a98-107">Schritte</span><span class="sxs-lookup"><span data-stu-id="59a98-107">Steps</span></span></th>
<th><span data-ttu-id="59a98-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="59a98-108">Permissions</span></span></th>
<th><span data-ttu-id="59a98-109">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="59a98-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59a98-110">Installieren der reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="59a98-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="59a98-111">Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="59a98-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="59a98-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="59a98-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59a98-114">Komponenten für Reaktionsgruppe installieren</span><span class="sxs-lookup"><span data-stu-id="59a98-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="59a98-115">Lync Server-Cmdlets, die lync Server-Systemsteuerung, das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents und der Client-Webdienst für Reaktionsgruppen werden als Teil von Webdiensten installiert.</span><span class="sxs-lookup"><span data-stu-id="59a98-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="59a98-116">Webdienste werden installiert, wenn Sie einen Enterprise Edition-Pool oder einen Standard Edition-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="59a98-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="59a98-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="59a98-118"><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59a98-119">Aktivieren von Benutzern für lync 2013 und für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="59a98-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="59a98-120">Aktivieren Sie Benutzer, die Agents für lync Server und Enterprise-VoIP sein sollen.</span><span class="sxs-lookup"><span data-stu-id="59a98-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="59a98-121">Benutzer müssen aktiviert sein, damit sie Agentgruppen hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="59a98-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="59a98-122">In der Regel sind Benutzer während der Enterprise Edition-oder Standard Edition-Server Bereitstellung für lync Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="59a98-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="59a98-123">Benutzer sind während der Enterprise-VoIP-Bereitstellung für Enterprise-VoIP aktiviert.</span><span class="sxs-lookup"><span data-stu-id="59a98-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="59a98-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="59a98-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="59a98-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="59a98-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59a98-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59a98-129">Erstellen und Konfigurieren von Reaktionsgruppen, die aus Agentgruppen, Warteschlangen und Workflows bestehen</span><span class="sxs-lookup"><span data-stu-id="59a98-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="59a98-130">Verwenden Sie die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="59a98-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="59a98-131">Erstellen und Konfigurieren von Agentgruppen</span><span class="sxs-lookup"><span data-stu-id="59a98-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="59a98-132">Erstellen und Konfigurieren von Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="59a98-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="59a98-133">Optional können Sie mithilfe der lync Server-Verwaltungsshell vordefinierte Geschäftszeiten und Feiertage in der Reaktionsgruppe erstellen.</span><span class="sxs-lookup"><span data-stu-id="59a98-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="59a98-134">Verwenden Sie das Reaktionsgruppen-Konfigurations Tool oder die lync Server-Verwaltungsshell zum Erstellen von Workflows (Sammelanschlüsse oder IVR-Anruf Bewegungen (Interactive Voice Response), einschließlich benutzerdefinierter Reaktionsgruppen-Geschäftszeiten und-Feiertage.</span><span class="sxs-lookup"><span data-stu-id="59a98-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="59a98-135">Sie können über die lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.</span><span class="sxs-lookup"><span data-stu-id="59a98-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="59a98-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="59a98-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="59a98-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="59a98-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="59a98-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="59a98-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="59a98-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="59a98-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59a98-143"><a href="lync-server-2013-create-response-group-queues.md">Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59a98-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59a98-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="59a98-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Erstellen oder Ändern eines Workflows in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59a98-147">(Optional) Anpassen der Einstellungen auf Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="59a98-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="59a98-148">Verwenden Sie die lync Server-Verwaltungsshell zum Anpassen der standardmäßigen Music-on-halten-Konfiguration, der standardmäßigen Music-on-halten-Audiodatei, des Kulanzzeitraums für den Rückruf des Agenten und der Konfiguration des Anruf Kontexts.</span><span class="sxs-lookup"><span data-stu-id="59a98-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="59a98-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="59a98-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="59a98-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="59a98-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="59a98-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="59a98-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59a98-155">(Optional) Delegieren der Verwaltung von Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="59a98-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="59a98-156">Weisen Sie Benutzern die CsResponseGroupManager-Rolle zu, um die Konfiguration von Reaktionsgruppen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="59a98-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="59a98-157">Die Antwortgruppen-Manager können dann die Ihnen zugewiesenen Antwortgruppen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="59a98-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="59a98-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="59a98-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="59a98-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="59a98-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="59a98-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="59a98-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="59a98-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="59a98-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planen für die rollenbasierte Zugriffssteuerung in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="59a98-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59a98-164">Überprüfen der Reaktionsgruppenbereitstellung</span><span class="sxs-lookup"><span data-stu-id="59a98-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="59a98-165">Führen Sie Testanrufe bei den Sammelanschlüssen und IVR-Workflows durch, um sicherzustellen, dass die Konfiguration wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="59a98-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

