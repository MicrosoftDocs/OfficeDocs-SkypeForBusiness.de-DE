---
title: Bereitstellungsprozess für die Integration von lokalen Unified Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="1db18-102">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1db18-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1db18-103">_**Letztes Änderungsdatum des Themas:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="1db18-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="1db18-104">Wenn Sie Exchange Unified Messaging (um) in lync Server 2013 integrieren möchten, müssen Sie die in diesem Thema beschriebenen Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="1db18-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="1db18-105">Stellen Sie außerdem sicher, dass Sie die bewährten Methoden für die Planung und Bereitstellung überprüfen, die unter [Richtlinien für die Integration von lokalen Unified Messaging und lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="1db18-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="1db18-106">In diesem Thema wird davon ausgegangen, dass Sie lync Server 2013 mit einem zusammengefassten Vermittlungsserver bereitgestellt haben und dass Sie Benutzer für lync Server 2013 aktiviert haben, aber nicht unbedingt, dass Sie alle Bereitstellungs-und Konfigurationsschritte ausgeführt haben, um Enterprise-VoIP zu aktivieren, wie unter [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1db18-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="1db18-107">Integrationsprozess für Unified Messaging (UM)</span><span class="sxs-lookup"><span data-stu-id="1db18-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1db18-108">Es ist wichtig, dass Sie sich bezüglich der durchzuführenden Aufgaben mit den Exchange-Administratoren in Ihrer Organisation absprechen, um eine nahtlose und erfolgreiche Integration sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="1db18-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1db18-109">Phase</span><span class="sxs-lookup"><span data-stu-id="1db18-109">Phase</span></span></th>
<th><span data-ttu-id="1db18-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="1db18-110">Steps</span></span></th>
<th><span data-ttu-id="1db18-111">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="1db18-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="1db18-112">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="1db18-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1db18-113">Stellen Sie eine der folgenden Exchange-Versionen bereit:</span><span class="sxs-lookup"><span data-stu-id="1db18-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="1db18-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="1db18-115">Microsoft Exchange Server 2010 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="1db18-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="1db18-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1db18-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1db18-117">Wenn Sie Microsoft Exchange Server 2013 verwenden, installieren Sie die folgenden Exchange-Serverrollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1db18-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-118">Clientzugriff</span><span class="sxs-lookup"><span data-stu-id="1db18-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="1db18-119">Postfach</span><span class="sxs-lookup"><span data-stu-id="1db18-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="1db18-120">Wenn Microsoft Exchange Server 2013 und Exchange Unified Messaging (um) in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur vertraut.</span><span class="sxs-lookup"><span data-stu-id="1db18-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="1db18-121">Wenn Sie Exchange 2010 verwenden, installieren Sie die folgenden Exchange-Serverrollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1db18-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-122">Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="1db18-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="1db18-123">Hub-Transport</span><span class="sxs-lookup"><span data-stu-id="1db18-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="1db18-124">Clientzugriff</span><span class="sxs-lookup"><span data-stu-id="1db18-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="1db18-125">Postfach</span><span class="sxs-lookup"><span data-stu-id="1db18-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="1db18-126">Wenn lync Server 2013 und Exchange Unified Messaging (um) in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur vertraut.</span><span class="sxs-lookup"><span data-stu-id="1db18-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="1db18-127">Organisations-Admins (wenn es sich um den ersten Exchange Server in der Organisation handelt)</span><span class="sxs-lookup"><span data-stu-id="1db18-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="1db18-128">- oder -</span><span class="sxs-lookup"><span data-stu-id="1db18-128">-OR-</span></span></p>
<p><span data-ttu-id="1db18-129">Exchange-Organisationsadministrator (wenn es sich nicht um den ersten Exchange Server in der Organisation handelt)</span><span class="sxs-lookup"><span data-stu-id="1db18-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="1db18-130">Weitere Informationen finden Sie in der Dokumentation zur jeweiligen Version von Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="1db18-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1db18-131">Exchange Server 2007-Bereitstellungs <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1db18-132">Exchange Server 2010 oder neueste Service Pack-Bereitstellungs <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="1db18-133">Microsoft Exchange Server 2013-Planung und- <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>Bereitstellung bei.</span><span class="sxs-lookup"><span data-stu-id="1db18-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db18-134">Installieren Sie Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="1db18-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="1db18-135">Laden Sie Zertifikate für jeden Exchange um-Server von einer vertrauenswürdigen Stammzertifizierungsstelle herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="1db18-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="1db18-136">Die Zertifikate sind für MTLS (Mutual Transport Level Security) zwischen den Servern mit Exchange um und lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1db18-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="1db18-137">Administratoren</span><span class="sxs-lookup"><span data-stu-id="1db18-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="1db18-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird</a></span><span class="sxs-lookup"><span data-stu-id="1db18-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db18-139">Erstellen und Konfigurieren eines neuen Exchange um-SIP-Wählplans</span><span class="sxs-lookup"><span data-stu-id="1db18-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1db18-140">Erstellen Sie auf dem Exchange um-Server einen SIP-Wählplan, der auf den spezifischen Bereitstellungsanforderungen Ihrer Organisation basiert.</span><span class="sxs-lookup"><span data-stu-id="1db18-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="1db18-141">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="1db18-142">Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Erstellen eines Unified Messaging-SIP-&quot; URI <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>-Wähl Plans unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="1db18-143">Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Erstellen eines&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>-Wählplans unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="1db18-144">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db18-145">Konfigurieren Sie die Sicherheitseinstellungen für den Exchange um-SIP-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="1db18-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1db18-146">Um Enterprise-VoIP-Datenverkehr zu verschlüsseln, konfigurieren Sie die Sicherheitseinstellungen für den Exchange um-SIP-Wählplan als <strong>SIP-gesichert</strong> oder <strong>gesichert</strong>.</span><span class="sxs-lookup"><span data-stu-id="1db18-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="1db18-147">Dies ist ein besonders wichtiger Schritt, wenn Sie lync Phone Edition-Geräte in Ihrer Umgebung bereitgestellt oder geplant haben.</span><span class="sxs-lookup"><span data-stu-id="1db18-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="1db18-148">Damit lync Phone Edition-Geräte in einer Umgebung mit Exchange um-Integration funktionieren, müssen die lync Server-Verschlüsselungseinstellungen mit den Sicherheitseinstellungen für den Exchange um-Wählplan ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="1db18-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="1db18-149">Ausführliche Informationen zu diesem Thema finden Sie in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1db18-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="1db18-150">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="1db18-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1db18-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1db18-152">Für Exchange 2007 SP1 oder das neueste Service Pack siehe auch:</span><span class="sxs-lookup"><span data-stu-id="1db18-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="1db18-153">&quot;Informationen zum Konfigurieren der Sicherheit für einen Unified Messaging-&quot; Wählplan <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="1db18-154">Informationen zu Exchange&#160;2010 oder neuestes Service Pack finden Sie auch hier:</span><span class="sxs-lookup"><span data-stu-id="1db18-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="1db18-155">&quot;Konfigurieren der VoIP&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>-Sicherheit für einen um-Wählplan</span><span class="sxs-lookup"><span data-stu-id="1db18-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="1db18-156">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db18-157">Fügen Sie dem Exchange um-SIP-Wählplan Unified Messaging-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="1db18-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1db18-158">Wenn Sie einen neu installierten Unified Messaging-Server zur Entgegennahme und Verarbeitung eingehender Anrufe aktivieren möchten, müssen Sie den Unified Messaging-Server einem UM-Wählplan hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1db18-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="1db18-159">Fügen Sie in diesem Fall den Server dem Exchange um-SIP-Wählplan hinzu.</span><span class="sxs-lookup"><span data-stu-id="1db18-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="1db18-160">Administratoren</span><span class="sxs-lookup"><span data-stu-id="1db18-160">Administrators</span></span></p>
<p><span data-ttu-id="1db18-161">Exchange-Serveradministratoren</span><span class="sxs-lookup"><span data-stu-id="1db18-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="1db18-162">Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Hinzufügen eines Unified Messaging-Servers&quot; zu <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>einem Wählplan unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="1db18-163">Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Anzeigen oder Konfigurieren der Eigenschaften eines&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>-Servers.</span><span class="sxs-lookup"><span data-stu-id="1db18-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="1db18-164">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db18-165">Konfigurieren Sie Postfächer mit SIP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="1db18-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="1db18-166">Weisen Sie den Postfächern von Enterprise-VoIP-Benutzern, die Exchange um-Features verwenden werden, SIP-Adressen zu.</span><span class="sxs-lookup"><span data-stu-id="1db18-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="1db18-167">Lync Server 2013-Administrator</span><span class="sxs-lookup"><span data-stu-id="1db18-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="1db18-168">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1db18-169">Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Hinzufügen, entfernen oder Ändern einer SIP-Adresse für einen um-&quot; aktivierten <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>Benutzer unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="1db18-170">Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Ändern einer SIP-Adresse für einen&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>-aktivierten Benutzer unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="1db18-171">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db18-172">Führen Sie das Skript "exchucutil.ps1" aus.</span><span class="sxs-lookup"><span data-stu-id="1db18-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="1db18-173">Öffnen Sie auf dem Server, auf dem Exchange um-Dienste ausgeführt wird, die Exchange-Verwaltungsshell, und führen Sie das exchucutil. ps1-Skript aus, das Folgendes ausführt:</span><span class="sxs-lookup"><span data-stu-id="1db18-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-174">Erteilt lync Server 2013 die Berechtigung zum Lesen von Exchange um-Active Directory-Domänendienst Objekten, insbesondere den SIP-Wählplänen, die in der vorherigen Aufgabe erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1db18-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="1db18-175">Erstellt ein Unified Messaging-IP-Gateway-Objekt in Active Directory für jeden lync Server 2013 Enterprise Edition-Pool oder Standard Edition-Server, der Benutzer hostet, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="1db18-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="1db18-176">Erstellt einen Exchange um-Sammelanschluss für jedes Gateway.</span><span class="sxs-lookup"><span data-stu-id="1db18-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="1db18-177">Die Pilot-ID des Sammelanschlusses ist der Name des Wählplans, der dem entsprechenden Gateway zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1db18-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="1db18-178">Es muss sich um eine 1:1-Zuordnung handeln, wenn mehrere Wählpläne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1db18-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1db18-179">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="1db18-180">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1db18-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1db18-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db18-182">Konfigurieren von lync Server 2013-Wählplänen</span><span class="sxs-lookup"><span data-stu-id="1db18-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="1db18-183">Wenn Sie in Exchange 2007 SP1 oder in das neueste Service Pack oder Exchange 2010 integriert sind, erstellen Sie einen neuen Enterprise-VoIP-Wählplan mit einem Namen, der dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange um-Wählplans entspricht.</span><span class="sxs-lookup"><span data-stu-id="1db18-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="1db18-184">Sie müssen dies für jeden UM-Wählplan durchführen.</span><span class="sxs-lookup"><span data-stu-id="1db18-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="1db18-185">Wenn Sie die Integration in Exchange 2010 SP1 durchführen, stellen Sie sicher, dass geeignete Einstellungen für Enterprise-sprach Wählpläne auf globaler/Websiteebene oder auf Poolebene konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="1db18-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="1db18-186">Wenn Sie in Exchange 2010 SP1 integriert sind, müssen die Namen für den lync Server-Wählplan und die Exchange um-SIP-Wähleinstellungen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1db18-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="1db18-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1db18-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1db18-188"><a href="lync-server-2013-configuring-dial-plans.md">Konfigurieren von Wählplänen in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1db18-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db18-189">Führen Sie das Exchange um-integrationstool aus.</span><span class="sxs-lookup"><span data-stu-id="1db18-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="1db18-190">Führen Sie auf dem lync Server 2013 die <strong>OCSUMUtil. exe</strong>aus, die:</span><span class="sxs-lookup"><span data-stu-id="1db18-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-191">Erstellen von Kontaktobjekten für Teilnehmerzugriff und automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="1db18-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="1db18-192">Überprüft, ob ein Enterprise-VoIP-Wählplan mit einem Namen vorhanden ist, der dem FQDN des Exchange um-Wählplans entspricht.</span><span class="sxs-lookup"><span data-stu-id="1db18-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="1db18-193">Wenn Sie Exchange 2010 SP1 oder höher ausführen, müssen die Namen des Wählplans nicht übereinstimmen, und Sie können die Warnung des Tools dazu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1db18-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="1db18-194">Dieses Tool scannt die Active Directory für Exchange um-Einstellungen und ermöglicht es dem lync Server 2013-Administrator, Kontaktobjekte anzuzeigen, zu erstellen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1db18-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="1db18-195">RTCUniversalServerAdmins  <em>und </em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1db18-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="1db18-196">Zur erfolgreichen Ausführung von "ocsumutil.exe" muss der Benutzer beiden dieser Gruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="1db18-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="1db18-197">Zum Erstellen von Kontaktobjekten muss der Benutzer, der ocsumutil.exe ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1db18-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="1db18-198">Diese Berechtigungen können gewährt werden, indem das Cmdlet <STRONG>Grant-CsOUPermission</STRONG> ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1db18-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="1db18-199">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1db18-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="1db18-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="1db18-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1db18-201">Führen Sie bei Bedarf andere Enterprise-VoIP-Konfigurationsschritte aus.</span><span class="sxs-lookup"><span data-stu-id="1db18-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="1db18-202">Wenn Sie die Enterprise-VoIP-Einstellungen für Ihre Server oder Benutzer noch nicht konfiguriert haben, führen Sie eine oder mehrere der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1db18-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-203">Bereitstellen und Konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1db18-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="1db18-204">PSTN-Gateways und Vermittlungsservern</span><span class="sxs-lookup"><span data-stu-id="1db18-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="1db18-205">Definieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und ausgehenden Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="1db18-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="1db18-206">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="1db18-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="1db18-207">(Optional) Konfigurieren von Wähleinstellungen für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="1db18-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="1db18-208">Je nach den von Ihnen aktivierten Enterprise-VoIP-Features sind möglicherweise andere Konfigurationsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1db18-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="1db18-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1db18-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1db18-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1db18-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1db18-211">Siehe die Themen in den folgenden Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="1db18-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="1db18-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1db18-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="1db18-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1db18-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1db18-214">Aktivieren Sie Enterprise-VoIP-Benutzer für Exchange um.</span><span class="sxs-lookup"><span data-stu-id="1db18-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="1db18-215">Stellen Sie auf dem Exchange um-Server sicher, dass eine Unified Messaging-Postfachrichtlinie erstellt wurde und dass jeder Benutzer eine eindeutige Durchwahlnummern Zuweisung hat, und aktivieren Sie dann den Benutzer für Unified Messaging.</span><span class="sxs-lookup"><span data-stu-id="1db18-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="1db18-216">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="1db18-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="1db18-217">Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter so wird es gemacht:&quot; aktivieren <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>eines Benutzers für Unified Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="1db18-218">Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Aktivieren eines Benutzers&quot; für <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>Unified Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="1db18-219">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="1db18-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

