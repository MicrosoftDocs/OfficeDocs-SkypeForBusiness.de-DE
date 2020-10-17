---
title: 'Lync Server 2013: Ausfall Sicherheitslösungen für Zweigstellenstandorte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25541f7681ece7b299d6e4c8076fb190382650ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512982"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="4e794-102">Ausfall Sicherheitslösungen für Zweigstellenstandorte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e794-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e794-103">_**Letztes Änderungsstand des Themas:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="4e794-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="4e794-104">Das Bereitstellen von Ausfallsicherheit für Zweigstellenstandorte bietet offensichtliche Vorteile.</span><span class="sxs-lookup"><span data-stu-id="4e794-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="4e794-105">Insbesondere wenn Sie die Verbindung mit dem zentralen Standort verlieren, verfügen die Zweigstellenbenutzer weiterhin über Enterprise-VoIP-Dienst und Voicemail (wenn Sie Einstellungen für die Umleitung von Voicemail konfigurieren; Weitere Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="4e794-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="4e794-106">Für Standorte mit weniger als 25 Benutzern ist die Implementierung einer Ausfallsicherheitslösung jedoch möglicherweise nicht ausreichend rentabel.</span><span class="sxs-lookup"><span data-stu-id="4e794-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="4e794-p102">Wenn Sie sich zur Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte entschließen, haben Sie drei Möglichkeiten. Entscheiden Sie mithilfe der folgenden Tabelle, welche Option für Sie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4e794-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e794-109">Situation</span><span class="sxs-lookup"><span data-stu-id="4e794-109">If you…</span></span></th>
<th><span data-ttu-id="4e794-110">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="4e794-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e794-111">Host mit 25 bis 1.000 Benutzern am Zweigstellenstandort, wobei eine vollständige Bereitstellung nicht rentabel ist oder kein administrativer Support zur Verfügung steht</span><span class="sxs-lookup"><span data-stu-id="4e794-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="4e794-112">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4e794-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="4e794-113">Das Survivable Branch Appliance ist ein Industriestandard-Blade-Server mit einer lync Server Registrierungsstelle und Vermittlungsserver, die auf Windows Server 2008 R2 läuft.</span><span class="sxs-lookup"><span data-stu-id="4e794-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="4e794-114">Das Survivable Branch Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="4e794-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="4e794-115">Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im Programm zur SBA-Qualifizierung/-Zertifizierung) bieten bei einem WAN-Ausfall eine dauerhafte PSTN-Verbindung (Public Switched Telephone Network, Telefonfestnetz), es werden jedoch keine ausfallsicheren Anwesenheits- und Konferenzfeatures bereitgestellt, da diese Features von den Front-End-Servern am zentralen Standort abhängen.</span><span class="sxs-lookup"><span data-stu-id="4e794-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="4e794-116">Ausführliche Informationen zu Survivable Branch Appliances finden Sie unter &quot; Survivable Branch Appliance Details &quot; weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4e794-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="4e794-117"><strong>Hinweis:</strong> Wenn Sie sich entscheiden, auch einen SIP-Trunk mit Ihrem Survivable Branch Appliance zu verwenden, wenden Sie sich an Ihren Survivable Branch Appliance-Anbieter, um zu erfahren, welcher Dienstanbieter am besten für Ihre Organisation geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4e794-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e794-118">Host zwischen 1000 und 2000 Benutzern an Ihrem Zweigstellenstandort, keine ausfallsichere WAN-Verbindung, und Sie haben lync Server Administratoren zur Verfügung gestellt</span><span class="sxs-lookup"><span data-stu-id="4e794-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="4e794-119">Survivable Branch Server oder zwei Survivable Branch Appliances.</span><span class="sxs-lookup"><span data-stu-id="4e794-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="4e794-120">Bei der Survivable Branch Server handelt es sich um eine Windows Server-Sitzung, für die die Hardwareanforderungen festgelegt sind, auf denen lync Server Registrierungsstelle und Vermittlungsserver Software installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4e794-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="4e794-121">Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="4e794-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="4e794-122">Ausführliche Informationen zu Survivable Branch-Servern finden Sie unter &quot; Survivable Branch Server Details &quot; weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="4e794-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e794-123">Wenn Sie zusätzlich zu den VoIP-Funktionen für bis zu 5000 Benutzer Anwesenheits-und Konferenzfunktionen benötigen und lync Server Administratoren verfügbar gemacht haben</span><span class="sxs-lookup"><span data-stu-id="4e794-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="4e794-124">Führen Sie statt einer Zweigstellenbereitstellung eine Bereitstellung als zentraler Standort mit einem Standard Edition-Server durch.</span><span class="sxs-lookup"><span data-stu-id="4e794-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="4e794-125">Eine umfassende lync Server-Bereitstellung bietet eine durchgehende PSTN-Verbindung und eine belastbare Anwesenheits-und Konferenzfunktion bei einem WAN-Ausfall.</span><span class="sxs-lookup"><span data-stu-id="4e794-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="4e794-126">Ausführliche Informationen zur Vorbereitung dieser Lösung finden Sie unter <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">bestimmen der Systemanforderungen für lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">bestimmen der Infrastrukturanforderungen für lync Server 2013</a>und anderer relevanter Abschnitte der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4e794-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="4e794-127">Topologien zur Bereitstellung von Ausfallsicherheit</span><span class="sxs-lookup"><span data-stu-id="4e794-127">Resiliency Topologies</span></span>

<span data-ttu-id="4e794-128">Die folgende Abbildung zeigt die empfohlenen Topologien zum Gewährleisten von Ausfallsicherheit für einen Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="4e794-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="4e794-129">**Optionen für die Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte**</span><span class="sxs-lookup"><span data-stu-id="4e794-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="4e794-130">![Optionen für die Ausfallsicherheit von VoIP-Zweigstellen](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Optionen für die Ausfallsicherheit von VoIP-Zweigstellen")</span><span class="sxs-lookup"><span data-stu-id="4e794-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="4e794-131">Details zur Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4e794-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="4e794-132">Die lync Server Survivable Branch Appliance umfasst die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="4e794-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="4e794-133">Einen Registrierungsserver für Benutzerauthentifizierung, Registrierung und Anrufrouting</span><span class="sxs-lookup"><span data-stu-id="4e794-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="4e794-134">Einen Vermittlungsserver für die Signalverarbeitung zwischen der Registrierung und einem PSTN-Gateway</span><span class="sxs-lookup"><span data-stu-id="4e794-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="4e794-135">Ein PSTN-Gateway zum Routen von Anrufen an das Telefonfestnetz als Fallback bei WAN-Ausfällen</span><span class="sxs-lookup"><span data-stu-id="4e794-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="4e794-136">SQL Server Express zur Speicherung lokaler Benutzerdaten</span><span class="sxs-lookup"><span data-stu-id="4e794-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="4e794-137">Das Survivable Branch Appliance enthält auch PSTN-Trunks, analoge Ports und einen Ethernet-Adapter.</span><span class="sxs-lookup"><span data-stu-id="4e794-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="4e794-138">Wenn die WAN-Verbindung der Zweigstelle zu einem zentralen Standort nicht mehr verfügbar ist, werden interne Zweigstellenbenutzer weiterhin bei der Survivable Branch Appliance Registrierungsstelle registriert und erhalten unterbrechungsfreie Sprachdienste über die Survivable Branch Appliance-Verbindung mit dem PSTN.</span><span class="sxs-lookup"><span data-stu-id="4e794-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="4e794-139">Zweigstellenbenutzer, die von zu Hause oder von Remotestandorten aus eine Verbindung herstellen, können sich beim Registrierungsserver am zentralen Standort registrieren, wenn die WAN-Leitung zum Zweigstellenstandort nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4e794-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="4e794-140">Diese Benutzer haben Zugriff auf die vollständige Unified Communications-Funktionalität (UM), mit der Ausnahme, dass eingehende Anrufe am Zweigstellenstandort an das Voicemailsystem übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="4e794-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="4e794-141">Wenn die WAN-Verbindung wieder verfügbar ist, sollte für Benutzer am Zweigstellenstandort automatisch die vollständige Funktionalität wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e794-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="4e794-142">Weder das Failover auf die Survivable Branch Appliance noch die Wiederherstellung des Diensts erfordert das vorhanden sein eines IT-Administrators.</span><span class="sxs-lookup"><span data-stu-id="4e794-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="4e794-143">Lync Server unterstützt bis zu zwei Survivable Branch Appliance an einem Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="4e794-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e794-144">Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e794-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="4e794-145">Übersicht über die Bereitstellung einer Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4e794-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="4e794-146">Das Survivable Branch Appliance wird von Herstellern von Originalgeräten in Partnerschaft mit Microsoft hergestellt und in Ihrem Auftrag von Wert Schöpfungs Händlern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4e794-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="4e794-147">Diese Bereitstellung sollte nur erfolgen, nachdem lync Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit dem Zweigstellenstandort vorhanden ist und Zweigstellenbenutzer für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="4e794-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="4e794-148">Ausführliche Informationen zu diesen Phasen finden Sie unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4e794-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e794-149">Phase</span><span class="sxs-lookup"><span data-stu-id="4e794-149">Phase</span></span></th>
<th><span data-ttu-id="4e794-150">Schritte</span><span class="sxs-lookup"><span data-stu-id="4e794-150">Steps</span></span></th>
<th><span data-ttu-id="4e794-151">Benutzerrechte</span><span class="sxs-lookup"><span data-stu-id="4e794-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e794-152">Einrichten Active Directory-Domänendienste für die Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4e794-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="4e794-153"><strong>Am zentralen Standort:</strong></span><span class="sxs-lookup"><span data-stu-id="4e794-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="4e794-154">Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch Appliance am Zweigstellenstandort installieren und aktivieren wird.</span><span class="sxs-lookup"><span data-stu-id="4e794-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="4e794-155">Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)) für Survivable Branch Appliance in Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="4e794-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="4e794-156">Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4e794-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4e794-157">Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein.</span><span class="sxs-lookup"><span data-stu-id="4e794-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="4e794-158">Die Survivable Branch Appliance müssen zur Gruppe RTCSBAUniversalServices gehören, die automatisch bei Verwendung des Topologie-Generators erfolgt.</span><span class="sxs-lookup"><span data-stu-id="4e794-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e794-159">Installieren und aktivieren Sie die Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4e794-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="4e794-160"><strong>Am Zweigstellenstandort:</strong></span><span class="sxs-lookup"><span data-stu-id="4e794-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="4e794-161">Verbinden Sie die Survivable Branch Appliance mit einem Ethernet-Port und einem PSTN-Port.</span><span class="sxs-lookup"><span data-stu-id="4e794-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="4e794-162">Starten Sie die Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="4e794-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="4e794-163">Fügen Sie die Survivable Branch Appliance der Domäne mithilfe des Domänenbenutzerkontos hinzu, das für die Survivable Branch Appliance am zentralen Standort erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4e794-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="4e794-164">Legen Sie FQDN und IP-Adresse auf den FQDN fest, den Sie im Computerkonto erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="4e794-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="4e794-165">Konfigurieren Sie die Survivable Branch Appliance mithilfe der OEM-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="4e794-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="4e794-166">Testen Sie die PSTN-Anbindung.</span><span class="sxs-lookup"><span data-stu-id="4e794-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4e794-167">Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein.</span><span class="sxs-lookup"><span data-stu-id="4e794-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="4e794-168">Details zum Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="4e794-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="4e794-169">Erstellen Sie im Topologie-Generator den Zweigstellenstandort, fügen Sie den Survivable Branch Server zu diesem Standort hinzu, und führen Sie dann den Assistenten für die lync Server-Bereitstellung auf dem Computer aus, auf dem Sie die Rolle installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4e794-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e794-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e794-170">See Also</span></span>


[<span data-ttu-id="4e794-171">Bereitstellen von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e794-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

