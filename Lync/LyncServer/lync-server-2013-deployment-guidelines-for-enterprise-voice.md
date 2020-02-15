---
title: 'Lync Server 2013: Bereitstellungsrichtlinien für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770dfe3ce43af7dc2e6984698c095430b5c34f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="422ae-102">Bereitstellungsrichtlinien für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="422ae-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="422ae-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="422ae-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="422ae-104">In diesem Thema werden die Voraussetzungen und anderen Richtlinien beschrieben, die Sie bei der Bereitstellung von lync Server 2013 und der Enterprise-VoIP-Arbeitsauslastung berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="422ae-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="422ae-105">Voraussetzungen für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="422ae-105">Deployment Prerequisites</span></span>

<span data-ttu-id="422ae-106">Für eine optimale Benutzerfreundlichkeit bei der Bereitstellung von Enterprise-VoIP stellen Sie sicher, dass Ihre IT-Infrastruktur, Ihr Netzwerk und ihre Systeme die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="422ae-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="422ae-107">Lync Server 2013 Standard Edition oder Enterprise Edition ist in Ihrem Netzwerk installiert und betriebsbereit.</span><span class="sxs-lookup"><span data-stu-id="422ae-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="422ae-108">Alle Edgeserver werden in Ihrem Umkreisnetzwerk bereitgestellt und in Betrieb genommen, einschließlich Edgeserver mit Zugriffs-Edgedienst, A/V-Edgedienst, Webkonferenz-Edgedienst und einem Reverse-Proxy.</span><span class="sxs-lookup"><span data-stu-id="422ae-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="422ae-109">Mindestens ein Benutzer wurde für lync Server erstellt und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="422ae-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="422ae-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) oder neuestes Service Pack oder Microsoft Exchange Server 2010 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="422ae-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="422ae-111">Eine davon ist für die Integration von Exchange Unified Messaging (um) mit lync Server erforderlich, um umfangreiche Benachrichtigungen und Anrufprotokoll Informationen für Clientendpunkte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="422ae-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="422ae-112">Für jeden Benutzer, der für Enterprise-VoIP aktiviert werden soll, wurde eine eindeutige primäre Telefonnummer festgelegt, normalisiert und in das Attribut **msRTCSIP-Linie** kopiert.</span><span class="sxs-lookup"><span data-stu-id="422ae-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="422ae-113">Lync Server unterstützt E. 164-Nummern und DID-Nummern (nicht direktes Inward Dialing).</span><span class="sxs-lookup"><span data-stu-id="422ae-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="422ae-114">Nicht-DID-Nummern können im Format <STRONG> &lt;E. 164&gt;; Ext =&lt;Extension&gt; </STRONG> oder als Ziffernfolge dargestellt werden, mit der Voraussetzung, dass die private Durchwahl im gesamten Unternehmen eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="422ae-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="422ae-115">Beispielsweise kann eine private Zahl von 1001 als <STRONG>+ 1425550100; ext = 1001</STRONG>oder als <STRONG>1001</STRONG>dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="422ae-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="422ae-116">Wenn er als <STRONG>1001</STRONG>dargestellt wird, besteht die Erwartung, dass diese private Nummer im gesamten Unternehmen eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="422ae-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="422ae-117">Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der Gruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="422ae-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="422ae-118">Office Communicator 2007 wird mindestens erfolgreich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="422ae-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="422ae-119">Für die Verwendung neuer Features in dieser Version wird lync 2013 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="422ae-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="422ae-120">Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="422ae-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="422ae-121">Für jeden Computer, auf dem Sie einen Vermittlungsserver installieren, gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="422ae-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="422ae-122">Ein Mitgliedsserver einer Domäne, der für Active Directory-Domänendienste vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="422ae-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="422ae-123">Informationen Active Directory-Domänendienste Vorbereitungsverfahren finden Sie unter [vorbereiten Active Directory-Domänendienste für lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="422ae-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="422ae-124">Es muss eines der folgenden Betriebssysteme ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="422ae-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="422ae-125">Die 64-Bit-Version von Windows Server 2008 Standard</span><span class="sxs-lookup"><span data-stu-id="422ae-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="422ae-126">Die 64-Bit-Version von Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="422ae-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="422ae-p105">Wenn die Verbindung zum Telefonfestnetz (Public Switched Telephone Network, PSTN) oder zu einer Nebenstellenanlage (Private Branch Exchange, PBX) per TDM-Verbindung (Time Division Multiplexing) erfolgt, stehen für die Bereitstellung ein oder mehrere PSTN-Gateways zur Verfügung. (Falls die Verbindung über einen SIP-Trunk hergestellt wird, ist kein PSTN-Gateway erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="422ae-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="422ae-129">Stromausfall, Ausfall des Netzwerks oder des Telefondiensts</span><span class="sxs-lookup"><span data-stu-id="422ae-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="422ae-130">Wenn ein Ausfall, eine Unterbrechung oder andere Beeinträchtigungen der Stromversorgung, des Netzwerks oder der Telefondienste an Ihrem Standort auftreten, funktionieren die sprach-, Chat-, Anwesenheits-und andere Features von lync Server sowie alle mit lync Server verbundenen Geräte möglicherweise nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="422ae-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="422ae-131">Abhängigkeit von Enterprise-VoIP von der Verfügbarkeit des Servers sowie der Funktionsfähigkeit des VoIP-Client und der Hardware</span><span class="sxs-lookup"><span data-stu-id="422ae-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="422ae-132">Die Sprachkommunikation mit lync Server hängt von der Verfügbarkeit der Server Software und der ordnungsgemäßen Funktion der VoIP-Clients oder der Hardware Telefongeräte ab, die eine Verbindung mit der Server Software herstellen.</span><span class="sxs-lookup"><span data-stu-id="422ae-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="422ae-133">Alternativer Zugriff auf Notrufdienste</span><span class="sxs-lookup"><span data-stu-id="422ae-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="422ae-134">Für die Standorte, an denen Sie einen VoIP-Client installieren (beispielsweise einen PC, auf dem lync-Client oder ein lync Phone Edition-Gerät ausgeführt wird), wird empfohlen, dass Sie eine Sicherungsoption für Benutzer zum Aufrufen von Notrufdiensten (beispielsweise 911 oder 999) für den Fall eines Stromausfalls beibehalten. , Beeinträchtigung der Netzwerkkonnektivität, Ausfall eines Telefondiensts oder ein anderes Problem, das den Betrieb von lync Server-, lync-oder lync Phone Edition-Geräten hemmen kann.</span><span class="sxs-lookup"><span data-stu-id="422ae-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="422ae-135">Zu diesen alternativen Optionen kann ein Telefon gehören, das mit einer standardmäßigen Telefonnetz Leitung oder einem Mobiltelefon verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="422ae-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="422ae-136">Notruf und Telefonsysteme mit mehreren Leitungen</span><span class="sxs-lookup"><span data-stu-id="422ae-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="422ae-137">Die Verwendung von Mehrleitungstelefonsystemen (MLTS) unterliegt eventuell gesetzlichen Bestimmungen, die bei einem Notruf die Angabe der Rufnummer, der Durchwahl und/oder des physischen Standorts des Anrufers erfordern.</span><span class="sxs-lookup"><span data-stu-id="422ae-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="422ae-138">In dieser Version können lync Server so konfiguriert werden, dass der physische Standort eines Anrufers für einen Anbieter von Notrufdiensten bereitgestellt wird, wie in [Planning for Emergency Services (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="422ae-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="422ae-139">Die Einhaltung von MLTS-Gesetzen liegt in der alleinigen Verantwortung des Käufers von lync Server-, lync-Client-und lync Phone Edition-Geräten.</span><span class="sxs-lookup"><span data-stu-id="422ae-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

