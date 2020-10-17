---
title: 'Lync Server 2013: Bereitstellen des Zugriffs durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1878b011ce62ff732f9b31fb905c012872fe743
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525312"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="e0343-102">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-102">Deploying external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0343-103">_**Letztes Änderungsstand des Themas:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="e0343-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="e0343-104">Durch die Bereitstellung von Edge-Komponenten für Microsoft lync Server 2013 können externe Benutzer, die nicht am internen Netzwerk Ihrer Organisation angemeldet sind, einschließlich authentifizierten und anonymen Remotebenutzern, Verbundpartnern (einschließlich XMPP-Partnern), mobilen Clients und Benutzern von öffentlichen Sofortnachrichtendiensten, mit anderen Benutzern in Ihrer Organisation über lync Server kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="e0343-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="e0343-105">Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 unterscheiden sich nicht wesentlich von lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0343-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="e0343-106">Die Tools für die Installation und Verwaltung sind ähnlich wie in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e0343-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0343-107">Microsoft lync Server 2013 &nbsp; Edgeserver-Installation und-Konfiguration kann ein komplexer Prozess sein, der eine potenziell erhebliche Menge an Planung und Koordination mit ihren internen Teams erfordert, einschließlich der Überlegungen zu Sicherheit, Netzwerk, Firewall, Domain Name System (DNS), Lastenausgleich und Public Key-Infrastruktur (PKI).</span><span class="sxs-lookup"><span data-stu-id="e0343-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="e0343-108">Es wird dringend empfohlen, den Planungsprozess und die Dokumentation zu überprüfen und zu verwenden, die vor der Bereitstellung Ihrer Komponenten für den externen Zugriff bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0343-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="e0343-109">Dies hilft beim Durchlaufen des Bereitstellungsprozesses, die Anzahl und die Häufigkeit unerwünschter Änderungen und Probleme zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="e0343-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="e0343-110">Informationen zum Planen des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e0343-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0343-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e0343-111">In This Section</span></span>

  - [<span data-ttu-id="e0343-112">Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="e0343-113">System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="e0343-114">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="e0343-115">Erstellen einer Edge-und Director-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="e0343-116">[Einrichten des Directors in lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span><span class="sxs-lookup"><span data-stu-id="e0343-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="e0343-117">Einrichten von Edge-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="e0343-118">Einrichten von Reverse-Proxyservern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="e0343-119">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="e0343-120">Leitfaden zur Anleitung zur Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="e0343-121">Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="e0343-122">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="e0343-123">Überprüfen der Edge-Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0343-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

