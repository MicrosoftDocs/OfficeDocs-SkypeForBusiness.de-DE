---
title: Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und öffentlicher Chatnachrichten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94590e669c17328a33b8af62eda46e861aec6bdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="b4bc5-102">Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4bc5-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4bc5-103">_**Letztes Änderungsstand des Themas:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b4bc5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b4bc5-104">Mithilfe von Verbünden, Verbindungen mit öffentlichen Sofortnachrichtendiensten und XMPP (Extensible Messaging and Presence Protocol) wird eine andere Klasse externer Benutzer definiert – Verbundbenutzer.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="b4bc5-105">Benutzer einer Verbund lync Server-Bereitstellung oder der XMPP-Bereitstellung haben Zugriff auf eine beschränkte Anzahl von Diensten und werden von der externen Bereitstellung authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="b4bc5-106">Remote Benutzer sind Mitglieder ihrer lync Server-Bereitstellung und haben Zugriff auf alle Dienste, die von Ihrer Bereitstellung angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="b4bc5-107">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b4bc5-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b4bc5-108">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-108">has been announced.</span></span> <span data-ttu-id="b4bc5-109">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b4bc5-110">Die Verbindung mit öffentlichen Instant Messaging-Diensten ist ein spezieller Verbundtyp, mit dem ein lync Server-Client mit dem lync 2013 auf konfigurierte öffentliche Chatpartner zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="b4bc5-111">Die aktuellen Partner für Verbindungen mit öffentlichen Sofortnachrichtendiensten lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b4bc5-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="b4bc5-112">America Online</span><span class="sxs-lookup"><span data-stu-id="b4bc5-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="b4bc5-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="b4bc5-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="b4bc5-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="b4bc5-114">Yahoo\!</span></span>

<span data-ttu-id="b4bc5-115">Mithilfe einer Konfiguration der Verbindungen mit öffentlichen Sofortnachrichtendiensten können Lync-Benutzer wie folgt auf Benutzer von Verbindungen mit öffentlichen Sofortnachrichtendiensten zugreifen:</span><span class="sxs-lookup"><span data-stu-id="b4bc5-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="b4bc5-116">Sofortnachrichten und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="b4bc5-116">IM and Presence</span></span>

  - <span data-ttu-id="b4bc5-117">Sichtbarkeit von Kontakten für Verbindungen mit öffentlichen Sofortnachrichtendiensten im Lync-Client</span><span class="sxs-lookup"><span data-stu-id="b4bc5-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="b4bc5-118">Sofortnachrichtenunterhaltungen zwischen Personen mit Kontakten</span><span class="sxs-lookup"><span data-stu-id="b4bc5-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="b4bc5-119">Audio- und Videoanrufe mit Windows Live-Benutzern</span><span class="sxs-lookup"><span data-stu-id="b4bc5-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="b4bc5-p104">Mithilfe des Lync Server-Verbunds wird eine Vereinbarung zwischen Ihrer Lync Server-Bereitstellung und anderen Bereitstellungen von Office Communications Server 2007 R2 oder Lync Server definiert. Mithilfe einer Lync Server-Verbundkonfiguration können Lync-Benutzer wie folgt auf Verbundbenutzer zugreifen:</span><span class="sxs-lookup"><span data-stu-id="b4bc5-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="b4bc5-122">Instant Messaging und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="b4bc5-122">IM and Presence</span></span>

  - <span data-ttu-id="b4bc5-123">Erstellung von Verbundkontakten im Lync-Client</span><span class="sxs-lookup"><span data-stu-id="b4bc5-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="b4bc5-p105">Mithilfe des XMPP-Verbunds wird eine externe Bereitstellung definiert, die auf dem Extensible Messaging and Presence Protocol basiert. Mithilfe einer XMPP-Konfiguration können Lync-Benutzer wie foglt auf zulässige XMPP-Domänenbenutzer zugreifen:</span><span class="sxs-lookup"><span data-stu-id="b4bc5-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="b4bc5-126">Instant Messaging und Anwesenheit – nur zwischen Personen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="b4bc5-127">Erstellung von XMPP-Verbundkontakten im Lync-Client</span><span class="sxs-lookup"><span data-stu-id="b4bc5-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b4bc5-128">Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="b4bc5-129">Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="b4bc5-130">Externer Edgeserver-Verbund, Verbindungen für öffentliche Sofortnachrichtendienste und Bereitstellungsprozess für XMPP-Benutzer</span><span class="sxs-lookup"><span data-stu-id="b4bc5-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4bc5-131">Phase</span><span class="sxs-lookup"><span data-stu-id="b4bc5-131">Phase</span></span></th>
<th><span data-ttu-id="b4bc5-132">Schritte</span><span class="sxs-lookup"><span data-stu-id="b4bc5-132">Steps</span></span></th>
<th><span data-ttu-id="b4bc5-133">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-133">Permissions</span></span></th>
<th><span data-ttu-id="b4bc5-134">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="b4bc5-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4bc5-135">Bestimmen Sie die Optionen, die der vorhandenen Edgebereitstellung hinzugefügt werden sollen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-136">Führen Sie den Topologie-Generator aus, um Edgeserver Einstellungen zu bearbeiten und die Topologie zu erstellen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="b4bc5-137">Durch Ihre vorhandene Edge-Topologie werden Änderungen aus dem zentralen Verwaltungsspeicher in den Edgeserver repliziert.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-138">Gruppe "Domänen-Admins" und Gruppe "RTCUniversalServerAdmins"</span><span class="sxs-lookup"><span data-stu-id="b4bc5-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="b4bc5-139">Sie können eine Topologie unter Verwendung eines Kontos bearbeiten, das Mitglied der lokalen Benutzergruppe ist. Für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe "Domänen-Admins" und der Gruppe "RTCUniversalServerAdmins" ist.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="b4bc5-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge-und Director-Topologie in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bc5-141">Bereiten Sie das Setup vor</span><span class="sxs-lookup"><span data-stu-id="b4bc5-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b4bc5-142">Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-143">Konfigurieren Sie interne und externe DNS-Einträge, um die Verbindung mit öffentlichen Sofortnachrichtendiensten, Lync-Verbünde und XMPP-Verbünde zu unterstützen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-144">Konfigurieren Sie Ports und Protokolle an der Firewall für die Unterstützung der von Ihnen bereitgestellten Verbundtypen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-p108">Fordern Sie öffentliche Zertifikate an, und installieren Sie sie. Die zum Anfordern von Zertifikaten erforderliche Zeit hängt davon ab, welche Zertifizierungstelle das Zeritfikat ausstellt. Dieser Schritt ist an dieser Stelle in der Bereitstellung optional. Wenn Sie diesen Schritt nicht zu diesem Zeitpunkt ausführen, müssen Sie dies bei der Edgeserverkonfiguration tun. Der Edgeserverdienst kann erst gestartet werden, nachdem die Zertifikate angefordert wurden</span><span class="sxs-lookup"><span data-stu-id="b4bc5-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b4bc5-150">Wie für Ihre Organisation angemessen, da diese Rollen normalerweise unter zahlreichen Arbeitsgruppen aufgeteilt werden</span><span class="sxs-lookup"><span data-stu-id="b4bc5-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bc5-152">Richten Sie Edgeserver für Verbundszenarien ein</span><span class="sxs-lookup"><span data-stu-id="b4bc5-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b4bc5-153">Transportieren Sie die exportierte Topologiekonfigurationsdatei zu den einzelnen Edgeservern, oder schließen Sie die Replikation ab</span><span class="sxs-lookup"><span data-stu-id="b4bc5-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-154">Führen Sie den Bereitstellungs-Assistenten erneut aus, um Unterstützungskomponenten für den Verbund zu installieren</span><span class="sxs-lookup"><span data-stu-id="b4bc5-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-155">Konfigurieren Sie die Edgeserver</span><span class="sxs-lookup"><span data-stu-id="b4bc5-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-156">Fordern Sie für jeden Edgeserver Zertifikate an, und installieren Sie sie</span><span class="sxs-lookup"><span data-stu-id="b4bc5-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-157">Starten Sie die Edgeserverdienste neu</span><span class="sxs-lookup"><span data-stu-id="b4bc5-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b4bc5-158">Administratorgruppe</span><span class="sxs-lookup"><span data-stu-id="b4bc5-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-159"><a href="lync-server-2013-setting-up-lync-federation.md">Einrichten von lync Federation in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b4bc5-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Einrichten der Verbindung mit öffentlichen Instant Messaging-Diensten in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b4bc5-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Einrichten des XMPP-Verbunds in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bc5-162">Konfigurieren Sie die Unterstützung des externen Benutzerzugriffs.</span><span class="sxs-lookup"><span data-stu-id="b4bc5-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="b4bc5-163">Verwenden des lync Server-Systemsteuerung Zugriffs durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="b4bc5-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-164">Konfigurieren Sie die Richtlinie für den externen Zugriff, um die Kommunikation mit Verbundbenutzern oder öffentlichen Benutzern zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-165">Konfigurieren Sie SIP-Verbunddomänen für die Zulassung oder Blockierung von Domänen</span><span class="sxs-lookup"><span data-stu-id="b4bc5-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-166">Aktivieren Sie SIP-Verbundanbieter für Anbieter von Verbindungen mit öffentlichen Sofortnachrichtendiensten</span><span class="sxs-lookup"><span data-stu-id="b4bc5-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="b4bc5-167">Konfigurieren Sie XMPP-Verbundpartner nach XMPP-Domäne</span><span class="sxs-lookup"><span data-stu-id="b4bc5-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="b4bc5-168">Gruppe "RTCUniversalServerAdmins" oder Benutzerkonto, das der Rolle "CSAdministrator" zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="b4bc5-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b4bc5-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Konfigurieren der Medienverschlüsselung für öffentliche Anbieter in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bc5-171">Überprüfen Sie die Edgeserverkonfiguration</span><span class="sxs-lookup"><span data-stu-id="b4bc5-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-172">Überprüfen Sie die Serverbindung und Replikation von Konfigurationsdaten von internen Servern</span><span class="sxs-lookup"><span data-stu-id="b4bc5-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-173">Für die Überprüfung der Replikation, der Gruppe "TCUniversalServerAdmins" oder des Benutzerkontos, das der Rolle "CSAdministrator" zugeordnet ist. Für die Überprüfung der Benutzerkonnektivität, ein Benutzer für jeden Verbundbenutzertyp</span><span class="sxs-lookup"><span data-stu-id="b4bc5-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="b4bc5-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edge-Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="b4bc5-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Beispiel für eine XMPP-Konfiguration in lync Server 2013 – XMPP-Partnerverbund mit Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="b4bc5-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

