---
title: 'Lync Server 2013: Bereitstellungsprozess für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c36f8d3ee6e26c00e7686a72e1b68139c1b5ec29
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="80038-102">Bereitstellungsprozess für Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80038-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80038-103">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="80038-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="80038-104">In diesem Abschnitt wird die Abfolge der Schritte beschrieben, die für die Bereitstellung des lync Server 2013 Mobilitätsfeatures erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="80038-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="80038-105">Mobilitätsbereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="80038-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80038-106">Phase</span><span class="sxs-lookup"><span data-stu-id="80038-106">Phase</span></span></th>
<th><span data-ttu-id="80038-107">Schritte</span><span class="sxs-lookup"><span data-stu-id="80038-107">Steps</span></span></th>
<th><span data-ttu-id="80038-108">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="80038-108">Permissions</span></span></th>
<th><span data-ttu-id="80038-109">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="80038-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80038-110">Erstellen von DNS-Einträgen (Domain Name System)</span><span class="sxs-lookup"><span data-stu-id="80038-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="80038-111">Erstellen Sie einen internen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA-) Eintrag, um die interne AutoErmittlungsdienst-URL aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="80038-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="80038-112">Erstellen Sie einen externen DNS-CNAME-oder einen (Host-, if IPv6, AAAA)-Eintrag, um die externe AutoErmittlungsdienst-URL aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="80038-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80038-113">Domänen-Admins</span><span class="sxs-lookup"><span data-stu-id="80038-113">Domain Admins</span></span></p>
<p><span data-ttu-id="80038-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="80038-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="80038-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80038-116">Ändern von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="80038-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="80038-117">Hinzufügen von Einträgen für alternative Antragstellernamen zu folgenden Zertifikaten, um sichere Verbindungen für mobile Benutzer zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="80038-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="80038-118">Director-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="80038-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="80038-119">Front-End-Pool Zertifikat</span><span class="sxs-lookup"><span data-stu-id="80038-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="80038-120">Reverseproxyzertifikat</span><span class="sxs-lookup"><span data-stu-id="80038-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80038-121">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="80038-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="80038-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Ändern von Zertifikaten für Mobilität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80038-123">Konfigurieren des Reverseproxys</span><span class="sxs-lookup"><span data-stu-id="80038-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="80038-124">Zuweisen von aktualisierten Zertifikaten mit alternativen Antragstellernamen zum SSL-Listener (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="80038-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="80038-125">Konfigurieren Sie die Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL neu.</span><span class="sxs-lookup"><span data-stu-id="80038-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="80038-126">Stellen Sie sicher, dass für die externe lync Server 2013 Webdienste-URL auf Ihrem Front-End-Pool eine Webveröffentlichungsregel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="80038-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="80038-127">Oder:</span><span class="sxs-lookup"><span data-stu-id="80038-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="80038-128">Wenn Sie http für die anfängliche Auto Ermittlungsanforderung verwenden und keine Listen alternativer Antragstellernamen auf den Zertifikaten aktualisieren, konfigurieren Sie eine neue Webveröffentlichungsregel, oder konfigurieren Sie eine vorhandene Veröffentlichungsregel für Port 80 http neu.</span><span class="sxs-lookup"><span data-stu-id="80038-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80038-129">Lokaler Administrator</span><span class="sxs-lookup"><span data-stu-id="80038-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="80038-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80038-131">Testen der Mobilitätsbereitstellung für lync 2010 Mobile mithilfe des MCX-mobilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="80038-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="80038-132">Führen Sie <strong>Test-CsMcxP2PIM</strong> aus, um das Senden einer Chatnachricht von einer Person an eine andere zu testen.</span><span class="sxs-lookup"><span data-stu-id="80038-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="80038-133">Eine vollständige Liste der Optionen finden Sie in der Dokumentation zu lync Server-Verwaltungsshell-Cmdlets für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</span><span class="sxs-lookup"><span data-stu-id="80038-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="80038-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="80038-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="80038-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80038-136">Testen der Mobilitätsbereitstellung für lync 2013 Mobile Clients mithilfe der UCWA-Webkomponenten</span><span class="sxs-lookup"><span data-stu-id="80038-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="80038-137">Verwenden Sie das Cmdlet <strong>Test-CsUcwaConference</strong> , um zu testen und zu überprüfen, ob vordefinierte Test Benutzer oder ein paar von tatsächlichen Benutzern UCWA zum Erstellen und teilnehmen an einer Konferenz verwenden können.</span><span class="sxs-lookup"><span data-stu-id="80038-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="80038-138">Eine vollständige Liste der Optionen finden Sie in der Dokumentation zu lync Server-Verwaltungsshell-Cmdlets für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> .</span><span class="sxs-lookup"><span data-stu-id="80038-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="80038-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="80038-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="80038-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80038-141">Konfigurieren von Pushbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="80038-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="80038-142">Fügen Sie für lync Server 2013-Edgeserver einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Partnerverbund für den Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="80038-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="80038-143">Fügen Sie für lync Server 2010-Edgeserver einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Partnerverbund für den Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="80038-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="80038-144">Fügen Sie für Office Communications Server 2007 R2-Edgeserver einen Verbundpartner hinzu.</span><span class="sxs-lookup"><span data-stu-id="80038-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="80038-145">Wenn Sie Pushbenachrichtigungen über ein WLAN-Netzwerk unterstützen möchten, konfigurieren Sie eine ausgehende Firewallregel für TCP-Port 5223.</span><span class="sxs-lookup"><span data-stu-id="80038-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="80038-146">Verwenden Sie das <strong>Set-CsPushNotificationConfiguration</strong>-Cmdlet, um Pushbenachrichtigungen an den Apple Push Notification Service (APNS) und Microsoft Push Notification Service (MPNS) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="80038-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="80038-147">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="80038-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="80038-148">Verwenden Sie das <strong>Test-CsFederatedPartner</strong>-Cmdlet zum Testen der Verbundkonfiguration und das <strong>Test-CsMCXPushNotification</strong>-Cmdlet zum Testen von Pushbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="80038-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="80038-149">Push-Benachrichtigungen werden für lync 2010 Mobile Clients auf Apple-Geräten und Windows Phone verwendet.</span><span class="sxs-lookup"><span data-stu-id="80038-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="80038-150">Push-Benachrichtigung ist für lync 2013 Mobile Clients nur auf Windows Phone erforderlich</span><span class="sxs-lookup"><span data-stu-id="80038-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="80038-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="80038-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="80038-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80038-153">Konfigurieren der Mobilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="80038-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="80038-154">Verwenden Sie das Cmdlet " <strong>CsMobilityPolicy</strong> ", um Folgendes zuzulassen oder zu verweigern:</span><span class="sxs-lookup"><span data-stu-id="80038-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="80038-155">Anruf über den Arbeitsplatz</span><span class="sxs-lookup"><span data-stu-id="80038-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="80038-156">IP-Audio und IP-Video aktivieren</span><span class="sxs-lookup"><span data-stu-id="80038-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="80038-157">WiFi für IP-Audio und/oder IP-Video erforderlich</span><span class="sxs-lookup"><span data-stu-id="80038-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="80038-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="80038-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="80038-159"><a href="lync-server-2013-configuring-mobility-policy.md">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="80038-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

