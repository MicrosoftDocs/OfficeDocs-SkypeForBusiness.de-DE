---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung für persistent Chat Server'
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
ms.openlocfilehash: 2399d6ce6fc17a802c8f6bc39730370948ef0253
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522742"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="6112b-102">Prüfliste für die Bereitstellung für persistent Chat Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6112b-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6112b-103">_**Letztes Änderungsstand des Themas:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="6112b-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="6112b-104">Für die Bereitstellung von lync Server 2013 ist der Server für beständigen Chat erforderlich, dass Sie ihn in der richtigen Reihenfolge bereitstellen und alle erforderlichen Bereitstellungsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="6112b-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="6112b-105">Bereitstellungsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="6112b-105">Deployment Sequence</span></span>

<span data-ttu-id="6112b-106">Sie können den Server für beständigen Chat bereitstellen, nachdem Sie die anfängliche Topologie bereitgestellt haben, einschließlich mindestens einer lync Server 2013, Front-End-Pool oder einer lync Server 2013 Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="6112b-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="6112b-107">In diesem Thema wird beschrieben, wie Sie den Server für beständigen Chat bereitstellen, indem Sie ihn einer vorhandenen Bereitstellung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6112b-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="6112b-108">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="6112b-108">Deployment Process</span></span>

<span data-ttu-id="6112b-109">In der folgenden Tabelle sind die grundlegenden Schritte zum Bereitstellen des Servers für beständigen Chat und Links für weitere Details aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6112b-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="6112b-110">Server Bereitstellungsprozess für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6112b-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6112b-111">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="6112b-111">Task</span></span></th>
<th><span data-ttu-id="6112b-112">Schritte</span><span class="sxs-lookup"><span data-stu-id="6112b-112">Steps</span></span></th>
<th><span data-ttu-id="6112b-113">Erforderliche Rollen und Gruppenmitgliedschaften</span><span class="sxs-lookup"><span data-stu-id="6112b-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="6112b-114">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6112b-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6112b-115"><strong>Erforderliche Hardware und Software installieren</strong></span><span class="sxs-lookup"><span data-stu-id="6112b-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6112b-116">Installieren Sie die folgenden Komponenten auf einem Hardwaresystem, das die Systemanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="6112b-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-117">Auf den Front-End-Servern für beständigen Chat Server:</span><span class="sxs-lookup"><span data-stu-id="6112b-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="6112b-118">Ein Betriebssystem, das die Systemanforderungen erfüllt</span><span class="sxs-lookup"><span data-stu-id="6112b-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="6112b-119">Software Voraussetzungen für Computer mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6112b-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="6112b-120">SQL Server auf dem Server, auf dem die Server Datenbank für beständigen Chat gehostet wird</span><span class="sxs-lookup"><span data-stu-id="6112b-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="6112b-121">Wenn die Server Kompatibilität für beständigen Chat erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="6112b-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-122">SQL Server auf dem Server, auf dem die Kompatibilitätsdatenbank für den Server für beständigen Chat gehostet wird</span><span class="sxs-lookup"><span data-stu-id="6112b-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6112b-123">Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6112b-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="6112b-124"><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6112b-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server Software-und Infrastrukturunterstützung in lync Server 2013</a> in der Unterstützungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6112b-126"><a href="lync-server-2013-determining-your-system-requirements.md">Bestimmen der Systemanforderungen für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6112b-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="6112b-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technische Anforderungen für den Server für beständigen Chat in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6112b-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6112b-128"><strong>Erstellen der geeigneten internen Topologie zur Unterstützung des Servers für beständigen Chat (und optional beständiger Chat – Compliance)</strong></span><span class="sxs-lookup"><span data-stu-id="6112b-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="6112b-129">Führen Sie den Topologie-Generator aus, um der Topologie einen Server Pool für beständigen Chat hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="6112b-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-130">Hinzufügen von Komponenten für beständigen Chat Server zur Topologie</span><span class="sxs-lookup"><span data-stu-id="6112b-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="6112b-131">Erstellen einer SQL Server Datenbank für den Server Speicher für beständigen Chat (und eine Sicherungs SQL Server für die Notfallwiederherstellung)</span><span class="sxs-lookup"><span data-stu-id="6112b-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="6112b-132">Definieren einer neuen lync-Dateispeicher oder Verwenden einer vorhandenen lync-Dateispeicher für Server Dateien für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6112b-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="6112b-133">Zuordnen des lync Server 2013 Pools, der Anforderungen an diesen Server Pool für beständigen Chat weiterleiten kann</span><span class="sxs-lookup"><span data-stu-id="6112b-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="6112b-134">Wenn die Compliance für beständigen Chat erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="6112b-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-135">Kompatibilitäts Speicher für beständigen Chat hinzufügen</span><span class="sxs-lookup"><span data-stu-id="6112b-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="6112b-136">Aktivieren Sie das Kontrollkästchen Definition für den Server Pool für beständigen Chat zur Aktivierung der Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="6112b-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="6112b-137">Veröffentlichen der Topologie</span><span class="sxs-lookup"><span data-stu-id="6112b-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="6112b-138">Wenn Sie den Server für beständigen Chat auf Standard Edition installieren, muss der vollqualifizierte Domänenname (FQDN) des Server Pools für beständigen Chat mit dem Standard Edition-Server übereinstimmen, und die SQL Server Datenbanken befinden sich auf der SQL Server Express Instanz auf dem Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="6112b-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="6112b-139">Zum Definieren einer Topologie. Ein Konto, das Mitglieder der lokalen Gruppe "Benutzer" ist.</span><span class="sxs-lookup"><span data-stu-id="6112b-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="6112b-140">Um die Topologie zu veröffentlichen, muss ein Konto, das Mitglied der Gruppe "Domänen-Admins" und der RTCUniversalServerAdmins-Gruppe ist, sowie der Benutzer über die Berechtigung "Vollzugriff" (Lesen/Schreiben/ändern) für die lync-Dateispeicher für Server Dateien für beständigen Chat verfügen (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann).</span><span class="sxs-lookup"><span data-stu-id="6112b-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="6112b-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen von persistent Chat Server zu Ihrer Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6112b-142"><strong>Bereitstellen des Servers für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="6112b-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="6112b-143">Führen Sie das lync Server-Setup auf allen Computern aus, auf denen persistent Chat Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6112b-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="6112b-144">Das Setup für beständigen Chat Server ist in den lync Server 2013-Bereitstellungs-Assistenten integriert, der die folgenden Anweisungen bereitstellt:</span><span class="sxs-lookup"><span data-stu-id="6112b-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-145">Den lokalen Verwaltungsspeicher bereitstellen</span><span class="sxs-lookup"><span data-stu-id="6112b-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="6112b-146">Installieren von Server Diensten für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="6112b-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="6112b-147">Zertifikate anfordern und zuweisen</span><span class="sxs-lookup"><span data-stu-id="6112b-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="6112b-148">Dienste ausführen und starten</span><span class="sxs-lookup"><span data-stu-id="6112b-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6112b-149">Jeder Benutzer, der Mitglied der lokalen Administratorgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="6112b-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="6112b-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Bereitstellen des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6112b-151"><strong>Erstellen eines Administrators für beständigen Chat</strong></span><span class="sxs-lookup"><span data-stu-id="6112b-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="6112b-152">Fügen Sie der Sicherheitsgruppe "CsPersistentChatAdministrator" Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="6112b-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="6112b-153">Jeder Benutzer, der Mitglied der Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="6112b-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="6112b-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Hinzufügen eines Administrators für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6112b-155"><strong>Konfigurieren von Persistent Chat Server</strong></span><span class="sxs-lookup"><span data-stu-id="6112b-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="6112b-156">Konfigurieren von Benutzern:</span><span class="sxs-lookup"><span data-stu-id="6112b-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="6112b-157">Der Benutzer muss durch eine Richtlinie aktiviert sein, um auf den Server für beständigen Chat zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6112b-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="6112b-158">Die Richtlinie ist standardmäßig für alle Benutzer deaktiviert und kann auf globaler, Standort-, Pool- und Benutzerebene definiert werden.</span><span class="sxs-lookup"><span data-stu-id="6112b-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="6112b-159">Einstellungen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="6112b-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6112b-p104">Der Benutzer muss Mitglied von "CsPersistentChatAdministrator" sein. Benutzer müssen sich zum Ändern der Richtlinie mindestens in "CsUserAdministrator" befinden.</span><span class="sxs-lookup"><span data-stu-id="6112b-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="6112b-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Konfigurieren des Servers für beständigen Chat in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6112b-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="6112b-163">Sie können einen oder mehrere Server Pools für beständigen Chat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6112b-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="6112b-164">Wir unterstützen mehrere Server Pools für beständigen Chat aus regulatorischen Gründen, wobei Daten, die in einer bestimmten Region generiert werden, in dieser Region verbleiben müssen.</span><span class="sxs-lookup"><span data-stu-id="6112b-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="6112b-165">Wenn Sie beispielsweise einen Serverpool für beständigen Chat in Chicago und einen anderen in Zürich bereitstellen, um die Vorschriften für Daten in der Schweiz einzuhalten, können Benutzer in den Server Pools für beständigen Chat auf Chatrooms zugreifen, vorausgesetzt, Sie verfügen über Zugriff.</span><span class="sxs-lookup"><span data-stu-id="6112b-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

