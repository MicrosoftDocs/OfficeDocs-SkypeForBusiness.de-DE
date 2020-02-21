---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f2897434eb275b82ef9ab4ef78e32e99e8d0a5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6065a-102">Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6065a-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6065a-103">_**Letztes Änderungsstand des Themas:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="6065a-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="6065a-104">Bevor Sie Ihr Umkreisnetzwerk bereitstellen und die Unterstützung für externe Benutzer implementieren, müssen Sie Ihre Microsoft lync Server 2013 internen Server bereits bereitgestellt haben, einschließlich einer Front-End-Pool oder einer Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="6065a-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="6065a-105">Wenn Sie die optionalen Directors in Ihrem internen Netzwerk bereitstellen möchten, sollten Sie Sie auch vor dem Bereitstellen von Edgeserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6065a-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="6065a-106">Ausführliche Informationen zum Bereitstellungsprozess für Director finden Sie unter [Scenarios for the Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6065a-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="6065a-107">Microsoft lync Server 2013 enthält Tools zur Erleichterung der Planung und Bereitstellung von internen Servern und Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="6065a-108">Veröffentlichen Sie nach dem Abschließen der Topologie die resultierende Topologiedefinition in Ihrer Produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="6065a-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="6065a-109">Um diese Aufgabe ausführen zu können, müssen Sie Mitglied der Gruppe **Domänen-Admins** und der Gruppe **RTCUniversalServerAdmins** sein.</span><span class="sxs-lookup"><span data-stu-id="6065a-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="6065a-110">**Planungs**   Tool Office Communications Server 2007 R2 ein Planungstool und ein Edge-Planungstool enthalten, mit deren Hilfe Sie das Topologie-Design vereinfachen können.</span><span class="sxs-lookup"><span data-stu-id="6065a-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="6065a-111">In lync Server 2010 wurden diese beiden Tools zu einem einzigen Planungs Tool zusammengefasst, das zusätzliche Features und Funktionen wie das Sammeln geplanter Benutzeranzahl, Sprachanforderungen, Zugriffstypen für externe Benutzer und Verbund Optionen aufweist.</span><span class="sxs-lookup"><span data-stu-id="6065a-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="6065a-112">Darüber hinaus können Sie die Netzwerkparameter Ihrer Infrastruktur wie IP-Adressen, Lastenausgleichs Typen und andere Aspekte des Umkreisnetzwerks planen.</span><span class="sxs-lookup"><span data-stu-id="6065a-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="6065a-113">**Topologie-Generator**   lync Server 2013 Topologie-Generator unterstützt Sie bei der Definition Ihrer Topologie und Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6065a-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="6065a-114">Der Topologie-Generator ist für die Bereitstellung von Servern erforderlich, auf denen lync Server 2013 ausführt.</span><span class="sxs-lookup"><span data-stu-id="6065a-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="6065a-115">Der Topologie-Generator veröffentlicht die Ergebnisse in einem zentralen Verwaltungsspeicher, der verwendet wird, um alle Server zu konfigurieren, auf denen lync Server 2013 in Ihrer Organisation läuft.</span><span class="sxs-lookup"><span data-stu-id="6065a-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="6065a-116">Sie können lync Server 2013 nicht auf Servern ohne Verwendung des Topologie-Generators installieren.</span><span class="sxs-lookup"><span data-stu-id="6065a-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="6065a-117">Wenn Sie Ihre Edge-Topologie während des Planungsprozesses entworfen haben, einschließlich der Ausführung des Topologie-Generators zur Definition ihrer Edge-Topologie, können Sie diese Ergebnisse verwenden, um die Edgeserver-Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="6065a-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="6065a-118">Wenn Sie die Edge-Topologie zuvor nicht fertig erstellt haben oder die zuvor angegebenen Informationen ändern möchten, müssen Sie den Topologie-Generator ausführen, bevor Sie mit anderen Bereitstellungsschritten fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6065a-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="6065a-119">Ausführliche Informationen zum Erstellen Ihrer Topologie finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6065a-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="6065a-120">Ausführliche Informationen zum Planungs Tool und zum Topologie-Generator finden Sie unter [Beginn des Planungsprozesses für lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6065a-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="6065a-121">Die folgende Tabelle zeigt eine Übersicht über den Bereitstellungsprozess für Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="6065a-122">Informationen zum Überprüfen der Planungsentscheidungen, die vor der Bereitstellung des Zugriffs durch externe Benutzer getroffen werden müssen, finden Sie unter [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6065a-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6065a-123">Die Informationen in der folgenden Tabelle gelten für eine neue Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="6065a-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="6065a-124">Wenn Sie Edgeserver in einer lync Server 2010-, Office Communications Server 2007 R2-oder Office Communications Server 2007-Umgebung bereitgestellt haben, finden Sie weitere Informationen zum Migrieren zu lync Server 2013 in der <A href="migration.md">Migration</A> .</span><span class="sxs-lookup"><span data-stu-id="6065a-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="6065a-125">Die Migration wird von keiner Version vor Office Communications Server 2007 R2 unterstützt, einschließlich Office Communications Server 2007, Live Communications Server 2005 und Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="6065a-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="6065a-126">Halten Sie sich bei der Bereitstellung des Umkreisnetzwerks und der Edgeserver an folgende Richtlinien, um sowohl die Leistung und Sicherheit der Edgeserver zu erhöhen als auch die Bereitstellung zu erleichtern:</span><span class="sxs-lookup"><span data-stu-id="6065a-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="6065a-127">Stellen Sie Edgeserver erst bereit, nachdem Sie den Betrieb von lync Server 2013 in Ihrer Organisation getestet und überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="6065a-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="6065a-p108">Es wird empfohlen, die Edgeserver nicht in einer Domäne, sondern in einer Arbeitsgruppe bereitzustellen. Dies vereinfacht die Installation und vermeidet eine Verbindung zwischen Active Directory-Domänendiensten (AD DS) und dem Umkreisnetzwerk. Eine Verbindung zwischen AD DS und dem Umkreisnetzwerk kann ein erhebliches Sicherheitsproblem darstellen.</span><span class="sxs-lookup"><span data-stu-id="6065a-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="6065a-p109">Ein Edgeserver kann einer Domäne hinzugefügt werden, die sich ganz im Umkreisnetzwerk befindet. Dies wird jedoch nicht empfohlen. Ein Edgeserver, der Teil der internen Domäne ist, verletzt die Grenzen des vertrauenswürdigen Netzwerks, wobei das Internet die am wenigsten vertrauenswürdige Zone, das Umkreisnetzwerk vertrauenswürdiger als das Internet und das interne Netzwerk am vertrauenswürdigsten ist. Ein Edgeserver, der Mitglied der Domäne ist, ist automatisch ein Teil des vertrauenswürdigsten Netzwerks, befindet sich jedoch in einem weniger vertrauenswürdigen Netzwerk (dem Umkreisnetzwerk).</span><span class="sxs-lookup"><span data-stu-id="6065a-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="6065a-134">Bereitstellungsprozess für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="6065a-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6065a-135">Phase</span><span class="sxs-lookup"><span data-stu-id="6065a-135">Phase</span></span></th>
<th><span data-ttu-id="6065a-136">Schritte</span><span class="sxs-lookup"><span data-stu-id="6065a-136">Steps</span></span></th>
<th><span data-ttu-id="6065a-137">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6065a-137">Permissions</span></span></th>
<th><span data-ttu-id="6065a-138">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6065a-139">Erstellen Sie die geeignete Edgetopologie, und ermitteln Sie die geeigneten Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6065a-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6065a-140">Führen Sie den Topologie-Generator aus, um Edgeserver Einstellungen zu konfigurieren und die Topologie zu erstellen und zu veröffentlichen, und verwenden Sie dann lync Server-Verwaltungsshell, um die Topologie-Konfigurationsdatei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6065a-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6065a-141">Gruppe " <strong>Domänen-Admins</strong> " und <strong>RTCUniversalServerAdmins</strong> oder <strong>CsAdmins</strong> -Gruppe</span><span class="sxs-lookup"><span data-stu-id="6065a-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6065a-142">Sie können eine Topologie unter Verwendung eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, für die Veröffentlichung einer Topologie ist jedoch ein Konto erforderlich, das Mitglied der Gruppe <STRONG>Domänen-Admins</STRONG> und der Gruppe <STRONG>RTCUniversalServerAdmins</STRONG> ist.</span><span class="sxs-lookup"><span data-stu-id="6065a-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="6065a-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Erstellen einer Edge-und Director-Topologie in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6065a-144">Bereiten Sie das Setup vor.</span><span class="sxs-lookup"><span data-stu-id="6065a-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6065a-145">Stellen Sie sicher, dass die Systemvoraussetzungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="6065a-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="6065a-146">Konfigurieren Sie IP-Adressen (IPv4 und IPv6, falls verwendet) für die internen und die öffentlichen Netzwerkschnittstellen auf jedem Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6065a-147">Konfigurieren Sie interne und externe DNS-Einträge (Host A und AAAA für IPv4 und IPv6), einschließlich Konfiguration des DNS-Suffixes auf dem Computer, der als Edgeserver bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6065a-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6065a-p110">(Optional) Erstellen und installieren Sie öffentliche Zertifikate. Die zum Anfordern von Zertifikaten erforderliche Zeit richtet sich nach der Zertifizierungsstelle, die das Zertifikat ausgibt. Wenn Sie diesen Schritt jetzt überspringen, müssen Sie ihn während der Installation der Edgeserver ausführen. Die Edgeserverdienste können erst gestartet werden, wenn Zertifikate angefordert und installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6065a-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="6065a-p111">Konfigurieren Sie die Unterstützung zur Verbindung mit öffentlichen Instant Messaging-Diensten, wenn Ihre Bereitstellung eine Kommunikation mit Benutzern von Windows Live, AOL oder Yahoo! unterstützen soll.</span><span class="sxs-lookup"><span data-stu-id="6065a-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="6065a-154">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6065a-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="6065a-155">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6065a-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="6065a-156">Messenger, bis der Dienst das Datum heruntergefahren hat.</span><span class="sxs-lookup"><span data-stu-id="6065a-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="6065a-157">Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo!</span><span class="sxs-lookup"><span data-stu-id="6065a-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6065a-158">wurde angekündigt.</span><span class="sxs-lookup"><span data-stu-id="6065a-158">has been announced.</span></span> <span data-ttu-id="6065a-159">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6065a-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="6065a-160">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6065a-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="6065a-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="6065a-161">Messenger.</span></span> <span data-ttu-id="6065a-162">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6065a-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="6065a-163">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="6065a-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="6065a-164">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6065a-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="6065a-165">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</span><span class="sxs-lookup"><span data-stu-id="6065a-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="6065a-166">Bereitstellen von Unterstützung für die XMPP-und Verbundunterstützung für Office Communications Server 2007, Office Communications Server 2007 R2 lync Server 2010 Partner, wenn Ihre Bereitstellung diese verwendet</span><span class="sxs-lookup"><span data-stu-id="6065a-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="6065a-167">Konfigurieren Sie die Firewalls.</span><span class="sxs-lookup"><span data-stu-id="6065a-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6065a-168">Je nach Organisationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="6065a-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="6065a-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6065a-170">Richten Sie den Reverseproxy ein.</span><span class="sxs-lookup"><span data-stu-id="6065a-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6065a-171">Richten Sie den Reverseproxy ein (beispielsweise für Microsoft Forefront Threat Management Gateway 2010 oder ISA (Microsoft Internet Security and Acceleration Server) mit Service Pack 1) im Umkreisnetzwerk, beziehen Sie die erforderlichen öffentlichen Zertifikate, und konfigurieren Sie die Webveröffentlichungsregeln auf dem Reverse-Proxy Server.</span><span class="sxs-lookup"><span data-stu-id="6065a-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="6065a-172">Bereiten Sie den Reverseproxy für Mobilitätsdienste vor, falls Sie Mobilität eingeplant haben und die Mobilitätsdienste im Front-End-Pool oder auf dem Standard Edition-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6065a-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6065a-173">Gruppe <strong>Administratoren</strong> oder Reverseproxy-Administrator</span><span class="sxs-lookup"><span data-stu-id="6065a-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="6065a-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Einrichten von Reverse-Proxyservern für lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6065a-175">Richten Sie einen Director ein (optional).</span><span class="sxs-lookup"><span data-stu-id="6065a-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6065a-176">(Optional) Installieren und konfigurieren Sie einen oder mehrere Director-Server im internen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="6065a-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6065a-177">Gruppe <strong>Administratoren</strong></span><span class="sxs-lookup"><span data-stu-id="6065a-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="6065a-178"><a href="lync-server-2013-setting-up-the-director.md">Einrichten des Directors in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6065a-179">Richten Sie die Edgeserver ein.</span><span class="sxs-lookup"><span data-stu-id="6065a-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6065a-180">Installieren Sie die erforderliche Software.</span><span class="sxs-lookup"><span data-stu-id="6065a-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="6065a-181">Übertragen Sie die exportierte Topologiekonfigurationsdatei auf jeden Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6065a-182">Installieren Sie die lync Server 2013 Software auf jeder Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6065a-183">Konfigurieren Sie die Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="6065a-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="6065a-184">Fordern Sie Zertifikate für alle Edgeserver an, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="6065a-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="6065a-185">Starten Sie die Edgeserverdienste.</span><span class="sxs-lookup"><span data-stu-id="6065a-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6065a-186">Gruppe <strong>Administratoren</strong></span><span class="sxs-lookup"><span data-stu-id="6065a-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="6065a-187"><a href="lync-server-2013-setting-up-edge-servers.md">Einrichten von Edge-Servern in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6065a-188">Konfigurieren Sie die Bereitstellung für den Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="6065a-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6065a-189">Verwenden Sie die lync Server-Systemsteuerung, um die Unterstützung für jede der folgenden Einstellungen zu konfigurieren (sofern zutreffend):</span><span class="sxs-lookup"><span data-stu-id="6065a-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="6065a-190">Mediarelay</span><span class="sxs-lookup"><span data-stu-id="6065a-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="6065a-191">Partnerverbundroute</span><span class="sxs-lookup"><span data-stu-id="6065a-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="6065a-192">Remotebenutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="6065a-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="6065a-193">Partnerverbund mit lync Server, Office Communications Server und Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="6065a-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="6065a-194">Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="6065a-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="6065a-195">XMPP-Verbund</span><span class="sxs-lookup"><span data-stu-id="6065a-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="6065a-196">Anonyme Benutzer</span><span class="sxs-lookup"><span data-stu-id="6065a-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="6065a-197">Konfigurieren Sie Benutzerkonten für Remotebenutzerzugriff, Partnerverbund, die Verbindung mit öffentlichen Instant Messaging-Diensten, XMPP und die Unterstützung anonymer Benutzer (sofern gewünscht)</span><span class="sxs-lookup"><span data-stu-id="6065a-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6065a-198">Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="6065a-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="6065a-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6065a-200">Überprüfen Sie Ihre Edgeserverkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="6065a-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6065a-201">Überprüfen Sie die Serverkonnektivität, und stellen Sie sicher, dass die Replikation der Konfigurationsdaten interner Server ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="6065a-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="6065a-202">Stellen Sie sicher, dass externe Benutzer eine Verbindung herstellen können – Remotebenutzer, Benutzer in Partnerdomänen, Benutzer öffentlicher Instant Messaging-Dienste und anonyme Benutzer eingeschlossen (je nach Anforderungen für Ihre Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="6065a-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="6065a-203">Überprüfen der Konfiguration und der Kommunikation mit dem lync Server Remote Connectivity Analyzer<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="6065a-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="6065a-204">Konfiguration der Fehlersuche und Hilfe bei Kommunikationsproblemen</span><span class="sxs-lookup"><span data-stu-id="6065a-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6065a-205">Zum Überprüfen der Replikation: Gruppe <strong>RTCUniversalServerAdmins</strong> oder Benutzerkonto mit zugewiesener Rolle <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="6065a-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="6065a-206">Zum Überprüfen der Benutzerkonnektivität: Ein Benutzer für jede Art von externem Zugriff, der unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="6065a-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="6065a-207">Remotebenutzer</span><span class="sxs-lookup"><span data-stu-id="6065a-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="6065a-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Überprüfen der Edge-Bereitstellung in lync Server 2013</a> in der Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="6065a-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

