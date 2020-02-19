---
title: 'Lync Server 2013: neue Features für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70d7720abb5f30b4cb4c953b16dceac6c505d103
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a743b-102">Neue Features für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a743b-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a743b-103">_**Letztes Änderungsstand des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a743b-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a743b-104">In lync Server 2013 werden neue Features vorgestellt, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern.</span><span class="sxs-lookup"><span data-stu-id="a743b-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="a743b-105">Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die für Ihre Organisation verfügbaren Dienste besser zu integrieren und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a743b-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="a743b-106">Im folgenden finden Sie eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013 Edgeserver Diensten auswirken können.</span><span class="sxs-lookup"><span data-stu-id="a743b-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="a743b-107">**Unterstützung für IPv6-Adressierungs**   lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver Dienste.</span><span class="sxs-lookup"><span data-stu-id="a743b-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="a743b-108">Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edgeserver Konfiguration über die IP-Adresskonfiguration im Topologie-Generator verwenden.</span><span class="sxs-lookup"><span data-stu-id="a743b-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a743b-109">Die Verwendung von IPv6-Adressen in lync Server 2013 hängt von der Unterstützung von IPv6 in Routern und Firewalls ab, die Ihre Organisation bereitstellt, sowie von der Unterstützung durch Ihren Internet Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="a743b-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="a743b-110">**Xmpp (Extensible Messaging and Presence Protocol)**   lync Server 2013 stellt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway auf Ihren Front-End-Servern vor.</span><span class="sxs-lookup"><span data-stu-id="a743b-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="a743b-111">Sie können einen XMPP-Verbund als optionale Komponente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a743b-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="a743b-112">Wenn Sie den XMPP-Proxy und das XMPP-Gateway hinzufügen und konfigurieren, können Ihre Microsoft lync 2013-Benutzer Kontakte von XMPP-basierten Partnern für Chatnachrichten und Anwesenheitsinformationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a743b-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a743b-113">Derzeit bieten die XMPP-Dienste in lync Server 2013 nur Chatnachrichten und Anwesenheitsinformationen zwischen lync-Clients und XMPP-basierten Kontakten.</span><span class="sxs-lookup"><span data-stu-id="a743b-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="a743b-114">**Mobilitätsdienste für mobile Clients**   , die in einem Kunden Update für lync Server 2010 eingeführt wurden, ermöglichen Mobilitätsdienste in lync Server 2013 Microsoft lync Mobile-Clients auf Mobiltelefonen und Tablet-Geräten, die unterstützte Apple IOS-, Android-, Windows Phone-oder Nokia Mobile-Geräte verwenden, zum Ausführen solcher Aktivitäten wie senden und empfangen von Sofortnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit.</span><span class="sxs-lookup"><span data-stu-id="a743b-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="a743b-115">Zudem unterstützen Mobilgeräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.</span><span class="sxs-lookup"><span data-stu-id="a743b-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a743b-116">Die Mobilitätsdienste verwenden den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind.</span><span class="sxs-lookup"><span data-stu-id="a743b-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="a743b-117">Änderungen an Edgeservern sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a743b-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="a743b-118">**Directors sind eine optionale Rolle**   , die die Rolle des Director-Servers in der lync Server 2013-Topologie nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="a743b-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="a743b-119">Er hostet weiterhin Webdienste, führt eine Vorabauthentifizierung eingehender Benutzeranfragen durch und leitet externe Benutzer an ihren Pool weiter.</span><span class="sxs-lookup"><span data-stu-id="a743b-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="a743b-120">Wenn Sie den Director von einer empfohlenen Rolle in eine optionale Rolle ändern, verringert sich nicht der Wert des Directors, sondern es wird die Verringerung der Serveranzahl und anderer Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) ohne unterstrichen betont. kompromittieren von Features und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a743b-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="a743b-121">Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können und keine Auswirkungen auf die bereitgestellten Dienste haben, können Sie optional Directors bereitstellen, wenn Sie sich für entscheiden.</span><span class="sxs-lookup"><span data-stu-id="a743b-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="a743b-122">Sie können den Director sicher mit Sicherheit ausschließen, dass die Front-End-Server dieselben Dienste an ihrer Stelle bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="a743b-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a743b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a743b-123">See Also</span></span>


[<span data-ttu-id="a743b-124">Planen und Konfigurieren von IPv6 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a743b-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="a743b-125">Planen des Zugriffs durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a743b-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="a743b-126">Planen des XMPP-Verbunds (Extensible Messaging and Presence Protocol) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a743b-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

