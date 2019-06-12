---
title: 'Lync Server 2013: Einrichten eines Lync-Partnerverbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="4aa04-102">Einrichten eines Lync-Partnerverbunds in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa04-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aa04-103">_**Letztes Änderungsdatum des Themas:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="4aa04-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="4aa04-104">Wenn Sie bereits Edgeserver oder Server bereitgestellt haben, ist das Hinzufügen der Features für Verbundszenarien direkt.</span><span class="sxs-lookup"><span data-stu-id="4aa04-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="4aa04-105">Wenn Sie keine Edgeserver eingerichtet haben, müssen Sie dies zunächst tun.</span><span class="sxs-lookup"><span data-stu-id="4aa04-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="4aa04-106">Ausführliche Informationen finden Sie unter: [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4aa04-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4aa04-107">Wenn Sie beabsichtigen, eine beliebige Kombination aus XMPP-Föderation, lync-Föderation oder öffentlicher Instant Messaging-Konnektivität einzurichten, können Sie Sie gleichzeitig oder einzeln bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-107">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time.</span></span> <span data-ttu-id="4aa04-108">Wenn Sie die Optionen über den Topologie-Generator und die lync Server-Verwaltungsshell konfigurieren und dann den Bereitstellungs-Assistenten auf dem Edgeserver ausführen, nachdem Sie die Optionen für einen, zwei oder alle drei Föderations Typen konfiguriert haben, können Sie die Anzahl der erforderlichen Schritte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="4aa04-108">If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="4aa04-109">Einrichten von lync Federation im Topologie-Generator und im Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4aa04-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="4aa04-110">Öffnen Sie auf einem Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="4aa04-110">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="4aa04-111">Erweitern Sie Edge-Pools, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edge-Serverpool.</span><span class="sxs-lookup"><span data-stu-id="4aa04-111">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="4aa04-112">Wählen Sie Eigenschaften bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="4aa04-112">Select Edit properties.</span></span>

2.  <span data-ttu-id="4aa04-113">Wählen Sie in Eigenschaften bearbeiten unter Allgemein die Option Föderation für diesen Edge-Pool aktivieren (Port 5061) aus.</span><span class="sxs-lookup"><span data-stu-id="4aa04-113">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="4aa04-114">Klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="4aa04-114">Click OK.</span></span>

3.  <span data-ttu-id="4aa04-115">Klicken Sie auf Aktion, wählen Sie Topologie aus, und wählen Sie veröffentlichen aus.</span><span class="sxs-lookup"><span data-stu-id="4aa04-115">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="4aa04-116">Wenn Sie dazu aufgefordert werden, die Topologie zu veröffentlichen, klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="4aa04-116">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="4aa04-117">Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-117">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="4aa04-118">Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4aa04-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="4aa04-119">Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-119">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="4aa04-120">Klicken Sie erneut auf ausführen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-120">Click Run Again.</span></span>

5.  <span data-ttu-id="4aa04-121">Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="4aa04-121">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="4aa04-122">Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4aa04-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="4aa04-123">Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-123">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="4aa04-124">Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-124">Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4aa04-125">Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="4aa04-125">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="4aa04-126">Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="4aa04-126">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="4aa04-127">Wenn Ihre Bereitstellung beispielsweise einen Edge-Pool oder einen einzelnen Edgeserver umfasst, der in New York bereitgestellt und in London bereitgestellt wurde, und Sie die Unterstützung der Föderation auf dem New York Edge-Pool oder einem Single Edge-Server aktivieren, wird der Signal Verkehr für verbundene Benutzer durch das New York durchlaufen. Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="4aa04-127">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="4aa04-128">Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aa04-128">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="4aa04-129">Konfigurieren des Verbunds mit Partnern</span><span class="sxs-lookup"><span data-stu-id="4aa04-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="4aa04-130">Wenn Sie einen erfolgreichen Verbund mit einem anderen Microsoft lync Server 2013, lync Server 2010, Office Communications Server 2007 R2 oder Office Communicator 2007 einrichten möchten, wählen Sie den Typ des Verbandes aus der folgenden Tabelle aus, und definieren Sie DNS-SRV-Einträge, DNS-Host (a oder AAAA für IPv6) und Konfigurieren von Richtlinien, die für den Typ des Verbandes gelten:</span><span class="sxs-lookup"><span data-stu-id="4aa04-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4aa04-131">Föderations</span><span class="sxs-lookup"><span data-stu-id="4aa04-131">Federation type</span></span></th>
    <th><span data-ttu-id="4aa04-132">DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="4aa04-132">DNS Records</span></span></th>
    <th><span data-ttu-id="4aa04-133">Richtlinien Definition</span><span class="sxs-lookup"><span data-stu-id="4aa04-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="4aa04-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4aa04-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4aa04-135">Erkannte Partner Domäne</span><span class="sxs-lookup"><span data-stu-id="4aa04-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="4aa04-136">Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, wobei der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4aa04-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="4aa04-137">&lt;externer Domänenname&gt; – der FQDN Ihres Access Edge-Diensts.</span><span class="sxs-lookup"><span data-stu-id="4aa04-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="4aa04-138">Details zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4aa04-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="4aa04-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="4aa04-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="4aa04-141">Frühere Versionen verweisen auf diesen Typ von Federation als <strong>Open Enhanced Federation</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aa04-141">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>.</span></span> <span data-ttu-id="4aa04-142">Die Erstellung des SRV-Eintrags ist für diesen Föderations erforderlich und ermöglicht es anderen Partnern, ihre Föderation zu entdecken.</span><span class="sxs-lookup"><span data-stu-id="4aa04-142">The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4aa04-143">Zulässige Partner Domäne</span><span class="sxs-lookup"><span data-stu-id="4aa04-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="4aa04-144">Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, wobei der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4aa04-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="4aa04-145">&lt;externer Domänenname&gt; – der FQDN Ihres Access Edge-Diensts.</span><span class="sxs-lookup"><span data-stu-id="4aa04-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="4aa04-146">Details zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="4aa04-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="4aa04-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="4aa04-148">In früheren Versionen wurde dieser Typ von Federation als <strong>Enhanced Federation</strong>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4aa04-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="4aa04-149">Die Erstellung des SRV-Eintrags ist für diesen Föderations optional und ermöglicht es anderen Partnern, ihre Föderation zu entdecken.</span><span class="sxs-lookup"><span data-stu-id="4aa04-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="4aa04-150">Selbstverständlich handelt es sich hierbei um eine <strong>offene erweiterte Föderation</strong>oder um eine <strong>erkannte Partner Domäne</strong> .</span><span class="sxs-lookup"><span data-stu-id="4aa04-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4aa04-151">Zulässiger Partner Server</span><span class="sxs-lookup"><span data-stu-id="4aa04-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="4aa04-152">Konfigurieren des SIP-Domänennamens und des Partner-Edgeserver-FQDN als Verbundpartner in Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4aa04-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="4aa04-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="4aa04-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="4aa04-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="4aa04-156">Bei diesem Verbundtyp handelt es sich um die Definition einer 1:1-Beziehung, die keine Ermittlung anderer Verbundpartner ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4aa04-156">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners.</span></span> <span data-ttu-id="4aa04-157">Jeder Föderationspartner wird explizit konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4aa04-157">Each federation partner is configured explicitly.</span></span> <span data-ttu-id="4aa04-158">In früheren Versionen wurde dies als <strong>direkte Föderation</strong> bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4aa04-158">In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4aa04-159">Hostinganbieter und Anbieter von öffentlichen Chats</span><span class="sxs-lookup"><span data-stu-id="4aa04-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="4aa04-160">Für diese Art von Föderation sind keine spezifischen DNS-Anforderungen definiert.</span><span class="sxs-lookup"><span data-stu-id="4aa04-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="4aa04-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="4aa04-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="4aa04-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4aa04-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="4aa04-164">Dieser Verbundtyp definiert Dienste und Hosting-Anbieter, die Sie für Ihre Benutzer konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4aa04-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="4aa04-165">Typische Verwendungen sind die Konfiguration für öffentliche Chat-Anbieter wie Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4aa04-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="4aa04-166">und AOL sowie Hosting-Anbieter wie lync Online und Office 365</span><span class="sxs-lookup"><span data-stu-id="4aa04-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="4aa04-167">Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4aa04-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4aa04-168">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="4aa04-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4aa04-169">Messenger, bis der Dienst das Datum beendet hat.</span><span class="sxs-lookup"><span data-stu-id="4aa04-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="4aa04-170">Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4aa04-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4aa04-171">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="4aa04-171">has been announced.</span></span> <span data-ttu-id="4aa04-172">Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4aa04-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="4aa04-173">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4aa04-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4aa04-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="4aa04-174">Messenger.</span></span> <span data-ttu-id="4aa04-175">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</span><span class="sxs-lookup"><span data-stu-id="4aa04-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="4aa04-176">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="4aa04-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4aa04-177">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4aa04-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4aa04-178">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="4aa04-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="4aa04-179">Definieren und Konfigurieren aller erforderlichen DNS-Hosts (A oder AAAA für IPv6) und DNS-SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="4aa04-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="4aa04-180">Definieren und konfigurieren Sie alle Richtlinien mithilfe der lync Server-Systemsteuerung oder mithilfe der lync Server-Verwaltungsshell und der entsprechenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="4aa04-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="4aa04-181">Ausführliche Informationen zu den Cmdlets der lync Server-Verwaltungsshell finden Sie unter [Föderations-und externe Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="4aa04-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aa04-182">Lync Room System (LRS) zeigt die Schaltfläche "Verknüpfung" nicht für Besprechungen an, die von Organisatoren in verbundenen lync-Partnern gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="4aa04-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="4aa04-183">Damit ein Besprechungs Verknüpfungs Link auf LRS angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Cmdlets aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4aa04-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="4aa04-184">Beachten Sie, dass dies nicht LRS-spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="4aa04-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="4aa04-185">Outlook und lync würden in diesem Fall auch keine Verknüpfungs Verknüpfungen anzeigen, da MAPI-Eigenschaften nicht transportiert werden, aber im Fall von Outlook kann der Benutzer die Besprechungseinladung öffnen und auf die Besprechungs-URL klicken.</span><span class="sxs-lookup"><span data-stu-id="4aa04-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="4aa04-186">Wenn TNEFEnabled auf true festgelegt ist, werden in Exchange 2013 keine MAPI-Eigenschaften wie OnlineMeetingExternalLink und die Schaltfläche "beitreten" auf der Erinnerung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4aa04-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4aa04-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4aa04-187">See Also</span></span>


[<span data-ttu-id="4aa04-188">Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa04-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="4aa04-189">Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aa04-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

