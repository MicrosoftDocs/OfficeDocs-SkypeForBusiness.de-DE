---
title: 'Lync Server 2013: Neue Funktionen für den externen Benutzerzugriff'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="d31ae-102">Neue Funktionen für den externen Benutzerzugriff in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d31ae-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d31ae-103">_**Letztes Änderungsdatum des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="d31ae-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="d31ae-104">Lync Server 2013 führt neue Features ein, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern.</span><span class="sxs-lookup"><span data-stu-id="d31ae-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="d31ae-105">Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die Dienste, die für Ihre Organisation verfügbar sind, besser zu integrieren und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d31ae-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="d31ae-106">Es folgt eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013-Edgeserver-Diensten auswirken können.</span><span class="sxs-lookup"><span data-stu-id="d31ae-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="d31ae-107">**Unterstützung für die IPv6-Adressierung**   lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver-Dienste.</span><span class="sxs-lookup"><span data-stu-id="d31ae-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="d31ae-108">Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edge-Server-Konfiguration über die IP-Adressenkonfiguration im Topologie-Generator verwenden.</span><span class="sxs-lookup"><span data-stu-id="d31ae-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d31ae-109">Die Verwendung von IPv6-Adressen in lync Server 2013 hängt von der Unterstützung von IPv6 in Routern und Firewalls ab, die von Ihrer Organisation bereitgestellt werden, sowie vom Support durch Ihren Internet Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="d31ae-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="d31ae-110">**Mit dem Extensible Messaging and Presence Protocol (XMPP)**   lync Server 2013 wird ein vollständig integrierter XMPP-Proxy (auf den Edge-Servern bereitgestellt) und ein auf den Front-End-Servern bereitgestelltes XMPP-Gateway eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d31ae-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="d31ae-111">Sie können die XMPP-Föderation als optionale Komponente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d31ae-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="d31ae-112">Durch das Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways können Ihre Microsoft lync 2013-Benutzer Kontakte aus XMPP-basierten Partnern für Sofortnachrichten (im) und Anwesenheitsinformationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d31ae-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d31ae-113">Derzeit bieten die XMPP-Dienste in lync Server 2013 nur Sofortnachrichten und Anwesenheitsinformationen zwischen lync-Clients und XMPP-basierten Kontakten.</span><span class="sxs-lookup"><span data-stu-id="d31ae-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="d31ae-114">**Mobilitätsdienste für mobile Clients**   , die in einem Kunden Update für lync Server 2010 eingeführt wurden, Mobilitätsdienste in lync Server 2013 ermöglichen Microsoft lync Mobile-Clients auf Mobiltelefonen und Tablet-Geräten mit unterstützten Apple IOS, Android, Windows Smartphone oder Nokia Mobile Geräte, um solche Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d31ae-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d31ae-115">Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit zu anrufen, eine Rufnummer zu erreichen, Voicemail und Benachrichtigungen über verpasste Anrufe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d31ae-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d31ae-116">Die Mobilitätsdienste verwenden den Reverse-Proxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d31ae-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="d31ae-117">Für Edgeserver sind keine Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d31ae-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="d31ae-118">**Directors sind eine optionale Rolle**   , die die Rolle des Director-Servers in der lync Server 2013-Topologie nicht geändert hat.</span><span class="sxs-lookup"><span data-stu-id="d31ae-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="d31ae-119">Sie hostet weiterhin Webdienste, authentifiziert eingehende Benutzeranforderungen vor und leitet externe Benutzer an Ihren privaten Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="d31ae-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="d31ae-120">Das Ändern des Directors von einer empfohlenen Rolle zu einer optionalen Rolle vermindert nicht den Wert des Directors, sondern hebt die Verringerung der Serveranzahl und anderer Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) ohne Kompromisse bei Features und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d31ae-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="d31ae-121">Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können, ohne dass dies Auswirkungen auf die bereitgestellten Dienste hat, können Sie optional Directors bereitstellen, wenn Sie sich dafür entscheiden.</span><span class="sxs-lookup"><span data-stu-id="d31ae-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="d31ae-122">Sie können den Director mit Sicherheit ausschließen, dass die Front-End-Server die gleichen Dienste an deren Ort bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d31ae-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d31ae-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d31ae-123">See Also</span></span>


[<span data-ttu-id="d31ae-124">Planen und Konfigurieren von IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d31ae-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="d31ae-125">Planen des Zugriffs externer Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d31ae-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d31ae-126">Planen der erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP)-Föderation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d31ae-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

