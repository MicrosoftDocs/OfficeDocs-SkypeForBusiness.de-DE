---
title: 'Lync Server 2013: Einrichten des lync-Verbund'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea596f571064a3b72ecbb3b0c2b56c2179aa315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a><span data-ttu-id="1f6bc-102">Einrichten von lync Federation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6bc-102">Setting up Lync federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f6bc-103">_**Letztes Änderungsstand des Themas:** 2014-03-27_</span><span class="sxs-lookup"><span data-stu-id="1f6bc-103">_**Topic Last Modified:** 2014-03-27_</span></span>

<span data-ttu-id="1f6bc-104">Wenn Sie bereits einen oder mehrere Edgeserver bereitgestellt haben, ist das Hinzufügen der Features für Partnerverbundszenarien ganz einfach.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-104">If you have already deployed you Edge server or servers, adding the federated scenarios features is straight forward.</span></span> <span data-ttu-id="1f6bc-105">Wenn Sie noch keine Edgeserver eingerichtet haben, müssen Sie diese Einrichtung zuerst durchführen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-105">If you have not set up Edge Servers, you must do that first.</span></span> <span data-ttu-id="1f6bc-106">Ausführliche Informationen finden Sie unter: [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-106">For details, see: [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f6bc-p102">Wenn Sie eine beliebige Kombination von XMPP-Partnerverbund, Lync-Partnerverbund oder Konnektivität mit öffentlichen Chatdiensten einrichten möchten, können Sie diese Partnerverbundtypen gleichzeitig oder nacheinander bereitstellen. Wenn Sie die Optionen über den Topologie-Generator und die Lync Server-Verwaltungsshell konfigurieren und dann den Bereitstellungs-Assistenten auf den Edgeserver ausführen, nachdem Sie die Optionen für einen, zwei oder drei Partnerverbundtypen konfiguriert haben, können Sie die Anzahl der erforderlichen Schritte reduzieren.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p102">If you intend to setup any combination of XMPP federation, Lync Federation, or public instant messaging connectivity, you can deploy them concurrently or one at a time. If you configure the options through the Topology Builder and the Lync Server Management shell, then run the Deployment Wizard at the Edge server after configuring the options for one, two or all three federation types, you can reduce the number of steps required.</span></span>



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a><span data-ttu-id="1f6bc-109">Einrichten des Lync-Partnerverbunds im Topologie-Generator und im Bereitstellungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="1f6bc-109">Setting Up Lync Federation in Topology Builder and the Deployment Wizard</span></span>

1.  <span data-ttu-id="1f6bc-p103">Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie die Edgepools, und klicken Sie dann mit der rechten Maustaste auf Ihren Edgeserver oder Edgeserverpool. Wählen Sie Eigenschaften bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p103">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="1f6bc-p104">Klicken Sie in "Eigenschaften bearbeiten" unter "Allgemein" auf "Partnerverbund für diesen Edgepool aktivieren" (Port 5061). Klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p104">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="1f6bc-p105">Klicken Sie auf "Aktion", wählen Sie "Topologie", und wählen Sie "Veröffentlichen" aus. Wenn Sie unter "Topologie veröffentlichen" dazu aufgefordert werden, klicken Sie auf "Weiter". Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf "Fertig stellen".</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p105">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="1f6bc-p106">Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p106">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="1f6bc-p107">Klicken Sie unter Lync Server-Komponenten einrichten auf Weiter. Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p107">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1f6bc-p108">Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzer öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a><span data-ttu-id="1f6bc-129">Konfigurieren des Verbunds mit Partnern</span><span class="sxs-lookup"><span data-stu-id="1f6bc-129">Configuring Federation with Partners</span></span>

1.  <span data-ttu-id="1f6bc-130">Zum Einrichten eines erfolgreichen Verbunds mit einem anderen Microsoft lync Server 2013, lync Server 2010, Office Communications Server 2007 R2 oder Office Communicator 2007 wählen Sie den Typ des Verbunds in der folgenden Tabelle aus und definieren DNS-SRV-Einträge, DNS-Host (a oder AAAA für IPv6) und Konfigurieren von Richtlinien für den Typ des Verbunds:</span><span class="sxs-lookup"><span data-stu-id="1f6bc-130">To setup a successful federation with another Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2, or Office Communicator 2007, select the type of federation from the following table and define DNS SRV records, DNS host (A or AAAA for IPv6) and configure policies applicable to the type of federation:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="1f6bc-131">Partnerverbundtyp</span><span class="sxs-lookup"><span data-stu-id="1f6bc-131">Federation type</span></span></th>
    <th><span data-ttu-id="1f6bc-132">DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="1f6bc-132">DNS Records</span></span></th>
    <th><span data-ttu-id="1f6bc-133">Richtliniendefinition</span><span class="sxs-lookup"><span data-stu-id="1f6bc-133">Policy Definition</span></span></th>
    <th><span data-ttu-id="1f6bc-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f6bc-134">Notes</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="1f6bc-135">Ermittelte Partnerdomäne</span><span class="sxs-lookup"><span data-stu-id="1f6bc-135">Discovered Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="1f6bc-136">Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, bei dem der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-136">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="1f6bc-137">&lt;externer Domänenname&gt; – der FQDN ihrer Zugriffs-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-137">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="1f6bc-138">Weitere Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1f6bc-138">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="1f6bc-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-139"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="1f6bc-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-140"><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Enable or disable discovery of federation partners in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="1f6bc-p110">In vorherigen Versionen wurde dieser Partnerverbundtyp als <strong>Offener erweiterter Partnerverbund</strong> definiert. Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp erforderlich und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p110">Previous versions referred to this type of federation as <strong>Open Enhanced Federation</strong>. The creation of the SRV record is required for this type of federation and is to allow other partners to discover your federation.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1f6bc-143">Zulässige Partnerdomäne</span><span class="sxs-lookup"><span data-stu-id="1f6bc-143">Allowed Partner Domain</span></span></p></td>
    <td><p><span data-ttu-id="1f6bc-144">Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, bei dem der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-144">Configure SRV record of the format _sipfederationtls._tcp.&lt;external domain name&gt;Where the port value for the SRV record is TCP 5061 and the <strong>Host offering this service</strong> is defined as sip.</span></span> <span data-ttu-id="1f6bc-145">&lt;externer Domänenname&gt; – der FQDN ihrer Zugriffs-Edgedienst.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-145">&lt;external domain name&gt; – the FQDN of your Access Edge service.</span></span> <span data-ttu-id="1f6bc-146">Weitere Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="1f6bc-146">See <a href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</a> for details on creating the SRV record</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="1f6bc-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-147"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="1f6bc-148">In früheren Versionen wurde dieser Typ von Verbund als <strong>Erweiterter Verbund</strong>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-148">Previous versions referred to this type of federation as <strong>Enhanced Federation</strong>.</span></span> <span data-ttu-id="1f6bc-149">Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp optional und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-149">The creation of the SRV record is optional for this type of federation and is to allow other partners to discover your federation.</span></span> <span data-ttu-id="1f6bc-150">In diesem Fall handelt es sich natürlich um einen <strong>Offenen erweiterten Partnerverbund</strong> oder eine <strong>Ermittelte Partnerdomäne</strong></span><span class="sxs-lookup"><span data-stu-id="1f6bc-150">Of course, this is then an <strong>Open Enhanced Federation</strong>, or <strong>Discovered Partner Domain</strong></span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="1f6bc-151">Zulässiger Partnerserver</span><span class="sxs-lookup"><span data-stu-id="1f6bc-151">Allowed Partner Server</span></span></p></td>
    <td><p><span data-ttu-id="1f6bc-152">Konfigurieren Sie den SIP-Domänennamen und den Partner Edgeserver FQDN als Verbundpartner in Richtlinien</span><span class="sxs-lookup"><span data-stu-id="1f6bc-152">Configure the SIP domain name and the partner Edge Server FQDN as a federation partner in Policies</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="1f6bc-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-153"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="1f6bc-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-154"><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Configure support for allowed external domains in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="1f6bc-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Konfigurieren der Unterstützung für blockierte externe Domänen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-155"><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Configure support for blocked external domains in Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="1f6bc-p113">Dieser Partnerverbundtyp ist die Definition einer 1:1-Beziehung und lässt die Ermittlung anderer Verbundpartner nicht zu. Jeder Verbundpartner wird explizit konfiguriert. In vorherigen Versionen wurde dies als <strong>Direkter Partnerverbund</strong> bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-p113">This federation type is the definition of a one to one relationship and does not allow for discovery of other federation partners. Each federation partner is configured explicitly. In previous versions, this was known as <strong>Direct Federation</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="1f6bc-159">Hostinganbieter und öffentlicher Chatanbieter</span><span class="sxs-lookup"><span data-stu-id="1f6bc-159">Hosting Provider and Public IM Provider</span></span></p></td>
    <td><p><span data-ttu-id="1f6bc-160">Für diesen Partnerverbundtyp sind keine besonderen DNS-Anforderungen definiert.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-160">No specific DNS requirements are defined for this type of federation</span></span></p></td>
    <td><ul>
    <li><p><span data-ttu-id="1f6bc-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-161"><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="1f6bc-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-162"><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</a></span></span></p></li>
    <li><p><span data-ttu-id="1f6bc-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1f6bc-163"><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Create or edit hosted SIP federated providers Lync Server 2013</a></span></span></p></li>
    </ul></td>
    <td><p><span data-ttu-id="1f6bc-164">Dieser Partnerverbundtyp definiert Dienste und Hostinganbieter, die Sie für Ihre Benutzer konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-164">This federation type defines services and hosting providers that you want to configure for your users.</span></span> <span data-ttu-id="1f6bc-165">Zu den typischen Verwendungen gehört die Konfiguration für öffentliche Chatanbieter wie Windows Live Messenger, Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1f6bc-165">Typical uses include configuration for public IM providers like Windows Live Messenger, Yahoo!</span></span> <span data-ttu-id="1f6bc-166">und AOL sowie Hosting-Anbieter wie lync Online und Office 365</span><span class="sxs-lookup"><span data-stu-id="1f6bc-166">and AOL, as well as hosting providers such as Lync Online and Office 365</span></span></p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="1f6bc-167">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-167">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1f6bc-168">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-168">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1f6bc-169">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-169">Messenger until the service shut down date.</span></span> <span data-ttu-id="1f6bc-170">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1f6bc-170">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1f6bc-171">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-171">has been announced.</span></span> <span data-ttu-id="1f6bc-172">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-172">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1f6bc-173">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-173">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1f6bc-174">Messenger.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-174">Messenger.</span></span> <span data-ttu-id="1f6bc-175">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-175">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="1f6bc-176">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-176">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1f6bc-177">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-177">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1f6bc-178">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-178">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  <span data-ttu-id="1f6bc-179">Definieren und Konfigurieren von erforderlichen DNS-Hosteinträgen (A oder AAAA für IPv6) und DNS-SRV-Einträgen</span><span class="sxs-lookup"><span data-stu-id="1f6bc-179">Define and configure any required DNS host (A or AAAA for IPv6) and DNS SRV records</span></span>

3.  <span data-ttu-id="1f6bc-180">Definieren und konfigurieren Sie alle Richtlinien mithilfe der lync Server-Systemsteuerung oder mithilfe der lync Server-Verwaltungsshell und der entsprechenden Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-180">Define and configure any policies using the Lync Server Control Panel or by using the Lync Server Management Shell and the appropriate cmdlets.</span></span> <span data-ttu-id="1f6bc-181">Ausführliche Informationen zu den lync Server-Verwaltungsshell-Cmdlets finden Sie unter [Verbund-und externer Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span><span class="sxs-lookup"><span data-stu-id="1f6bc-181">For details on the Lync Server Management Shell cmdlets, see [Federation and external access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f6bc-182">Lync Room System (LRS) zeigt keine Verknüpfungsschaltfläche für Besprechungen an, die von Organisatoren in Partner-lync-Partnern gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-182">Lync Room System (LRS) does not show join button for meetings sent by organizers in federated Lync partners.</span></span> <span data-ttu-id="1f6bc-183">Damit ein Link zum besprechungsbeitritt auf dem LRS angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Cmdlets aktivieren:</span><span class="sxs-lookup"><span data-stu-id="1f6bc-183">For a meeting join link to appear on LRS, the sending organization must enable TNEF by using the following cmdlet:</span></span><BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR><span data-ttu-id="1f6bc-184">Beachten Sie, dass dies nicht LRS-spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-184">Note that this is not LRS specific.</span></span> <span data-ttu-id="1f6bc-185">Outlook und lync würden auch in diesem Fall keine Verknüpfungs Verknüpfungen anzeigen, da MAPI-Eigenschaften nicht transportiert werden, aber im Fall von Outlook kann der Benutzer die Besprechungseinladung öffnen und auf die Besprechungs-URL klicken.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-185">Outlook and Lync would also not show Join links in this case as MAPI properties are not transported, but in the Outlook case, the user can open up the meeting invite and click on the meeting URL.</span></span> <span data-ttu-id="1f6bc-186">Wenn TNEFEnabled auf true festgelegt ist Exchange 2013 keine MAPI-Eigenschaften einschließlich OnlineMeetingExternalLink, und die Schaltfläche beitreten wird in der Erinnerung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f6bc-186">When TNEFEnabled is set to true Exchange 2013 does not strip MAPI properties including OnlineMeetingExternalLink and the Join button will be shown on the reminder.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f6bc-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f6bc-187">See Also</span></span>


[<span data-ttu-id="1f6bc-188">Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6bc-188">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[<span data-ttu-id="1f6bc-189">Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f6bc-189">Managing federation and external access to Lync Server 2013</span></span>](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

