---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung für persistent Chat Server'
description: 'Lync Server 2013: Prüfliste für die Bereitstellung des Servers für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568291"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="61e99-103">Prüfliste für die Bereitstellung für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61e99-103">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61e99-104">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="61e99-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="61e99-105">Für die Bereitstellung von lync Server 2013 ist der Server für beständigen Chat erforderlich, dass Sie ihn in der richtigen Reihenfolge bereitstellen und alle erforderlichen Bereitstellungsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="61e99-105">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="61e99-106">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="61e99-106">Deployment Sequence</span></span>

<span data-ttu-id="61e99-107">Sie können den Server für beständigen Chat bereitstellen, nachdem Sie die anfängliche Topologie bereitgestellt haben, einschließlich mindestens einer lync Server 2013, Front-End-Pool oder einer lync Server 2013 Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="61e99-107">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="61e99-108">In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat bereitstellen, indem Sie ihn einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="61e99-108">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="61e99-109">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="61e99-109">Deployment Process</span></span>

<span data-ttu-id="61e99-110">In der folgenden Tabelle sind die grundlegenden Schritte zum Bereitstellen des Servers für beständigen Chat und Links für weitere Details aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="61e99-110">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="61e99-111">Server Bereitstellungsprozess für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="61e99-111">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61e99-112">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="61e99-112">Task</span></span></th>
<th><span data-ttu-id="61e99-113">Schritte</span><span class="sxs-lookup"><span data-stu-id="61e99-113">Steps</span></span></th>
<th><span data-ttu-id="61e99-114">Erforderliche Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="61e99-114">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="61e99-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="61e99-115">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61e99-116"><strong>Erforderliche Hardware und Software installieren</strong></span><span class="sxs-lookup"><span data-stu-id="61e99-116"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="61e99-117">Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="61e99-117">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-118">Auf den Front-End-Servern für beständigen Chat Server:</span><span class="sxs-lookup"><span data-stu-id="61e99-118">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="61e99-119">Ein Betriebssystem, das die Systemanforderungen erfüllt</span><span class="sxs-lookup"><span data-stu-id="61e99-119">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="61e99-120">Software Voraussetzungen für Computer mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61e99-120">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="61e99-121">SQL Server auf dem Server, auf dem die Server Datenbank für beständigen Chat gehostet wird</span><span class="sxs-lookup"><span data-stu-id="61e99-121">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="61e99-122">Wenn die Server Kompatibilität für beständigen Chat erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="61e99-122">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-123">SQL Server auf dem Server, auf dem die Kompatibilitätsdatenbank für den Server für beständigen Chat gehostet wird</span><span class="sxs-lookup"><span data-stu-id="61e99-123">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="61e99-124">Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="61e99-124">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="61e99-125"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-125"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="61e99-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="61e99-127"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="61e99-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="61e99-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="61e99-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e99-129"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung des Servers für beständigen Chat (und optional beständiger Chat – Compliance)</strong></span><span class="sxs-lookup"><span data-stu-id="61e99-129"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="61e99-130">Führen Sie den Topologie-Generator aus, um der Topologie einen Server Pool für beständigen Chat hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="61e99-130">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-131">Hinzufügen von Komponenten für beständigen Chat Server zur Topologie</span><span class="sxs-lookup"><span data-stu-id="61e99-131">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="61e99-132">Erstellen einer SQL Server Datenbank für den Server Speicher für beständigen Chat (und eine Sicherungs SQL Server für die Notfallwiederherstellung)</span><span class="sxs-lookup"><span data-stu-id="61e99-132">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="61e99-133">Definieren einer neuen lync-Dateispeicher oder Verwenden einer vorhandenen lync-Dateispeicher für Server Dateien für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="61e99-133">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="61e99-134">Zuordnen des lync Server 2013 Pools, der Anforderungen an diesen Server Pool für beständigen Chat weiterleiten kann</span><span class="sxs-lookup"><span data-stu-id="61e99-134">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="61e99-135">Wenn die Compliance für beständigen Chat erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="61e99-135">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-136">Kompatibilitäts Speicher für beständigen Chat hinzufügen</span><span class="sxs-lookup"><span data-stu-id="61e99-136">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="61e99-137">Aktivieren Sie das Kontrollkästchen Definition für den Server Pool für beständigen Chat zur Aktivierung der Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="61e99-137">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="61e99-138">Veröffentlichen der Topologie</span><span class="sxs-lookup"><span data-stu-id="61e99-138">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="61e99-139">Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (FQDN) des Server Pools für beständigen Chat mit dem Standard Edition-Server übereinstimmen, und die SQL Server Datenbanken befinden sich auf der SQL Server Express Instanz auf dem Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="61e99-139">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="61e99-140">Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe "Benutzer" ist.</span><span class="sxs-lookup"><span data-stu-id="61e99-140">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="61e99-141">Um die Topologie zu veröffentlichen, muss ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, sowie der Benutzer über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die lync-Dateispeicher für Server Dateien für beständigen Chat verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</span><span class="sxs-lookup"><span data-stu-id="61e99-141">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="61e99-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von persistent Chat Server zu Ihrer Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e99-143"><strong>Bereitstellen des Servers für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="61e99-143"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="61e99-144">Führen Sie das lync Server-Setup auf allen Computern aus, auf denen persistent Chat Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61e99-144">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="61e99-145">Das Setup für beständigen Chat Server ist in den lync Server 2013-Bereitstellungs-Assistenten integriert, der die folgenden Anweisungen bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="61e99-145">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-146">Den lokalen Verwaltungsspeicher bereitstellen</span><span class="sxs-lookup"><span data-stu-id="61e99-146">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="61e99-147">Installieren von Server Diensten für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="61e99-147">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="61e99-148">Zertifikate anfordern und zuweisen</span><span class="sxs-lookup"><span data-stu-id="61e99-148">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="61e99-149">Dienste ausführen und starten</span><span class="sxs-lookup"><span data-stu-id="61e99-149">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="61e99-150">Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="61e99-150">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="61e99-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e99-152"><strong>Erstellen eines Administrators für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="61e99-152"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="61e99-153">Fügen Sie der Sicherheitsgruppe "CsPersistentChatAdministrator" Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="61e99-153">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="61e99-154">Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="61e99-154">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="61e99-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e99-156"><strong>Konfigurieren von Persistent Chat Server</strong></span><span class="sxs-lookup"><span data-stu-id="61e99-156"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="61e99-157">Konfigurieren von Benutzern:</span><span class="sxs-lookup"><span data-stu-id="61e99-157">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="61e99-158">Der Benutzer muss durch eine Richtlinie aktiviert sein, um auf den Server für beständigen Chat zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="61e99-158">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="61e99-159">Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</span><span class="sxs-lookup"><span data-stu-id="61e99-159">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="61e99-160">Einstellungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="61e99-160">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="61e99-p104">Der Benutzer muss Mitglied von "CsPersistentChatAdministrator" sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in "CsUserAdministrator" befinden.</span><span class="sxs-lookup"><span data-stu-id="61e99-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="61e99-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="61e99-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="61e99-164">Sie können einen oder mehrere Server Pools für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="61e99-164">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="61e99-165">Wir unterstützen mehrere Server Pools für beständigen Chat aus regulatorischen Gründen, wobei Daten, die in einer bestimmten Region generiert werden, in dieser Region verbleiben müssen.</span><span class="sxs-lookup"><span data-stu-id="61e99-165">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="61e99-166">Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago und einen anderen in Zürich bereitstellen, um die Vorschriften für Daten in der Schweiz einzuhalten, können Benutzer in den Server Pools für beständigen Chat auf Chatrooms zugreifen, vorausgesetzt, Sie verfügen über Zugriff.</span><span class="sxs-lookup"><span data-stu-id="61e99-166">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

