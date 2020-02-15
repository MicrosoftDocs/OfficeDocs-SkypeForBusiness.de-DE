---
title: Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Funktionen
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
ms.openlocfilehash: cbef561e7b2c4edd3e38f028bdbdcdfbe246d036
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="9da02-102">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-und lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da02-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da02-103">_**Letztes Änderungsstand des Themas:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="9da02-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="9da02-104">Wenn Sie Exchange Unified Messaging (um) mit lync Server 2013 integrieren möchten, müssen Sie die in diesem Thema beschriebenen Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="9da02-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="9da02-105">Stellen Sie außerdem sicher, dass Sie die in [Richtlinien für die Integration lokaler Unified Messaging und lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)beschriebenen bewährten Methoden für die Planung und Bereitstellung lesen.</span><span class="sxs-lookup"><span data-stu-id="9da02-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="9da02-106">In diesem Thema wird davon ausgegangen, dass Sie lync Server 2013 mit einem zusammengefassten Vermittlungsserver bereitgestellt haben und Benutzer für lync Server 2013 aktiviert haben, aber nicht unbedingt, dass Sie alle Bereitstellungs-und Konfigurationsschritte zur Aktivierung von Enterprise-VoIP ausgeführt haben, wie unter [Deploying Enterprise Voice in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9da02-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="9da02-107">Integrationsprozess für Unified Messaging (UM)</span><span class="sxs-lookup"><span data-stu-id="9da02-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9da02-108">Es ist wichtig, dass Sie sich mit den Exchange-Administratoren Ihrer Organisation abstimmen, um die Aufgaben zu bestätigen, die von Ihnen durchgeführt werden, um eine reibungslose und erfolgreiche Integration zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9da02-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="9da02-109">Phase</span><span class="sxs-lookup"><span data-stu-id="9da02-109">Phase</span></span></th>
<th><span data-ttu-id="9da02-110">Schritte</span><span class="sxs-lookup"><span data-stu-id="9da02-110">Steps</span></span></th>
<th><span data-ttu-id="9da02-111">Erforderliche Gruppen und Rollen</span><span class="sxs-lookup"><span data-stu-id="9da02-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="9da02-112">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="9da02-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9da02-113">Stellen Sie eine der folgenden Exchange-Versionen bereit:</span><span class="sxs-lookup"><span data-stu-id="9da02-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="9da02-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="9da02-115">Microsoft Exchange Server 2010 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="9da02-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="9da02-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da02-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9da02-117">Wenn Sie Microsoft Exchange Server 2013 verwenden, installieren Sie die folgenden Exchange Server Rollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9da02-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-118">Clientzugriff</span><span class="sxs-lookup"><span data-stu-id="9da02-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="9da02-119">Postfach</span><span class="sxs-lookup"><span data-stu-id="9da02-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="9da02-120">Wenn Microsoft Exchange Server 2013 und Exchange Unified Messaging (um) in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur vertraut.</span><span class="sxs-lookup"><span data-stu-id="9da02-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="9da02-121">Wenn Sie Exchange 2010 verwenden, installieren Sie die folgenden Exchange Server Rollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9da02-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-122">Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="9da02-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="9da02-123">Hub-Transport</span><span class="sxs-lookup"><span data-stu-id="9da02-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="9da02-124">Clientzugriff</span><span class="sxs-lookup"><span data-stu-id="9da02-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="9da02-125">Postfach</span><span class="sxs-lookup"><span data-stu-id="9da02-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="9da02-126">Wenn lync Server 2013 und Exchange Unified Messaging (um) in unterschiedlichen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013 Gesamtstruktur vertraut.</span><span class="sxs-lookup"><span data-stu-id="9da02-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="9da02-127">Organisations-Admins (wenn es sich um den ersten Exchange Server in der Organisation handelt)</span><span class="sxs-lookup"><span data-stu-id="9da02-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="9da02-128">oder -</span><span class="sxs-lookup"><span data-stu-id="9da02-128">-OR-</span></span></p>
<p><span data-ttu-id="9da02-129">Exchange-Organisationsadministrator (wenn es sich nicht um den ersten Exchange Server in der Organisation handelt)</span><span class="sxs-lookup"><span data-stu-id="9da02-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="9da02-130">Weitere Informationen finden Sie in der Dokumentation zur jeweiligen Version von Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="9da02-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="9da02-131">Exchange Server 2007 Bereitstellungsdokumentation <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="9da02-132">Exchange Server 2010 oder neueste Service Pack-Bereitstellungs <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="9da02-133">Microsoft Exchange Server 2013 Planung und Bereitstellung <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>bei.</span><span class="sxs-lookup"><span data-stu-id="9da02-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da02-134">Installieren Sie Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="9da02-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="9da02-135">Herunterladen und Installieren von Zertifikaten für jeden Exchange um Server von einer vertrauenswürdigen Stammzertifizierungsstelle (Certification Authority, ca).</span><span class="sxs-lookup"><span data-stu-id="9da02-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="9da02-136">Die Zertifikate sind für MTLS (Mutual Transport Level Security) zwischen den Servern mit Exchange um und lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9da02-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="9da02-137">Administratoren</span><span class="sxs-lookup"><span data-stu-id="9da02-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="9da02-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft</a></span><span class="sxs-lookup"><span data-stu-id="9da02-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da02-139">Erstellen und konfigurieren Sie einen neuen Exchange um SIP-Wähleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9da02-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="9da02-140">Erstellen Sie auf dem Exchange um Server einen SIP-Wählplan basierend auf den spezifischen Bereitstellungsanforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9da02-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="9da02-141">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="9da02-142">Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden &quot;Sie unter Erstellen eines Unified Messaging-SIP-URI&quot; - <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>Wähl Plans unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="9da02-143">Informationen zum Exchange 2010 oder neuesten Service Pack finden &quot;Sie unter Erstellen eines um&quot; - <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>Wähl Plans unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="9da02-144">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da02-145">Konfigurieren Sie Sicherheitseinstellungen für den Exchange um SIP-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="9da02-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="9da02-146">Um Enterprise-VoIP-Datenverkehr zu verschlüsseln, konfigurieren Sie die Sicherheitseinstellungen im Exchange um SIP-Wählplan als <strong>SIP-gesichert</strong> oder <strong>abgesichert</strong>.</span><span class="sxs-lookup"><span data-stu-id="9da02-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="9da02-147">Dies ist ein besonders wichtiger Schritt, wenn Sie lync Phone Edition-Geräte in Ihrer Umgebung bereitgestellt oder geplant haben.</span><span class="sxs-lookup"><span data-stu-id="9da02-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="9da02-148">Damit lync Phone Edition-Geräte in einer Umgebung mit Exchange um Integration funktionieren, müssen lync Server Verschlüsselungseinstellungen mit den Sicherheitseinstellungen für den Exchange um Wählplan übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9da02-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="9da02-149">Ausführliche Informationen zu diesem Thema finden Sie in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9da02-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="9da02-150">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="9da02-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9da02-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="9da02-152">Informationen zu Exchange 2007 SP1 oder zum neuesten Service Pack finden Sie unter auch:</span><span class="sxs-lookup"><span data-stu-id="9da02-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="9da02-153">&quot;Konfigurieren der Sicherheit für einen Unified Messaging-Wählplan&quot; unter. <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a></span><span class="sxs-lookup"><span data-stu-id="9da02-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="9da02-154">Informationen zu Exchange 2010 oder neuestes Service Pack finden Sie auch hier:</span><span class="sxs-lookup"><span data-stu-id="9da02-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="9da02-155">&quot;Konfigurieren Sie VoIP&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>-Sicherheit für einen um-Wählplan.</span><span class="sxs-lookup"><span data-stu-id="9da02-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="9da02-156">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da02-157">Fügen Sie dem Exchange um SIP-Wähleinstellungen Unified Messaging-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="9da02-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="9da02-158">Wenn Sie einen neu installierten Unified Messaging-Server zur Entgegennahme und Verarbeitung eingehender Anrufe aktivieren möchten, müssen Sie den Unified Messaging-Server einem Satz mit UM-Wähleinstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9da02-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="9da02-159">In diesem Fall fügen Sie den Server dem Exchange um SIP-Wähleinstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="9da02-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="9da02-160">Administratoren</span><span class="sxs-lookup"><span data-stu-id="9da02-160">Administrators</span></span></p>
<p><span data-ttu-id="9da02-161">Exchange-Serveradministratoren</span><span class="sxs-lookup"><span data-stu-id="9da02-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="9da02-162">Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden &quot;Sie unter Hinzufügen von Unified Messaging-Server zu&quot; Wähl <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>Einstellungen unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="9da02-163">Informationen zum Exchange 2010 oder neuesten Service Pack finden &quot;Sie unter Anzeigen oder Konfigurieren der Eigenschaften eines um&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>-Servers unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="9da02-164">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da02-165">Konfigurieren Sie Postfächer mit SIP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="9da02-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="9da02-166">Weisen Sie den Postfächern von Enterprise-VoIP-Benutzern, die Exchange um-Features verwenden werden, SIP-Adressen zu.</span><span class="sxs-lookup"><span data-stu-id="9da02-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="9da02-167">Lync Server 2013 Administrator</span><span class="sxs-lookup"><span data-stu-id="9da02-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="9da02-168">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="9da02-169">Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden &quot;Sie unter Hinzufügen, entfernen oder Ändern einer SIP-Adresse für einen um-aktivierten&quot; Benutzer <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="9da02-170">Informationen zum Exchange 2010 oder neuesten Service Pack finden &quot;Sie unter Ändern einer SIP-Adresse für einen um&quot; - <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>aktivierten Benutzer unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="9da02-171">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da02-172">Führen Sie das Skript "exchucutil.ps1" aus.</span><span class="sxs-lookup"><span data-stu-id="9da02-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="9da02-173">Öffnen Sie auf dem Server, auf dem Exchange um Dienste ausgeführt werden, das Exchange-Verwaltungsshell, und führen Sie das Skript "exchucutil. ps1-Skript aus, das Folgendes ausführt:</span><span class="sxs-lookup"><span data-stu-id="9da02-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-174">Erteilt lync Server 2013 Berechtigung zum Lesen von Exchange um Active Directory-Domänendienste-Objekten, insbesondere die SIP-Wählpläne, die in der vorherigen Aufgabe erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9da02-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="9da02-175">Erstellt ein Unified Messaging-IP-Gateway-Objekt in Active Directory für jeden lync Server 2013 Enterprise Edition-Pool oder Standard Edition-Server, der Benutzer hostet, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="9da02-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="9da02-176">Erstellt für jedes Gateway eine Exchange um Sammelanschluss Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9da02-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="9da02-177">Die Pilot-ID des Sammelanschlusses ist der Name der Wähleinstellungen, die dem entsprechenden Gateway zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9da02-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="9da02-178">Es muss sich um eine 1:1-Zuordnung handeln, wenn mehrere Sätze mit Wähleinstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9da02-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9da02-179">Exchange-Organisationsadministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="9da02-180">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="9da02-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging für Microsoft Exchange für lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9da02-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da02-182">Konfigurieren von lync Server 2013 Wählplänen</span><span class="sxs-lookup"><span data-stu-id="9da02-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="9da02-183">Wenn Sie in Exchange 2007 SP1 oder das neueste Service Pack oder Exchange 2010 integrieren möchten, erstellen Sie einen neuen Enterprise-VoIP-Wählplan mit einem Namen, der dem vollqualifizierten Domänennamen (FQDN) des Exchange um Wähl Plans entspricht.</span><span class="sxs-lookup"><span data-stu-id="9da02-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="9da02-184">Dies müssen Sie für die einzelnen um-Wähleinstellungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="9da02-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="9da02-185">Wenn Sie in Exchange 2010 SP1 integrieren, müssen Sie sicherstellen, dass geeignete Einstellungen für Enterprise-VoIP-Unternehmen auf globaler/Standortebene oder auf Poolebene konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="9da02-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="9da02-186">Wenn Sie in Exchange 2010 SP1 integrieren, müssen die lync Server Wähleinstellungen und Exchange um Namen für den SIP-Wählplan nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9da02-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="9da02-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9da02-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9da02-188"><a href="lync-server-2013-configuring-dial-plans.md">Konfigurieren von Wählplänen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9da02-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da02-189">Führen Sie das Exchange um-integrationstool aus.</span><span class="sxs-lookup"><span data-stu-id="9da02-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="9da02-190">Führen Sie auf der lync Server 2013 <strong>OCSUMUtil. exe</strong>aus, die:</span><span class="sxs-lookup"><span data-stu-id="9da02-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-191">Erstellen von Kontaktobjekten für Teilnehmerzugriff und automatische Telefonzentrale.</span><span class="sxs-lookup"><span data-stu-id="9da02-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="9da02-192">Überprüft, ob ein Enterprise-VoIP-Wählplan mit einem Namen vorhanden ist, der mit dem FQDN des Exchange um Wähl Plans übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9da02-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="9da02-193">Wenn Sie Exchange 2010 SP1 oder höher ausführen, müssen die Namen der Wähleinstellungen nicht übereinstimmen, und Sie können die Warnung des Tools zu diesem Thema ignorieren.</span><span class="sxs-lookup"><span data-stu-id="9da02-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="9da02-194">Dieses Tool scannt die Active Directory auf Exchange um Einstellungen und ermöglicht es dem lync Server 2013 Administrator, Kontaktobjekte anzuzeigen, zu erstellen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9da02-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="9da02-195">RTCUniversalServerAdmins <em>und</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9da02-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="9da02-196">Zur erfolgreichen Ausführung von "ocsumutil.exe" muss der Benutzer beiden dieser Gruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="9da02-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="9da02-197">Zum Erstellen von Kontaktobjekten muss der Benutzer, der "ocsumutil.exe" ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9da02-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="9da02-198">Diese Berechtigung kann durch Ausführen des Cmdlets <STRONG>Grant-CsOUPermission</STRONG> erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9da02-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="9da02-199">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="9da02-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="9da02-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="9da02-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da02-201">Führen Sie bei Bedarf weitere Schritte zur Enterprise-VoIP-Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="9da02-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="9da02-202">Wenn Sie nicht bereits Enterprise-VoIP-Einstellungen für Ihre Server oder Benutzer konfiguriert haben, führen Sie eine oder mehrere der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9da02-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-203">Bereitstellen und konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9da02-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="9da02-204">PSTN-Gateways (Public Switched Telephone Network) und Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="9da02-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="9da02-205">Definieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und ausgehenden Anrufrouten</span><span class="sxs-lookup"><span data-stu-id="9da02-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="9da02-206">Aktivieren von Benutzern für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="9da02-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="9da02-207">(Optional) Konfigurieren von Wähleinstellungen für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="9da02-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="9da02-208">Je nach aktivierten Enterprise-VoIP-Funktionen ist möglicherweise die Ausführung weiterer Konfigurationsschritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9da02-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="9da02-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9da02-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="9da02-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9da02-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9da02-211">Siehe die Themen in den folgenden Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="9da02-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da02-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9da02-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="9da02-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9da02-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da02-214">Aktivieren Sie Enterprise-VoIP-Benutzer für Exchange um.</span><span class="sxs-lookup"><span data-stu-id="9da02-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="9da02-215">Stellen Sie auf dem Exchange um Server sicher, dass eine Unified Messaging-Postfachrichtlinie erstellt wurde und dass jeder Benutzer über eine eindeutige Durchwahlnummer verfügt, und aktivieren Sie dann den Benutzer für Unified Messaging.</span><span class="sxs-lookup"><span data-stu-id="9da02-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="9da02-216">Exchange-Empfängeradministrator</span><span class="sxs-lookup"><span data-stu-id="9da02-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="9da02-217">Informationen zum Exchange 2007 SP1 oder neuesten Service Pack finden &quot;Sie unter Aktivieren eines Benutzers für Unified Messaging&quot; unter <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="9da02-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="9da02-218">Informationen zum Exchange 2010 oder neuesten Service Pack finden &quot;Sie unter Aktivieren eines Benutzers für&quot; Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="9da02-219">Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</span><span class="sxs-lookup"><span data-stu-id="9da02-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

