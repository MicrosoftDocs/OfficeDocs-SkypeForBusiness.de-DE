---
title: 'Lync Server 2013: Bereitstellen des Zugriffs durch externe Benutzer'
description: 'Lync Server 2013: Bereitstellen des Zugriffs durch externe Benutzer.'
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
ms.openlocfilehash: af41a169fe3a72e440e95cfa370a16117fb828a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573441"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6eb32-103">Bereitstellen von externem Benutzer Zugriff in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-103">Deploying external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eb32-104">_**Letztes Änderungsstand des Themas:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="6eb32-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="6eb32-105">Durch die Bereitstellung von Edge-Komponenten für Microsoft lync Server 2013 können externe Benutzer, die nicht am internen Netzwerk Ihrer Organisation angemeldet sind, einschließlich authentifizierten und anonymen Remotebenutzern, Verbundpartnern (einschließlich XMPP-Partnern), mobilen Clients und Benutzern von öffentlichen Sofortnachrichtendiensten, mit anderen Benutzern in Ihrer Organisation über lync Server kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6eb32-105">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="6eb32-106">Die Bereitstellungs-und Konfigurationsprozesse für lync Server 2013 unterscheiden sich nicht wesentlich von lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6eb32-106">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="6eb32-107">Die Tools für die Installation und Verwaltung sind ähnlich wie in lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6eb32-107">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6eb32-108">Microsoft lync Server 2013 &nbsp; Edgeserver-Installation und-Konfiguration kann ein komplexer Prozess sein, der eine potenziell erhebliche Menge an Planung und Koordination mit ihren internen Teams erfordert, einschließlich der Überlegungen zu Sicherheit, Netzwerk, Firewall, Domain Name System (DNS), Lastenausgleich und Public Key-Infrastruktur (PKI).</span><span class="sxs-lookup"><span data-stu-id="6eb32-108">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="6eb32-109">Es wird dringend empfohlen, den Planungsprozess und die Dokumentation zu überprüfen und zu verwenden, die vor der Bereitstellung Ihrer Komponenten für den externen Zugriff bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6eb32-109">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="6eb32-110">Dies hilft beim Durchlaufen des Bereitstellungsprozesses, die Anzahl und die Häufigkeit unerwünschter Änderungen und Probleme zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="6eb32-110">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="6eb32-111">Informationen zum Planen des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external User Access in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6eb32-111">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6eb32-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6eb32-112">In This Section</span></span>

  - [<span data-ttu-id="6eb32-113">Prüfliste zur Bereitstellung für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-113">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="6eb32-114">System Anforderungen für Komponenten für den Zugriff durch externe Benutzer für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-114">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="6eb32-115">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-115">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="6eb32-116">Erstellen einer Edge-und Director-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-116">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="6eb32-117">[Einrichten des Directors in lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span><span class="sxs-lookup"><span data-stu-id="6eb32-117">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="6eb32-118">Einrichten von Edge-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-118">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="6eb32-119">Einrichten von Reverse-Proxyservern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-119">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="6eb32-120">Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-120">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="6eb32-121">Leitfaden zur Anleitung zur Lync-Skype Konnektivität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-121">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="6eb32-122">Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-122">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="6eb32-123">Bereitstellen von Mobilität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-123">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="6eb32-124">Überprüfen der Edge-Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb32-124">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

